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
      background: #000000;
      color: #fff;
      margin: 0;
      padding: 0;
    }

    nav {
      position: fixed;
      bottom: 0;
      width: 100%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: #000000;
      padding: 15px 30px;
      box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.5);
      z-index: 999;
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

    /* Search Container - Top Left with Horizontal Layout */
    .search-container {
      position: fixed;
      top: 20px;
      left: 20px;
      display: flex;
      align-items: center;
      gap: 12px;
      z-index: 1000;
    }

    #search {
      width: 25%;
      padding: 12px 16px;
      border-radius: 20px;
      border: 2px solid transparent;
      outline: none;
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(10px);
      color: #fff;
      font-size: 14px;
      transition: width 0.4s ease, border-color 0.4s ease;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
      animation: neonGlow 2s infinite;
      position: relative;
    }

    #search::placeholder {
      color: rgba(255, 255, 255, 0.6);
    }

    #search:focus {
      width: 65%;
      background: rgba(255, 255, 255, 0.15);
      box-shadow: 0 0 20px rgba(255, 64, 129, 0.6), inset 0 0 10px rgba(255, 64, 129, 0.2);
    }

    /* Neon Glimmering and Glittering Animation */
    @keyframes neonGlow {
      0% {
        border-color: #ff4081;
        box-shadow: 0 0 10px rgba(255, 64, 129, 0.5), inset 0 0 5px rgba(255, 64, 129, 0.1);
      }
      50% {
        border-color: #ff10a0;
        box-shadow: 0 0 20px rgba(255, 64, 129, 0.8), inset 0 0 10px rgba(255, 64, 129, 0.3);
      }
      100% {
        border-color: #ff4081;
        box-shadow: 0 0 10px rgba(255, 64, 129, 0.5), inset 0 0 5px rgba(255, 64, 129, 0.1);
      }
    }

    /* Social Media Icons - Circular and Smaller */
    .social-icons {
      position: fixed;
      top: 20px;
      left: calc(20px + 280px);
      display: flex;
      flex-direction: row;
      gap: 10px;
      z-index: 1000;
    }

    .social-icon {
      width: 35px;
      height: 35px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(10px);
      border-radius: 50%;
      border: 2px solid #ff4081;
      color: #ff4081;
      font-size: 16px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 15px rgba(255, 64, 129, 0.4);
      animation: socialGlitter 2.5s infinite;
      text-decoration: none;
    }

    .social-icon:nth-child(1) {
      animation-delay: 0s;
    }

    .social-icon:nth-child(2) {
      animation-delay: 0.3s;
    }

    .social-icon:nth-child(3) {
      animation-delay: 0.6s;
    }

    .social-icon:nth-child(4) {
      animation-delay: 0.9s;
    }

    .social-icon:nth-child(5) {
      animation-delay: 1.2s;
    }

    .social-icon:nth-child(6) {
      animation-delay: 1.5s;
    }

    @keyframes socialGlitter {
      0%, 100% {
        border-color: #ff4081;
        box-shadow: 0 4px 15px rgba(255, 64, 129, 0.4);
      }
      50% {
        border-color: #ff10a0;
        box-shadow: 0 0 20px rgba(255, 64, 129, 0.8), 0 0 30px rgba(255, 64, 129, 0.5);
      }
    }

    .social-icon:hover {
      transform: scale(1.15);
      box-shadow: 0 6px 25px rgba(255, 64, 129, 0.8);
      border-color: #ff10a0;
    }

    /* Hero Section Styles */
    .hero-section {
      background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(255, 64, 129, 0.3)), 
                  url('https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?w=1200&h=400&fit=crop') center/cover no-repeat;
      padding: 80px 40px;
      text-align: center;
      margin: 20px;
      border-radius: 15px;
      box-shadow: 0 8px 32px rgba(255, 64, 129, 0.3);
      animation: slideInDown 0.8s ease;
    }

    .hero-section h1 {
      font-size: 48px;
      font-weight: bold;
      color: #fff;
      margin: 0 0 15px 0;
      text-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
    }

    .hero-section p {
      font-size: 24px;
      color: #ff4081;
      margin: 0;
      font-weight: 300;
      letter-spacing: 2px;
      text-shadow: 0 2px 8px rgba(0, 0, 0, 0.5);
    }

    @keyframes slideInDown {
      from {
        opacity: 0;
        transform: translateY(-30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    main {
      padding: 40px;
      padding-bottom: 120px;
      text-align: center;
      background: linear-gradient(135deg, #ff4081, #ff1493);
      min-height: calc(100vh - 180px);
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
      color: #fff;
    }

    section h2 i {
      color: #fff;
    }

    section p {
      color: #fff;
      font-size: 18px;
      margin-bottom: 20px;
    }

    button {
      background: #000000;
      border: 2px solid #fff;
      padding: 10px 20px;
      margin: 10px;
      color: #fff;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      transition: all 0.3s ease;
    }

    button:hover {
      background: #fff;
      color: #ff4081;
      border-color: #ff4081;
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
  <!-- Search Container and Social Media Icons -->
  <div class="search-container">
    <input type="text" id="search" placeholder="Let's dive in ....">
  </div>

  <div class="social-icons">
    <a href="https://instagram.com/itshunt0" target="_blank" rel="noopener noreferrer" class="social-icon" title="Instagram">
      <i class="fab fa-instagram"></i>
    </a>
    <a href="https://tiktok.com" target="_blank" rel="noopener noreferrer" class="social-icon" title="TikTok">
      <i class="fab fa-tiktok"></i>
    </a>
    <a href="https://wa.me" target="_blank" rel="noopener noreferrer" class="social-icon" title="WhatsApp">
      <i class="fab fa-whatsapp"></i>
    </a>
    <a href="https://linkedin.com" target="_blank" rel="noopener noreferrer" class="social-icon" title="LinkedIn">
      <i class="fab fa-linkedin"></i>
    </a>
    <a href="https://youtube.com" target="_blank" rel="noopener noreferrer" class="social-icon" title="YouTube">
      <i class="fab fa-youtube"></i>
    </a>
    <a href="https://x.com" target="_blank" rel="noopener noreferrer" class="social-icon" title="X">
      <i class="fab fa-x-twitter"></i>
    </a>
  </div>

  <!-- Hero Section -->
  <div class="hero-section">
    <h1>HARMONIX</h1>
    <p>A new way to play....</p>
  </div>

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

  <nav>
    <h1><i class="fas fa-music"></i> Harmonix</h1>
    <ul>
      <li><a href="#" onclick="showPage('home')"><i class="fas fa-home"></i> Home</a></li>
      <li><a href="#" onclick="showPage('you')"><i class="fas fa-user"></i> You</a></li>
      <li><a href="#" onclick="showPage('calendar')"><i class="fas fa-calendar-alt"></i> Event Calendar</a></li>
      <li><a href="#" onclick="showPage('collections')"><i class="fas fa-compact-disc"></i> Collections</a></li>
    </ul>
  </nav>

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
