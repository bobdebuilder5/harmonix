<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Harmonix</title>
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
    }

    nav ul li a:hover {
      color: #ff4081;
    }

    .search-container {
      position: relative;
    }

    #search {
      width: 10%;
      transition: width 0.4s ease;
      padding: 8px;
      border-radius: 20px;
      border: none;
      outline: none;
    }

    #search:focus {
      width: 45%;
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

    button {
      background: #ff4081;
      border: none;
      padding: 10px 20px;
      margin: 10px;
      color: white;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
    }

    button:hover {
      background: #f50057;
    }
  </style>
</head>
<body>
  <nav>
    <h1>🎶 Harmonix</h1>
    <ul>
      <li><a href="#" onclick="showPage('home')">Home</a></li>
      <li><a href="#" onclick="showPage('you')">You</a></li>
      <li><a href="#" onclick="showPage('calendar')">Event Calendar</a></li>
      <li><a href="#" onclick="showPage('collections')">Collections</a></li>
    </ul>
    <div class="search-container">
      <input type="text" id="search" placeholder="Let's dive in ....">
    </div>
  </nav>

  <main>
    <section id="home" class="active">
      <h2>Home</h2>
      <p>Discover trending tracks and curated playlists.</p>
      <button onclick="playSound()">Play Sound</button>
      <button onclick="stopSound()">Stop Sound</button>
    </section>

    <section id="you">
      <h2>You</h2>
      <p>Your personalized music space.</p>
    </section>

    <section id="calendar">
      <h2>Event Calendar</h2>
      <p>Upcoming concerts and events.</p>
    </section>

    <section id="collections">
      <h2>Collections</h2>
      <p>Browse curated collections of tracks.</p>
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
