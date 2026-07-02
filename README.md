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
      width: 80%;
      left: 10%;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #000000;
      padding: 15px 30px;
      box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.5);
      z-index: 999;
    }

    nav h1 {
      display: none;
    }

    nav ul {
      list-style: none;
      display: flex;
      gap: 20px;
      margin: 0;
      padding: 0;
      width: 100%;
      justify-content: center;
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
      color: #ff9bc3;
    }

    /* Search Container - Centered with Icon and Input */
    .search-container {
      position: fixed;
      top: 20px;
      left: 25%;
      right: 25%;
      display: flex;
      align-items: center;
      gap: 12px;
      z-index: 1000;
      width: 50%;
      transform: translateX(0);
    }

    .search-icon {
      color: #ff9bc3;
      font-size: 18px;
      flex-shrink: 0;
      pointer-events: none;
    }

    #search {
      width: 100%;
      padding: 12px 16px;
      border-radius: 20px;
      border: 2px solid transparent;
      outline: none;
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(10px);
      color: #fff;
      font-size: 14px;
      transition: all 0.4s ease;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
      animation: neonGlow 2s infinite;
      position: relative;
    }

    #search::placeholder {
      color: rgba(255, 255, 255, 0.6);
    }

    #search:focus {
      background: rgba(255, 255, 255, 0.15);
      box-shadow: 0 0 20px rgba(255, 155, 195, 0.6), inset 0 0 10px rgba(255, 155, 195, 0.2);
    }

    /* Neon Glimmering and Glittering Animation */
    @keyframes neonGlow {
      0% {
        border-color: #ff9bc3;
        box-shadow: 0 0 10px rgba(255, 155, 195, 0.5), inset 0 0 5px rgba(255, 155, 195, 0.1);
      }
      50% {
        border-color: #ffb3d9;
        box-shadow: 0 0 20px rgba(255, 155, 195, 0.8), inset 0 0 10px rgba(255, 155, 195, 0.3);
      }
      100% {
        border-color: #ff9bc3;
        box-shadow: 0 0 10px rgba(255, 155, 195, 0.5), inset 0 0 5px rgba(255, 155, 195, 0.1);
      }
    }

    /* Social Media Icons - Circular and Smaller */
    .social-icons {
      position: fixed;
      top: 20px;
      right: 20px;
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
      border: 2px solid #ff9bc3;
      color: #ff9bc3;
      font-size: 16px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 15px rgba(255, 155, 195, 0.4);
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
        border-color: #ff9bc3;
        box-shadow: 0 4px 15px rgba(255, 155, 195, 0.4);
      }
      50% {
        border-color: #ffb3d9;
        box-shadow: 0 0 20px rgba(255, 155, 195, 0.8), 0 0 30px rgba(255, 155, 195, 0.5);
      }
    }

    .social-icon:hover {
      transform: scale(1.15);
      box-shadow: 0 6px 25px rgba(255, 155, 195, 0.8);
      border-color: #ffb3d9;
    }

    /* Hero Section Styles */
    .hero-section {
      background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(255, 155, 195, 0.2)), 
                  url('https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?w=1200&h=400&fit=crop') center/cover no-repeat;
      padding: 80px 40px;
      text-align: center;
      margin: 20px;
      border-radius: 15px;
      box-shadow: 0 8px 32px rgba(255, 155, 195, 0.2);
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
      color: #ff9bc3;
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
      background: linear-gradient(135deg, #ff9bc3, #ffb3d9);
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
      color: #ff9bc3;
      border-color: #ff9bc3;
    }

    button.hidden {
      display: none;
    }

    button i {
      font-size: 18px;
    }

    /* Hexagonal Slider Styles */
    .slider-container {
      margin: 60px 20px;
      overflow: hidden;
      perspective: 1200px;
    }

    .slider-wrapper {
      display: flex;
      gap: 20px;
      transform-style: preserve-3d;
      animation: autoScroll 10s infinite linear;
    }

    .hexagon-slide {
      flex: 0 0 calc(40% - 16px);
      min-width: calc(40% - 16px);
      height: 300px;
      position: relative;
      border-radius: 20px;
      overflow: hidden;
      transform: skewX(-15deg);
      box-shadow: 0 8px 32px rgba(255, 155, 195, 0.3);
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .hexagon-slide:hover {
      transform: skewX(-15deg) scale(1.05);
      box-shadow: 0 12px 48px rgba(255, 155, 195, 0.6);
    }

    .hexagon-slide > div {
      width: 100%;
      height: 100%;
      background-size: cover;
      background-position: center;
    }

    .slide-content {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      background: linear-gradient(to top, rgba(0, 0, 0, 0.9), transparent);
      padding: 30px 20px;
      z-index: 2;
      transform: skewX(15deg);
      color: #fff;
      text-align: left;
    }

    .slide-content h3 {
      margin: 0 0 10px 0;
      font-size: 20px;
      color: #ff9bc3;
    }

    .slide-content p {
      margin: 0;
      font-size: 14px;
      color: #fff;
    }

    @keyframes autoScroll {
      0% {
        transform: translateX(0);
      }
      100% {
        transform: translateX(-calc(40% + 20px));
      }
    }

    .slider-wrapper:hover {
      animation-play-state: paused;
    }

    /* Slider Indicators */
    .slider-indicators {
      display: flex;
      justify-content: center;
      gap: 10px;
      margin-top: 20px;
    }

    .indicator {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      background: rgba(255, 155, 195, 0.5);
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .indicator.active {
      background: #ff9bc3;
      transform: scale(1.3);
    }
  </style>
</head>
<body>
  <!-- Search Container and Social Media Icons -->
  <div class="search-container">
    <i class="fas fa-search search-icon"></i>
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

      <!-- Hexagonal Slider -->
      <div class="slider-container">
        <div class="slider-wrapper" id="sliderWrapper">
          <div class="hexagon-slide">
            <div style="background-image: url('https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?w=500&h=300&fit=crop');"></div>
            <div class="slide-content">
              <h3>🎵 Summer Vibes</h3>
              <p>"Music is the universal language of mankind."</p>
            </div>
          </div>
          <div class="hexagon-slide">
            <div style="background-image: url('https://images.unsplash.com/photo-1470225620780-dba8ba36b745?w=500&h=300&fit=crop');"></div>
            <div class="slide-content">
              <h3>🎸 Electric Dreams</h3>
              <p>"Melody is the soul of music."</p>
            </div>
          </div>
          <div class="hexagon-slide">
            <div style="background-image: url('https://images.unsplash.com/photo-1459749411175-04bf5292ceea?w=500&h=300&fit=crop');"></div>
            <div class="slide-content">
              <h3>🎹 Jazz Night</h3>
              <p>"Without music, life would be a mistake."</p>
            </div>
          </div>
          <div class="hexagon-slide">
            <div style="background-image: url('https://images.unsplash.com/photo-1511379938547-c1f69b13d835?w=500&h=300&fit=crop');"></div>
            <div class="slide-content">
              <h3>🎤 Live Sessions</h3>
              <p>"Music gives a soul to the universe."</p>
            </div>
          </div>
          <div class="hexagon-slide">
            <div style="background-image: url('https://images.unsplash.com/photo-1487180144351-b8472da7d491?w=500&h=300&fit=crop');"></div>
            <div class="slide-content">
              <h3>🎧 Chill Beats</h3>
              <p>"Music washes away from the soul the dust of everyday life."</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Slider Indicators -->
      <div class="slider-indicators">
        <div class="indicator active" onclick="goToSlide(0)"></div>
        <div class="indicator" onclick="goToSlide(1)"></div>
        <div class="indicator" onclick="goToSlide(2)"></div>
        <div class="indicator" onclick="goToSlide(3)"></div>
        <div class="indicator" onclick="goToSlide(4)"></div>
      </div>
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

    // Slider functionality
    let currentSlide = 0;
    const slides = document.querySelectorAll('.hexagon-slide');
    const totalSlides = slides.length;

    function goToSlide(n) {
      currentSlide = n;
      updateSlider();
    }

    function nextSlide() {
      currentSlide = (currentSlide + 1) % totalSlides;
      updateSlider();
    }

    function updateSlider() {
      const sliderWrapper = document.getElementById('sliderWrapper');
      const offset = currentSlide * (40 + 2.4);
      sliderWrapper.style.animation = 'none';
      setTimeout(() => {
        sliderWrapper.style.transform = `translateX(-${offset}%)`;
      }, 10);
      
      // Update indicators
      document.querySelectorAll('.indicator').forEach((ind, idx) => {
        ind.classList.toggle('active', idx === currentSlide);
      });

      // Reset animation
      setTimeout(() => {
        sliderWrapper.style.animation = 'autoScroll 10s infinite linear';
      }, 300);
    }

    // Auto rotate slides every 10 seconds
    setInterval(nextSlide, 10000);
  </script>
</body>
</html>