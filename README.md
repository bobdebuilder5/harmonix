<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Harmonix</title>
  <!-- Font Awesome for Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Nunito&display=swap" rel="stylesheet">

  <style>
    /* ===== GLOBAL STYLES ===== */
    * {
      font-family: 'Nunito', sans-serif;
margin: 0;
padding: 0;
box-sizing: border-box;
      
    }

    /* Body: Pure black background with centered layout */
    body {
      background: #000000;
      color: #fff;
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }

    /* ===== HEADER / NAV BAR ===== */
    /* Top navigation bar - horizontal menu */
    .header {
      background: rgba(0, 0, 0, 0.95);
      backdrop-filter: blur(10px);
      padding: 20px 40px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      box-shadow: 0 4px 20px rgba(255, 155, 195, 0.1);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    /* Logo/Title in header */
    .header-title {
      font-size: 28px;
      font-weight: bold;
      background: linear-gradient(135deg, #ff9bc3, #ffb3d9);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    /* Navigation menu - horizontal list */
    .nav-menu {
      display: flex;
      gap: 30px;
      list-style: none;
    }

    .nav-menu li a {
      color: #fff;
      text-decoration: none;
      font-weight: 500;
      display: flex;
      align-items: center;
      gap: 8px;
      padding: 8px 12px;
      border-radius: 8px;
      transition: all 0.3s ease;
      cursor: pointer;
    }

    .nav-menu li a:hover,
    .nav-menu li a.active {
      color: #ff9bc3;
      background: rgba(255, 155, 195, 0.1);
    }

    /* Search and Social container - right side of header */
    .header-right {
      display: flex;
      align-items: center;
      gap: 20px;
    }

    /* ===== SEARCH CONTAINER ===== */
    .search-container {
      display: flex;
      align-items: center;
      gap: 10px;
      background: rgba(255, 255, 255, 0.1);
      padding: 10px 16px;
      border-radius: 20px;
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 155, 195, 0.3);
      transition: all 0.3s ease;
    }

    .search-container:focus-within {
      border-color: #ff9bc3;
      box-shadow: 0 0 20px rgba(255, 155, 195, 0.3);
    }

    .search-icon {
      color: #ff9bc3;
      font-size: 16px;
    }

    #search {
      background: transparent;
      border: none;
      color: #fff;
      outline: none;
      width: 200px;
      font-size: 14px;
    }

    #search::placeholder {
      color: rgba(255, 255, 255, 0.6);
    }

    /* ===== SOCIAL MEDIA ICONS ===== */
    .social-icons {
      display: flex;
      gap: 8px;
    }

    .social-icon {
      width: 35px;
      height: 35px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: rgba(255, 155, 195, 0.1);
      border: 1.5px solid #ff9bc3;
      border-radius: 50%;
      color: #ff9bc3;
      font-size: 14px;
      cursor: pointer;
      transition: all 0.3s ease;
      text-decoration: none;
    }

    .social-icon:hover {
      transform: scale(1.15);
      background: #ff9bc3;
      color: #000;
      box-shadow: 0 0 20px rgba(255, 155, 195, 0.6);
    }

    /* ===== MAIN CONTENT AREA ===== */
    main {
      flex: 1;
      padding: 60px 40px;
      max-width: 1200px;
      margin: 0 auto;
      width: 100%;
    }

    /* ===== HERO SECTION ===== */
    .hero-section {
      text-align: center;
      margin-bottom: 60px;
      animation: slideInDown 0.8s ease;
    }

    .hero-section h1 {
      font-size: 72px;
      font-weight: bold;
      background: linear-gradient(135deg, #ff9bc3, #ffb3d9);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 15px;
      letter-spacing: 3px;
    }

    .hero-section p {
      font-size: 20px;
      color: rgba(255, 255, 255, 0.8);
      font-weight: 300;
      letter-spacing: 1px;
    }

    /* ===== SECTIONS ===== */
    section {
      display: none;
    }

    section.active {
      display: block;
      animation: fadeIn 0.5s ease;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(10px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes slideInDown {
      from {
        opacity: 0;
        transform: translateY(-20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    section h2 {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
      font-size: 36px;
      margin-bottom: 30px;
      background: linear-gradient(135deg, #ff9bc3, #ffb3d9);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    section p {
      color: rgba(255, 255, 255, 0.7);
      font-size: 16px;
      margin-bottom: 30px;
      text-align: center;
    }

    /* ===== BUTTONS ===== */
    .button-group {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
      margin: 30px 0;
    }

    button {
      background: rgba(255, 155, 195, 0.1);
      border: 2px solid #ff9bc3;
      padding: 12px 24px;
      color: #ff9bc3;
      font-size: 15px;
      cursor: pointer;
      border-radius: 8px;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      transition: all 0.3s ease;
      font-weight: 500;
    }

    button:hover {
      background: #ff9bc3;
      color: #000;
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(255, 155, 195, 0.4);
    }

    button i {
      font-size: 16px;
    }

    button.hidden {
      display: none;
    }

    /* ===== SLIDER STYLES ===== */
    .slider-container {
      margin: 50px 0;
      overflow: hidden;
    }

    .slider-wrapper {
      display: flex;
      gap: 20px;
      overflow-x: auto;
      padding: 20px 0;
      scroll-behavior: smooth;
      /* Hide scrollbar */
      -ms-overflow-style: none;
      scrollbar-width: none;
    }

    .slider-wrapper::-webkit-scrollbar {
      display: none;
    }

    .hexagon-slide {
      flex: 0 0 280px;
      height: 200px;
      position: relative;
      border-radius: 12px;
      overflow: hidden;
      cursor: pointer;
      transition: all 0.3s ease;
      background: linear-gradient(135deg, #1a1a1a, #2a2a2a);
      border: 1px solid rgba(255, 155, 195, 0.2);
    }

    .hexagon-slide > div {
      width: 100%;
      height: 100%;
      background-size: cover;
      background-position: center;
    }

    .hexagon-slide:hover {
      transform: translateY(-8px);
      border-color: #ff9bc3;
      box-shadow: 0 12px 40px rgba(255, 155, 195, 0.4);
    }

    .slide-content {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      background: linear-gradient(to top, rgba(0, 0, 0, 0.95), transparent);
      padding: 20px;
      z-index: 2;
      color: #fff;
    }

    .slide-content h3 {
      margin: 0 0 8px 0;
      font-size: 16px;
      color: #ff9bc3;
    }

    .slide-content p {
      margin: 0;
      font-size: 12px;
      color: rgba(255, 255, 255, 0.8);
    }

    /* ===== SLIDER INDICATORS ===== */
    .slider-indicators {
      display: flex;
      justify-content: center;
      gap: 10px;
      margin-top: 25px;
    }

    .indicator {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: rgba(255, 155, 195, 0.3);
      cursor: pointer;
      transition: all 0.3s ease;
      border: 1px solid rgba(255, 155, 195, 0.5);
    }

    .indicator.active {
      background: #ff9bc3;
      transform: scale(1.3);
    }

    /* ===== RESPONSIVE DESIGN ===== */
    @media (max-width: 768px) {
      .header {
        flex-direction: column;
        gap: 15px;
        padding: 15px 20px;
      }

      .nav-menu {
        gap: 15px;
        flex-wrap: wrap;
        justify-content: center;
      }

      .header-right {
        flex-direction: column;
        gap: 10px;
        width: 100%;
      }

      .search-container {
        width: 100%;
      }

      #search {
        width: 100%;
      }

      .hero-section h1 {
        font-size: 48px;
      }

      main {
        padding: 40px 20px;
      }

      .hexagon-slide {
        flex: 0 0 240px;
        height: 180px;
      }
    }
  </style>
</head>
<body>
  <!-- ===== HEADER / NAVIGATION ===== -->
  <header class="header">
    <div class="header-title">HARMONIX</div>
    
    <ul class="nav-menu">
      <li><a href="#" onclick="showPage('home')" class="nav-link active"><i class="fas fa-home"></i> Home</a></li>
      <li><a href="#" onclick="showPage('you')" class="nav-link"><i class="fas fa-user"></i> You</a></li>
      <li><a href="#" onclick="showPage('calendar')" class="nav-link"><i class="fas fa-calendar-alt"></i> Events</a></li>
      <li><a href="#" onclick="showPage('collections')" class="nav-link"><i class="fas fa-compact-disc"></i> Collections</a></li>
    </ul>

    <div class="header-right">
      <div class="search-container">
        <i class="fas fa-search search-icon"></i>
        <input type="text" id="search" placeholder="Search...">
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
        <a href="https://twitter.com" target="_blank" rel="noopener noreferrer" class="social-icon" title="X">
          <i class="fab fa-twitter"></i>
        </a>
      </div>
    </div>
  </header>

  <!-- ===== MAIN CONTENT ===== -->
  <main>
    <!-- ===== HERO SECTION ===== -->
    <div class="hero-section">
      <h1>HARMONIX</h1>
      <p>A new way to play</p>
    </div>

    <!-- HOME SECTION -->
    <section id="home" class="active">
      <h2><i class="fas fa-home"></i> Home</h2>
      <p>Discover trending tracks and curated playlists.</p>
      
      <div class="button-group">
        <button class="searchable" data-keywords="play sound music" onclick="playSound()"><i class="fas fa-play"></i> Play Sound</button>
        <button class="searchable" data-keywords="stop sound pause" onclick="stopSound()"><i class="fas fa-stop"></i> Stop Sound</button>
      </div>

      <!-- ===== CAROUSEL SLIDER ===== -->
      <div class="slider-container">
        <div class="slider-wrapper" id="sliderWrapper">
          <!-- Slide 1: Summer Vibes -->
          <div class="hexagon-slide">
            <div style="background-image: url('https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?w=500&h=300&fit=crop');"></div>
            <div class="slide-content">
              <h3>🎵 Summer Vibes</h3>
              <p>"Music is the universal language of mankind."</p>
            </div>
          </div>
          <!-- Slide 2: Electric Dreams -->
          <div class="hexagon-slide">
            <div style="background-image: url('https://images.unsplash.com/photo-1470225620780-dba8ba36b745?w=500&h=300&fit=crop');"></div>
            <div class="slide-content">
              <h3> Electric Dreams</h3>
              <p>"Melody is the soul of music."</p>
            </div>
          </div>
          <!-- Slide 3: Jazz Night -->
          <div class="hexagon-slide">
            <div style="background-image: url('https://images.unsplash.com/photo-1459749411175-04bf5292ceea?w=500&h=300&fit=crop');"></div>
            <div class="slide-content">
              <h3> Jazz Night</h3>
              <p>"Without music, life would be a mistake."</p>
            </div>
          </div>
          <!-- Slide 4: Live Sessions -->
          <div class="hexagon-slide">
            <div style="background-image: url('https://images.unsplash.com/photo-1511379938547-c1f69b13d835?w=500&h=300&fit=crop');"></div>
            <div class="slide-content">
              <h3>🎤 Live Sessions</h3>
              <p>"Music gives a soul to the universe."</p>
            </div>
          </div>
          <!-- Slide 5: Chill Beats -->
          <div class="hexagon-slide">
            <div style="background-image: url('https://images.unsplash.com/photo-1487180144351-b8472da7d491?w=500&h=300&fit=crop');"></div>
            <div class="slide-content">
              <h3>Chill Beats</h3>
              <p>"Music washes away from the soul the dust of everyday life."</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Slider indicators -->
      <div class="slider-indicators">
        <div class="indicator active" onclick="goToSlide(0)"></div>
        <div class="indicator" onclick="goToSlide(1)"></div>
        <div class="indicator" onclick="goToSlide(2)"></div>
        <div class="indicator" onclick="goToSlide(3)"></div>
        <div class="indicator" onclick="goToSlide(4)"></div>
      </div>
    </section>

    <!-- YOU SECTION -->
    <section id="you">
      <h2><i class="fas fa-user-circle"></i> You</h2>
      <p>Your personalized music space.</p>
      <div class="button-group">
        <button class="searchable" data-keywords="favorites heart liked"><i class="fas fa-heart"></i> Your Favorites</button>
        <button class="searchable" data-keywords="playlists list"><i class="fas fa-list"></i> Your Playlists</button>
      </div>
    </section>

    <!-- EVENT CALENDAR SECTION -->
    <section id="calendar">
      <h2><i class="fas fa-calendar-alt"></i> Event Calendar</h2>
      <p>Upcoming concerts and events.</p>
      <div class="button-group">
        <button class="searchable" data-keywords="featured events star"><i class="fas fa-star"></i> Featured Events</button>
        <button class="searchable" data-keywords="near location dot"><i class="fas fa-location-dot"></i> Near You</button>
      </div>
    </section>

    <!-- COLLECTIONS SECTION -->
    <section id="collections">
      <h2><i class="fas fa-compact-disc"></i> Collections</h2>
      <p>Browse curated collections of tracks.</p>
      <div class="button-group">
        <button class="searchable" data-keywords="trending fire hot"><i class="fas fa-fire"></i> Trending</button>
        <button class="searchable" data-keywords="new releases music"><i class="fas fa-music"></i> New Releases</button>
      </div>
    </section>
  </main>

  <!-- ===== EXTERNAL LIBRARIES ===== -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/howler/2.2.3/howler.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/tone/14.8.39/Tone.min.js"></script>

  <script>
    // ===== PAGE NAVIGATION =====
    function showPage(pageId) {
      document.querySelectorAll('main section').forEach(sec => sec.classList.remove('active'));
      document.getElementById(pageId).classList.add('active');
      
      document.querySelectorAll('.nav-link').forEach(link => link.classList.remove('active'));
      event.target.closest('.nav-link').classList.add('active');
      
      document.getElementById('search').value = '';
      filterButtons('');
    }

    // ===== SEARCH & FILTER =====
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

    // ===== AUDIO PLAYBACK =====
    const sound = new Howl({
      src: ['https://actions.google.com/sounds/v1/cartoon/clang_and_wobble.ogg']
    });

    function playSound() {
      sound.play();
    }

    function stopSound() {
      sound.stop();
    }

    // ===== TONE.JS SYNTHESIS =====
    document.addEventListener('keydown', async (e) => {
      await Tone.start();
      const synth = new Tone.Synth().toDestination();
      synth.triggerAttackRelease("C4", "8n");
    });

    // ===== SLIDER FUNCTIONALITY =====
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
      const active = slides[currentSlide];
      
      if (active) {
        const wrapperRect = sliderWrapper.getBoundingClientRect();
        const activeRect = active.getBoundingClientRect();
        const offset = active.offsetLeft - (wrapperRect.width/2 - activeRect.width/2);
        sliderWrapper.scrollTo({ left: offset, behavior: 'smooth' });
      }

      document.querySelectorAll('.indicator').forEach((ind, idx) => {
        ind.classList.toggle('active', idx === currentSlide);
      });
    }

    // Auto-rotate every 30 seconds
    setInterval(nextSlide, 30000);
  </script>
</body>
</html>
