<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Harmonix</title>
  <!-- Font Awesome for Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #000000, #ff4081);
      color: #fff;
      margin: 0;
      padding: 0;
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(0,0,0,0.8);
      padding: 15px 30px;
    }

    nav h1 {
      font-size: 24px;
      color: #ff4081;
    }

    nav ul {
      list-style: none;
      display: flex;
      gap: 20px;
      margin: 0;
      padding: 0;
    }

    nav ul li a {
      color: #fff;
      text-decoration: none;
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 8px;
      transition: color 0.3s ease;
    }

    nav ul li a:hover {
      color: #ff4081;
    }

    .search-container {
      position: relative;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .search-icon {
      color: #ff4081;
      font-size: 18px;
      cursor: pointer;
      transition: color 0.3s ease;
    }

    .search-icon:hover {
      color: #fff;
    }

    #search {
      width: 5%;
      transition: width 0.4s ease;
      padding: 8px 12px;
      border-radius: 20px;
      border: none;
      outline: none;
      background: rgba(255, 255, 255, 0.9);
      color: #000;
    }

    #search:focus {
      width: 45%;
      background: #fff;
      box-shadow: 0 0 10px rgba(255, 64, 129, 0.5);
    }

    #search::placeholder {
      color: #999;
    }

    main {
      padding: 40px;
      text-align: center;
    }

    section {
      display: none;
    }

    section.active {
      display: block;
    }

    section h2 {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
      font-size: 28px;
      margin-bottom: 20px;
    }

    section h2 i {
      color: #ff4081;
    }

    button {
      background: #ff4081;
      border: none;
      padding: 10px 20px;
      margin: 10px;
      color: white;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      transition: background 0.3s ease;
    }

    button:hover {
      background: #f50057;
    }

    button.hidden {
      display: none;
    }

    button i {
      font-size: 18px;
    }
  </style>
</head>
<body>
  <nav>
    <h1><i class="fas fa-music"></i> Harmonix</h1>
    <ul>
      <li><a href="#" onclick="showPage('home')"><i class="fas fa-home"></i> Home</a></li>
      <li><a href="#" onclick="showPage('you')"><i class="fas fa-user"></i> You</a></li>
      <li><a href="#" onclick="showPage('calendar')"><i class="fas fa-calendar-alt"></i> Event Calendar</a></li>
      <li><a href="#" onclick="showPage('collections')"><i class="fas fa-compact-disc"></i> Collections</a></li>
    </ul>
    <div class="search-container">
      <i class="fas fa-search search-icon"></i>
      <input type="text" id="search" placeholder="Let's dive in ....">
    </div>
  </nav>

  <main>
    <section id="home" class="active">
      <h2><i class="fas fa-home"></i> Home</h2>
      <p>Discover trending tracks and curated playlists.</p>
      <button class="searchable" data-keywords="play sound music" onclick="playSound()"><i class="fas fa-play"></i> Play Sound</button>
      <button class="searchable" data-keywords="stop sound pause" onclick="stopSound()"><i class="fas fa-stop"></i> Stop Sound</button>
    </section>

    <section id="you">
      <h2><i class="fas fa-user-circle"></i> You</h2>
      <p>Your personalized music space.</p>
      <button class="searchable" data-keywords="favorites heart liked"><i class="fas fa-heart"></i> Your Favorites</button>
      <button class="searchable" data-keywords="playlists list"><i class="fas fa-list"></i> Your Playlists</button>
    </section>

    <section id="calendar">
      <h2><i class="fas fa-calendar-alt"></i> Event Calendar</h2>
      <p>Upcoming concerts and events.</p>
      <button class="searchable" data-keywords="featured events star"><i class="fas fa-star"></i> Featured Events</button>
      <button class="searchable" data-keywords="near location dot"><i class="fas fa-location-dot"></i> Near You</button>
    </section>

    <section id="collections">
      <h2><i class="fas fa-compact-disc"></i> Collections</h2>
      <p>Browse curated collections of tracks.</p>
      <button class="searchable" data-keywords="trending fire hot"><i class="fas fa-fire"></i> Trending</button>
      <button class="searchable" data-keywords="new releases music"><i class="fas fa-music"></i> New Releases</button>
    </section>
  </main>

  <!-- Libraries -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/howler/2.2.3/howler.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/tone/14.8.39/Tone.min.js"></script>
  <script>
    // Page navigation
    function showPage(pageId) {
      document.querySelectorAll('main section').forEach(sec => sec.classList.remove('active'));
      document.getElementById(pageId).classList.add('active');
      // Clear search when navigating
      document.getElementById('search').value = '';
      filterButtons('');
    }

    // Automated search functionality
    const searchInput = document.getElementById('search');
    searchInput.addEventListener('input', (e) => {
      filterButtons(e.target.value.toLowerCase());
    });

    // Focus search input when search icon is clicked
    document.querySelector('.search-icon').addEventListener('click', () => {
      searchInput.focus();
    });

    function filterButtons(query) {
      const buttons = document.querySelectorAll('button.searchable');

      buttons.forEach(button => {
        const keywords = button.dataset.keywords.toLowerCase();
        const buttonText = button.textContent.toLowerCase();
        
        if (query === '' || keywords.includes(query) || buttonText.includes(query)) {
          button.classList.remove('hidden');
        } else {
          button.classList.add('hidden');
        }
      });
    }

    // Howler.js demo
    const sound = new Howl({
      src: ['https://actions.google.com/sounds/v1/cartoon/clang_and_wobble.ogg']
    });

    function playSound() {
      sound.play();
    }

    function stopSound() {
      sound.stop();
    }

    // Tone.js demo
    document.addEventListener('keydown', async (e) => {
      await Tone.start();
      const synth = new Tone.Synth().toDestination();
      synth.triggerAttackRelease("C4", "8n");
    });
  </script>
</body>
</html>
