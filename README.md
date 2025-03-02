<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover" />
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />
  <title>Raise A Glass LLC - Event Bartending & Casino</title>
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet" />
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <!-- jQuery UI CSS for datepicker and draggable -->
  <link rel="stylesheet" href="https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css" />
  <style>
    /* RESET & TYPOGRAPHY */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: 'Montserrat', sans-serif;
      background: linear-gradient(to bottom right, #ffdde1, #ee9ca7);
      background-size: cover;
      background-attachment: fixed;
      color: #333;
      position: relative;
      overflow-x: hidden;
      -webkit-font-smoothing: antialiased;
      -webkit-overflow-scrolling: touch;
    }
    h1 {
      font-family: 'Dancing Script', cursive;
      font-size: 3.5em;
      color: #fff7e6;
      text-align: center;
      margin-bottom: 10px;
      text-shadow: 3px 3px 8px rgba(0,0,0,0.5);
      position: relative;
    }
    h2 { color: #3d405b; font-size: 2.5em; margin-bottom: 20px; text-align: center; }
    
    /* FUN TICKER (Top Bar) */
    #fun-fact-box {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      background-color: rgba(224,122,95,0.95);
      color: #fff;
      font-size: 1rem;
      padding: 10px;
      text-align: center;
      z-index: 10000;
      transition: transform 0.3s ease;
    }
    
    /* BUBBLES & FIZZ */
    .bubbles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 5;
      overflow: hidden;
    }
    .bubble {
      position: absolute;
      background: rgba(255,255,255,0.8);
      border-radius: 50%;
      opacity: 0;
      animation: riseAndFizz 6s infinite ease-out;
    }
    .bubble.suds {
      background: radial-gradient(circle, rgba(255,255,255,0.9), rgba(255,255,255,0));
      animation: sudsPop 4s infinite ease-out;
    }
    @keyframes riseAndFizz {
      0% { transform: translateY(100vh) scale(0.3); opacity: 0.8; }
      50% { transform: translateY(50vh) scale(0.8) translateX(10px); opacity: 1; }
      100% { transform: translateY(-20vh) scale(1); opacity: 0; }
    }
    @keyframes sudsPop {
      0% { transform: translateY(100vh) scale(0.5); opacity: 0.9; }
      70% { transform: translateY(30vh) scale(1.2); opacity: 1; }
      100% { transform: translateY(0) scale(0.8); opacity: 0; }
    }
    
    /* CUSTOM CHAMPAGNE GLASSES */
    .champagne-glasses {
      position: absolute;
      top: 10px;
      right: 20px;
      width: 50px;
      height: 50px;
      z-index: 10;
      animation: clinkAndFizz 3s infinite ease-in-out;
    }
    @keyframes clinkAndFizz {
      0% { transform: translateX(0) rotate(0deg); }
      25% { transform: translateX(-10px) rotate(10deg); }
      50% { transform: translateX(0) rotate(0deg); }
      75% { transform: translateX(5px) rotate(-5deg); }
      100% { transform: translateX(0) rotate(0deg); }
    }
    
    /* HEADER */
    .header {
      background: #3d405b;
      color: #f4f1de;
      padding: 60px 0;
      border-bottom: 4px solid #e07a5f;
      text-shadow: 2px 2px 5px #333;
      position: relative;
    }
    .header .tagline { text-align: center; font-size: 1.8em; color: #f2cc8f; }
    
    /* NAVIGATION */
    .main-nav {
      background-color: #e07a5f;
      text-align: center;
      padding: 15px 0;
      margin-top: 20px;
      z-index: 1000;
      position: sticky;
      top: 0;
      box-shadow: 0 2px 10px rgba(0,0,0,0.2);
    }
    .main-nav a {
      color: #fff;
      text-decoration: none;
      margin: 0 20px;
      font-size: 1.2em;
      transition: color 0.3s, transform 0.2s;
      display: inline-block;
    }
    .main-nav a:hover { color: #ffddd2; transform: scale(1.1); }
    
    /* Glamorous Rae's Casino Link */
    .casino-link {
      position: relative;
      font-family: 'Dancing Script', cursive;
      font-size: 1.4em;
      color: #ffd700; /* Gold */
      text-shadow: 0 0 5px #ffd700, 0 0 10px #ff4500;
      padding: 5px 15px;
      border: 2px solid #ffd700;
      border-radius: 8px;
      animation: casinoGlow 2s infinite alternate;
    }
    @keyframes casinoGlow {
      0% { box-shadow: 0 0 5px #ffd700; }
      100% { box-shadow: 0 0 15px #ff4500; }
    }
    
    /* Casino Dropdown */
    .casino-dropdown {
      position: relative;
      display: inline-block;
    }
    .casino-dropdown-content {
      display: none;
      position: absolute;
      background-color: #3d405b;
      min-width: 160px;
      box-shadow: 0 8px 16px rgba(0,0,0,0.2);
      z-index: 1;
      border-radius: 5px;
      top: 100%;
      left: 50%;
      transform: translateX(-50%);
    }
    .casino-dropdown-content a {
      color: #fff;
      padding: 12px 16px;
      text-decoration: none;
      display: block;
      font-family: 'Montserrat', sans-serif;
      font-size: 1em;
      margin: 0;
    }
    .casino-dropdown-content a:hover {
      background-color: #e07a5f;
      color: #ffd700;
    }
    .casino-dropdown:hover .casino-dropdown-content { display: block; }
    
    /* COLUMNS (Old Mansion Vibe) */
    .columns {
      position: absolute;
      height: 100%;
      width: 10%;
      background: rgba(255,223,211,0.8);
      top: 0;
      z-index: -1;
      border-radius: 0 25px 25px 0;
    }
    .left-column {
      left: 0;
      border-right: 4px solid #3d405b;
      box-shadow: 10px 0 15px -5px #6b4226;
    }
    .right-column {
      right: 0;
      border-left: 4px solid #3d405b;
      box-shadow: -10px 0 15px -5px #6b4226;
      border-radius: 25px 0 0 25px;
    }
    
    /* SECTIONS */
    section {
      padding: 100px 0;
      text-align: center;
      background: rgba(255,245,238,0.95);
      border: 4px solid #e07a5f;
      margin: 40px 0;
      box-shadow: 8px 8px 20px rgba(0,0,0,0.3);
      border-radius: 25px;
      position: relative;
    }
    .container { width: 80%; margin: 0 auto; max-width: 1200px; }
    ul { list-style-type: none; margin: 40px 0; padding: 0; }
    ul li {
      font-size: 1.4em;
      margin-bottom: 20px;
      padding: 20px;
      background: rgba(255,255,255,0.9);
      border-radius: 15px;
      box-shadow: 4px 4px 15px rgba(0,0,0,0.2);
      transition: transform 0.3s;
    }
    ul li:hover { transform: translateY(-5px); }
    
    /* BUTTONS WITH FIZZ */
    .btn {
      display: inline-block;
      background: linear-gradient(to right, #e07a5f, #3d405b);
      color: #fff;
      padding: 15px 30px;
      text-decoration: none;
      margin: 10px;
      border-radius: 12px;
      box-shadow: 5px 5px 15px rgba(0,0,0,0.3);
      transition: background 0.3s, box-shadow 0.3s, transform 0.2s;
      font-size: 1.2em;
      touch-action: manipulation;
      position: relative;
      overflow: hidden;
    }
    .btn:hover {
      background: linear-gradient(to right, #3d405b, #e07a5f);
      box-shadow: 7px 7px 20px rgba(0,0,0,0.4);
      transform: scale(1.05);
    }
    .btn::after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background: rgba(255,255,255,0.5);
      border-radius: 50%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      animation: fizzBurst 1s infinite;
      opacity: 0;
    }
    .btn:hover::after { animation-play-state: running; opacity: 1; }
    @keyframes fizzBurst {
      0% { transform: translate(-50%, -50%) scale(0); opacity: 1; }
      100% { transform: translate(-50%, -50%) scale(2); opacity: 0; }
    }
    
    /* FOOTER */
    .footer {
      background-color: #3d405b;
      color: #ffddd2;
      padding: 40px 0;
      text-align: center;
      font-size: 1.1em;
      border-top: 4px solid #81b29a;
      box-shadow: 0 -4px 8px rgba(0,0,0,0.3);
    }
    .footer a {
      color: #ffddd2;
      text-decoration: none;
      margin: 0 10px;
      font-size: 1.3em;
    }
    .footer a:hover {
      text-decoration: underline;
      color: #ffffff;
    }
    
    /* INFO SECTIONS */
    .info-section {
      padding: 80px 0;
      background: rgba(255,245,238,0.95);
      border: 4px solid #e07a5f;
      margin: 40px 0;
      box-shadow: 8px 8px 20px rgba(0,0,0,0.3);
      border-radius: 25px;
    }
    .info-section h2 { margin-bottom: 20px; }
    .info-form {
      max-width: 600px;
      margin: 0 auto;
      text-align: left;
    }
    .info-form label {
      font-size: 1em;
      display: block;
      margin-bottom: 5px;
      color: #3d405b;
    }
    .info-form input,
    .info-form select,
    .info-form textarea {
      width: 100%;
      padding: 12px;
      margin-bottom: 15px;
      border-radius: 10px;
      border: 1px solid #ccc;
      font-size: 1em;
      font-family: 'Montserrat', sans-serif;
      transition: border-color 0.3s;
    }
    .info-form input:focus,
    .info-form select:focus,
    .info-form textarea:focus {
      border-color: #e07a5f;
      outline: none;
    }
    .info-form button {
      display: block;
      width: 100%;
      background: linear-gradient(to right, #e07a5f, #3d405b);
      border: none;
      color: #fff;
      padding: 15px;
      font-size: 1.2em;
      border-radius: 12px;
      cursor: pointer;
      transition: background 0.3s, transform 0.2s;
    }
    .info-form button:hover {
      background: linear-gradient(to right, #3d405b, #e07a5f);
      transform: scale(1.02);
    }
    #quoteResult {
      font-size: 1.5em;
      text-align: center;
      color: #3d405b;
      margin-top: 20px;
    }
    
    /* ABOUT SECTION */
    .about-section {
      padding: 80px 0;
      background: rgba(255,245,238,0.98);
      border: 4px solid #e07a5f;
      margin: 40px 0;
      box-shadow: 8px 8px 20px rgba(0,0,0,0.3);
      border-radius: 25px;
    }
    .about-section p {
      font-size: 1.3em;
      max-width: 700px;
      margin: 0 auto;
      line-height: 1.6;
      text-align: center;
      color: #3d405b;
    }
    
    /* RESPONSIVE DESIGN */
    @media (max-width: 768px) {
      .container { width: 90%; }
      .main-nav { padding: 10px 0; }
      .main-nav a { margin: 8px; font-size: 1em; display: block; }
      .casino-link { font-size: 1.2em; padding: 3px 10px; }
      .casino-dropdown-content { position: static; transform: none; width: 100%; }
      .columns { display: none; }
      .btn { padding: 12px 25px; font-size: 1em; }
      .booking-calendar { flex-direction: column; }
      .booking-calendar > div { width: 100%; margin-bottom: 20px; }
      h1 { font-size: 2.5em; }
      h2 { font-size: 2em; }
      .header { padding: 40px 0; }
      .info-form input,
      .info-form select,
      .info-form textarea { font-size: 1em; padding: 10px; }
      .champagne-glasses { width: 40px; height: 40px; }
    }
    @media only screen and (max-width: 414px) and (-webkit-min-device-pixel-ratio: 2) {
      body { padding-top: env(safe-area-inset-top); padding-bottom: env(safe-area-inset-bottom); }
      .main-nav { padding: 8px 0; }
      .main-nav a { font-size: 0.9em; margin: 6px; }
      .casino-link { font-size: 1.1em; }
      .btn { padding: 10px 20px; font-size: 0.9em; }
      #fun-fact-box { font-size: 0.85em; padding: 8px; }
      .champagne-glasses { width: 30px; height: 30px; right: 10px; }
    }
    
    /* Booking & Calendar Combined */
    .booking-calendar {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      gap: 20px;
    }
    .booking-calendar .booking-form { flex: 1; }
    .booking-calendar .calendar-container { flex: 1; max-width: 350px; }
    .availability-status { margin-top: 10px; font-size: 1.1em; color: #3d405b; }
    
    /* Sticky Book Raeanne Button */
    .sticky-book-btn {
      position: fixed;
      bottom: 20px;
      left: 20px;
      background: #e07a5f;
      color: #fff;
      padding: 12px 25px;
      border-radius: 50px;
      text-decoration: none;
      font-size: 1.1em;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
      z-index: 10001;
      transition: transform 0.3s;
    }
    .sticky-book-btn:hover { transform: scale(1.1); background: #3d405b; }
    
    /* Floating Buttons for Pop-Ups */
    .floating-btn {
      position: fixed;
      bottom: 20px;
      margin: 5px;
      background: #3d405b;
      color: #fff;
      border: none;
      padding: 10px 15px;
      border-radius: 8px;
      cursor: pointer;
      z-index: 10001;
      box-shadow: 2px 2px 8px rgba(0,0,0,0.4);
      font-size: 1em;
      transition: background 0.3s, transform 0.2s;
    }
    .floating-btn:hover { background: #e07a5f; transform: scale(1.05); }
    #openQuotePopup { right: 20px; padding: 12px 20px; font-size: 1.1em; }
    #openSlotMachine { right: 150px; }
    #openBlackjack { right: 260px; }
    #openRocket { right: 370px; }
    
    /* Pop-Up Windows */
    .popup {
      position: fixed;
      top: 50px;
      left: 50px;
      background: #fff;
      border: 2px solid #3d405b;
      border-radius: 10px;
      z-index: 10000;
      box-shadow: 5px 5px 20px rgba(0,0,0,0.5);
      max-width: 90%;
    }
    .popup-header {
      background: #3d405b;
      color: #fff;
      padding: 8px;
      cursor: move;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-top-left-radius: 8px;
      border-top-right-radius: 8px;
    }
    .popup-header .popup-title { font-weight: bold; }
    .popup-header button {
      background: transparent;
      border: none;
      color: #fff;
      font-size: 1em;
      cursor: pointer;
      margin-left: 5px;
    }
    .popup-content { padding: 15px; }
    .popup .hidden { display: none; }
    
    /* Slot Machine Popup */
    #slotMachinePopup {
      width: 400px;
      background: #e8f8f5;
      border-color: #16a085;
    }
    #slotDisplay {
      display: flex;
      justify-content: center;
      gap: 20px;
      font-size: 3em;
      margin: 20px 0;
    }
    .slot-reel {
      width: 60px;
      height: 60px;
      text-align: center;
      line-height: 60px;
      background: rgba(255,255,255,0.8);
      border-radius: 8px;
      overflow: hidden;
    }
    .slot-reel.spinning { animation: spinReel 0.5s linear infinite; }
    @keyframes spinReel {
      0% { transform: translateY(-100%); }
      100% { transform: translateY(100%); }
    }
    #slotBetInput {
      margin: 10px 0;
      padding: 8px;
      font-size: 1em;
      border-radius: 5px;
      width: 100px;
    }
    
    /* Blackjack Popup */
    #blackjackPopup {
      width: 500px;
      background: #fef9e7;
      border-color: #d4ac0d;
    }
    #blackjackHands {
      display: flex;
      justify-content: space-between;
      margin: 20px 0;
    }
    .hand {
      width: 45%;
      padding: 10px;
      background: rgba(255,255,255,0.8);
      border-radius: 8px;
    }
    #blackjackResult { margin-top: 10px; font-weight: bold; }
    
    /* Rocket Game Popup */
    #rocketPopup {
      width: 400px;
      background: #e8f8f5;
      border-color: #16a085;
    }
    #rocketDisplay {
      font-size: 2em;
      text-align: center;
      margin: 20px 0;
      color: #3d405b;
    }
    #rocketMultiplier {
      font-size: 3em;
      color: #e07a5f;
    }
    #rocketResult { margin-top: 10px; font-weight: bold; }
    
    /* Shared Casino Styles */
    .casino-btn {
      padding: 8px 15px;
      margin: 5px;
      background: #16a085;
      border: none;
      color: #fff;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.3s;
    }
    .casino-btn:hover { background: #e07a5f; }
    .casino-input {
      padding: 8px;
      margin: 5px;
      border-radius: 5px;
      font-size: 1em;
    }
  </style>
</head>
<body>
  <!-- Fun Fact Ticker -->
  <div id="fun-fact-box">Did you know? Loading fun facts...</div>
  
  <!-- Bubbles & Fizz -->
  <div class="bubbles">
    <div class="bubble" style="left: 5%; width: 20px; height: 20px; animation-delay: 0s;"></div>
    <div class="bubble suds" style="left: 15%; width: 30px; height: 30px; animation-delay: 1s;"></div>
    <div class="bubble" style="left: 25%; width: 25px; height: 25px; animation-delay: 2s;"></div>
    <div class="bubble suds" style="left: 35%; width: 35px; height: 35px; animation-delay: 3s;"></div>
    <div class="bubble" style="left: 45%; width: 15px; height: 15px; animation-delay: 4s;"></div>
    <div class="bubble suds" style="left: 55%; width: 40px; height: 40px; animation-delay: 5s;"></div>
    <div class="bubble" style="left: 65%; width: 20px; height: 20px; animation-delay: 6s;"></div>
    <div class="bubble suds" style="left: 75%; width: 30px; height: 30px; animation-delay: 7s;"></div>
    <div class="bubble" style="left: 85%; width: 25px; height: 25px; animation-delay: 8s;"></div>
    <div class="bubble suds" style="left: 95%; width: 35px; height: 35px; animation-delay: 9s;"></div>
  </div>
  
  <!-- HEADER -->
  <header class="header" id="home">
    <div class="container">
      <h1>Raise A Glass LLC 
        <svg class="champagne-glasses" viewBox="0 0 50 50" fill="none" stroke="#f4f1de" stroke-width="2">
          <path d="M15 10 L15 30 Q15 35 20 35 L25 35" />
          <path d="M35 10 L35 30 Q35 35 30 35 L25 35" />
          <path d="M25 35 L25 45" />
          <circle cx="25" cy="45" r="5" />
        </svg>
      </h1>
      <p class="tagline">Mobile Bartending Services & Casino Fun</p>
    </div>
  </header>
  
  <!-- NAVIGATION -->
  <nav class="main-nav">
    <a href="#home">Home</a>
    <a href="#about">About Raeanne</a>
    <a href="#services">Services</a>
    <a href="#packages">Packages</a>
    <a href="#booking">Book Your Event</a>
    <a href="#quote">Quote Generator</a>
    <div class="casino-dropdown">
      <a href="#" class="casino-link">Rae's Casino</a>
      <div class="casino-dropdown-content">
        <a href="#slots" id="slotNavLink">Slots</a>
        <a href="#blackjack" id="blackjackNavLink">Blackjack</a>
        <a href="#rocket" id="rocketNavLink">Rocket Game</a>
      </div>
    </div>
    <a href="#contact">Contact Us</a>
  </nav>
  
  <!-- COLUMNS (Old Mansion Vibe) -->
  <div class="columns left-column"></div>
  <div class="columns right-column"></div>
  
  <!-- MAIN CONTENT -->
  <main>
    <!-- ABOUT SECTION -->
    <section class="about-section" id="about">
      <div class="container">
        <h2>About Raeanne 
          <svg class="champagne-glasses" style="width: 40px; height: 40px;" viewBox="0 0 50 50" fill="none" stroke="#3d405b" stroke-width="2">
            <path d="M15 10 L15 30 Q15 35 20 35 L25 35" />
            <path d="M35 10 L35 30 Q35 35 30 35 L25 35" />
            <path d="M25 35 L25 45" />
            <circle cx="25" cy="45" r="5" />
          </svg>
        </h2>
        <p>
          Hi, I'm Raeanne! With over 7 years of bartending experience, I blend creativity and passion to bring unforgettable experiences to every event. I love turning gatherings into celebrations—cheers to great times and even greater drinks!
        </p>
      </div>
    </section>
    
    <!-- SERVICES SECTION -->
    <section class="services" id="services">
      <div class="container">
        <h2>Our Services</h2>
        <ul>
          <li><strong><i class="fas fa-user-tie"></i> Professional Bartending Staff:</strong> Our trained bartenders ensure your event is unforgettable.</li>
          <li><strong><i class="fas fa-cocktail"></i> Signature Cocktails & Specialty Menus:</strong> Crafted with care for a unique experience.</li>
          <li><strong><i class="fas fa-coffee"></i> Hot Coffee & Tea Bar:</strong> Cozy drinks to keep your guests warm and happy.</li>
        </ul>
      </div>
    </section>
    
    <!-- PACKAGES SECTION -->
    <section class="packages" id="packages">
      <div class="container">
        <h2>Our Packages</h2>
        <ul>
          <li><strong><i class="fas fa-user-tie"></i> Bartender Only:</strong> You provide everything (bar, alcohol, ice, etc.). Raeanne bartends for up to 100 guests. Call for pricing.</li>
          <li><strong><i class="fas fa-glass-whiskey"></i> Essentials Package:</strong> We supply cups, straws, mixers, garnishes, ice, and a display. You provide the alcohol. Call for pricing.</li>
          <li><strong><i class="fas fa-cocktail"></i> Ultimate Package:</strong> Includes the Essentials Package plus unlimited water, lemonade, iced tea, and a coffee & tea bar. Call for pricing.</li>
          <li><strong><i class="fas fa-wine-glass-alt"></i> Farmhouse Experience Package:</strong> Everything in the Ultimate Package plus our stunning old farmhouse wood bar. We bring the bar to your event for a rustic yet elegant experience. Call for pricing.</li>
          <li><strong><i class="fas fa-users"></i> Additional Bartender:</strong> For events over 100 guests, an additional bartender will be provided. Alcohol is supplied by the client. Call for pricing.</li>
        </ul>
      </div>
    </section>
    
    <!-- BOOKING & CALENDAR COMBINED SECTION -->
    <section class="info-section" id="booking">
      <div class="container">
        <h2>Book Your Event</h2>
        <div class="booking-calendar">
          <div class="booking-form">
            <form class="info-form" id="bookingForm" onsubmit="submitBookingForm(); return false;">
              <label for="name">Your Name</label>
              <input type="text" name="name" id="name" placeholder="Your awesome name" required>
              <label for="email">Your Email</label>
              <input type="email" name="email" id="email" placeholder="you@example.com" required>
              <label for="phone">Your Phone Number</label>
              <input type="tel" name="phone" id="phone" placeholder="(123) 456-7890" required>
              <label for="address">Your Address</label>
              <input type="text" name="address" id="address" placeholder="Street, City, ZIP">
              <label for="eventDate">Event Date</label>
              <input type="text" name="eventDate" id="eventDate" placeholder="MM/DD/YYYY" required>
              <label for="headcount">Guest Count</label>
              <input type="number" name="headcount" id="headcount" placeholder="How many?" required>
              <label for="eventType">Event Type</label>
              <select name="eventType" id="eventType" required>
                <option value="backyard">Backyard Party</option>
                <option value="wedding">Wedding</option>
                <option value="other">Other</option>
              </select>
              <label for="location">Event Location</label>
              <input type="text" name="location" id="location" placeholder="Where's the party?" required>
              <label for="barService">Need a mobile bar?</label>
              <select name="barService" id="barService" required>
                <option value="yes">Yes, please!</option>
                <option value="no">No, thanks!</option>
              </select>
              <label for="comments">Additional Party Details</label>
              <textarea name="comments" id="comments" rows="3" placeholder="Tell us a bit about your celebration"></textarea>
              <button type="submit">Submit Booking Request</button>
            </form>
          </div>
          <div class="calendar-container">
            <h3>Choose Your Date</h3>
            <div id="datepicker" style="margin: 0 auto;"></div>
            <div class="availability-status" id="availabilityStatus">Check Raeanne's availability!</div>
          </div>
        </div>
      </div>
    </section>
    
    <!-- QUOTE GENERATOR SECTION -->
    <section class="info-section" id="quote">
      <div class="container">
        <h2>Quote Generator</h2>
        <form class="info-form" id="quoteForm" onsubmit="submitQuoteForm(); return false;">
          <label for="qName">Your Name</label>
          <input type="text" id="qName" name="qName" placeholder="Your Name" required>
          <label for="qEmail">Your Email</label>
          <input type="email" id="qEmail" name="qEmail" placeholder="you@example.com" required>
          <label for="qHeadcount">Number of Guests</label>
          <input type="number" id="qHeadcount" name="qHeadcount" placeholder="Enter guest count" required>
          <label for="qEventType">Event Type</label>
          <select id="qEventType" name="qEventType" required>
            <option value="backyard">Backyard Party</option>
            <option value="wedding">Wedding</option>
            <option value="other">Other</option>
          </select>
          <label for="qBarService">Need a Mobile Bar?</label>
          <select id="qBarService" name="qBarService" required>
            <option value="yes">Yes</option>
            <option value="no">No</option>
          </select>
          <button type="button" id="calculateQuote">Calculate Quote</button>
          <div id="quoteResult" style="margin-top:20px;"></div>
          <input type="hidden" id="calculatedQuote" name="calculatedQuote" value="">
          <button type="submit">Send Quote Request</button>
        </form>
      </div>
    </section>
    
    <!-- CONTACT SECTION -->
    <section class="info-section" id="contact">
      <div class="container">
        <h2>Contact Us</h2>
        <p>Call: Raeanne (860) 517-6602</p>
        <p>Email: <a href="mailto:raiseaglassservices@gmail.com">raiseaglassservices@gmail.com</a></p>
        <a href="#booking" class="btn">Book Now</a>
      </div>
    </section>
  </main>
  
  <!-- FOOTER -->
  <footer class="footer">
    <div class="container">
      <p>© 2024 Raise A Glass LLC - Mobile Event Bartending & Casino Fun</p>
    </div>
  </footer>
  
  <!-- Sticky Book Raeanne Button -->
  <a href="#booking" class="sticky-book-btn">Book Raeanne Now!</a>
  
  <!-- Floating Buttons for Pop-Ups -->
  <button id="openQuotePopup" class="floating-btn">Quick Quote</button>
  <button id="openSlotMachine" class="floating-btn">Slots</button>
  <button id="openBlackjack" class="floating-btn">Blackjack</button>
  <button id="openRocket" class="floating-btn">Rocket</button>
  
  <!-- Pop-Up: Quick Quote Calculator -->
  <div id="quotePopup" class="popup" style="display:none;">
    <div class="popup-header">
      <span class="popup-title">Quick Quote Calculator</span>
      <div>
        <button class="popup-minimize">_</button>
        <button class="popup-close">X</button>
      </div>
    </div>
    <div class="popup-content">
      <label>Guest Count:</label>
      <input type="number" id="popupGuestCount" placeholder="Enter guest count" min="1" />
      <label>Event Type:</label>
      <select id="popupEventType">
        <option value="backyard">Backyard Party</option>
        <option value="wedding">Wedding</option>
        <option value="other">Other</option>
      </select>
      <label>Need a Mobile Bar?</label>
      <select id="popupBarService">
        <option value="yes">Yes</option>
        <option value="no">No</option>
      </select>
      <button id="popupCalculateQuote" class="casino-btn">Calculate Quote</button>
      <div id="popupQuoteResult" style="margin-top:10px; font-weight:bold;"></div>
    </div>
  </div>
  
  <!-- Pop-Up: Slot Machine Game -->
  <div id="slotMachinePopup" class="popup" style="display:none;">
    <div class="popup-header">
      <span class="popup-title">Bartender Slot Machine</span>
      <button class="popup-close">X</button>
    </div>
    <div class="popup-content">
      <div id="slotBankDisplay" style="font-weight:bold; margin-bottom:10px;">Bank: $1000</div>
      <div id="slotDisplay">
        <div class="slot-reel" id="slot1">?</div>
        <div class="slot-reel" id="slot2">?</div>
        <div class="slot-reel" id="slot3">?</div>
      </div>
      <input type="number" id="slotBetInput" class="casino-input" min="1" max="500" value="10" placeholder="Bet ($1-$500)" />
      <button id="slotSpinButton" class="casino-btn">Spin</button>
      <button id="slotCashOutButton" class="casino-btn">Cash Out</button>
      <div id="slotResult" style="margin-top:10px; font-weight:bold;"></div>
    </div>
  </div>
  
  <!-- Pop-Up: Blackjack Game -->
  <div id="blackjackPopup" class="popup" style="display:none;">
    <div class="popup-header">
      <span class="popup-title">Blackjack</span>
      <button class="popup-close">X</button>
    </div>
    <div class="popup-content">
      <div id="blackjackBankDisplay" style="font-weight:bold; margin-bottom:10px;">Bank: $1000</div>
      <input type="number" id="blackjackBetInput" class="casino-input" min="1" max="500" value="10" placeholder="Bet ($1-$500)" />
      <button id="blackjackStartButton" class="casino-btn">Start Game</button>
      <div id="blackjackHands">
        <div class="hand" id="playerHand">Player: </div>
        <div class="hand" id="dealerHand">Dealer: </div>
      </div>
      <div id="blackjackControls" style="display:none;">
        <button id="hitButton" class="casino-btn">Hit</button>
        <button id="standButton" class="casino-btn">Stand</button>
        <button id="doubleButton" class="casino-btn">Double Down</button>
        <button id="splitButton" class="casino-btn" style="display:none;">Split</button>
      </div>
      <div id="blackjackResult" style="margin-top:10px; font-weight:bold;"></div>
    </div>
  </div>
  
  <!-- Pop-Up: Rocket Game -->
  <div id="rocketPopup" class="popup" style="display:none;">
    <div class="popup-header">
      <span class="popup-title">Rocket Game</span>
      <button class="popup-close">X</button>
    </div>
    <div class="popup-content">
      <div id="rocketBankDisplay" style="font-weight:bold; margin-bottom:10px;">Bank: $1000</div>
      <input type="number" id="rocketBetInput" class="casino-input" min="1" max="500" value="10" placeholder="Bet ($1-$500)" />
      <button id="rocketStartButton" class="casino-btn">Launch Rocket</button>
      <div id="rocketDisplay">
        Multiplier: <span id="rocketMultiplier">1.00x</span>
      </div>
      <button id="rocketCashOutButton" class="casino-btn" style="display:none;">Cash Out</button>
      <div id="rocketResult" style="margin-top:10px; font-weight:bold;"></div>
    </div>
  </div>
  
  <!-- Pop-Up: Booking Confirmation -->
  <div id="bookingConfirmPopup" class="popup" style="display:none;">
    <div class="popup-header">
      <span class="popup-title">Booking Confirmed!</span>
      <button class="popup-close">X</button>
    </div>
    <div class="popup-content">
      <p id="confirmMessage">Your event with Raeanne is booked! We'll reach out soon to confirm details.</p>
      <button class="btn" onclick="$('#bookingConfirmPopup').hide();">Close</button>
    </div>
  </div>
  
  <!-- jQuery, jQuery UI, and Inline Scripts -->
  <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
  <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
  <script>
    // Shared Casino Bank
    let bank = 1000;
    
    // Simulated booked dates (for demo purposes)
    const bookedDates = ["11/15/2024", "11/20/2024", "12/01/2024"];
    
    // Booking Form Submission
    function submitBookingForm() {
      var name = document.getElementById('name').value;
      var email = document.getElementById('email').value;
      var phone = document.getElementById('phone').value;
      var address = document.getElementById('address').value;
      var eventDate = document.getElementById('eventDate').value;
      var headcount = document.getElementById('headcount').value;
      var eventType = document.getElementById('eventType').value;
      var location = document.getElementById('location').value;
      var barService = document.getElementById('barService').value;
      var comments = document.getElementById('comments').value;
      
      if (bookedDates.includes(eventDate)) {
        alert("Oops! Raeanne is already booked on this date. Please choose another.");
        return;
      }
      
      var subject = encodeURIComponent("New Booking Request from " + name);
      var body = encodeURIComponent(
        "Name: " + name + "\n" +
        "Email: " + email + "\n" +
        "Phone: " + phone + "\n" +
        "Address: " + address + "\n" +
        "Event Date: " + eventDate + "\n" +
        "Guest Count: " + headcount + "\n" +
        "Event Type: " + eventType + "\n" +
        "Location: " + location + "\n" +
        "Mobile Bar: " + barService + "\n" +
        "Additional Comments: " + comments
      );
      
      window.location.href = "mailto:raiseaglassservices@gmail.com?subject=" + subject + "&body=" + body;
      
      $("#confirmMessage").html(`Your event with Raeanne is booked for ${eventDate}! We'll reach out soon to confirm details.`);
      $("#bookingConfirmPopup").show();
      $("#bookingForm")[0].reset();
    }
    
    // Quote Form Submission
    function submitQuoteForm() {
      var qName = document.getElementById('qName').value;
      var qEmail = document.getElementById('qEmail').value;
      var qHeadcount = document.getElementById('qHeadcount').value;
      var qEventType = document.getElementById('qEventType').value;
      var qBarService = document.getElementById('qBarService').value;
      var calculatedQuote = document.getElementById('calculatedQuote').value;
      
      var subject = encodeURIComponent("New Quote Request from " + qName);
      var body = encodeURIComponent(
        "Name: " + qName + "\n" +
        "Email: " + qEmail + "\n" +
        "Number of Guests: " + qHeadcount + "\n" +
        "Event Type: " + qEventType + "\n" +
        "Mobile Bar: " + qBarService + "\n" +
        "Estimated Quote: $" + calculatedQuote
      );
      
      window.location.href = "mailto:raiseaglassservices@gmail.com?subject=" + subject + "&body=" + body;
    }
    
    $(document).ready(function(){
      // Initialize Datepickers
      $("#eventDate").datepicker({ 
        minDate: 0, 
        dateFormat: "mm/dd/yy",
        beforeShowDay: function(date) {
          var formattedDate = $.datepicker.formatDate("mm/dd/yy", date);
          return [!bookedDates.includes(formattedDate), bookedDates.includes(formattedDate) ? "booked" : ""];
        },
        onSelect: function(dateText) {
          if (bookedDates.includes(dateText)) {
            $("#availabilityStatus").html("Raeanne is booked on this date.").css("color", "#e07a5f");
          } else {
            $("#availabilityStatus").html("Raeanne is available! Lock it in!").css("color", "#3d405b");
          }
        }
      });
      $("#datepicker").datepicker({ 
        minDate: 0, 
        beforeShowDay: function(date) {
          var formattedDate = $.datepicker.formatDate("mm/dd/yy", date);
          return [!bookedDates.includes(formattedDate), bookedDates.includes(formattedDate) ? "booked" : ""];
        },
        onSelect: function(dateText) {
          $("#eventDate").val(dateText);
          if (bookedDates.includes(dateText)) {
            $("#availabilityStatus").html("Raeanne is booked on this date.").css("color", "#e07a5f");
          } else {
            $("#availabilityStatus").html("Raeanne is available! Lock it in!").css("color", "#3d405b");
          }
        }
      });
      
      // Quote Generator Logic
      $("#calculateQuote").click(function(){
        var headcount = parseInt($("#qHeadcount").val());
        var eventType = $("#qEventType").val();
        var barService = $("#qBarService").val();
        if (isNaN(headcount) || headcount <= 0) {
          $("#quoteResult").html("Please enter a valid number of guests.");
          return;
        }
        var basePrice = 200, pricePerGuest = 10;
        if (eventType === "wedding") { 
          basePrice = 500; 
          pricePerGuest = 20; 
        }
        var total = basePrice + (headcount * pricePerGuest);
        if (barService === "yes") { total += 150; }
        $("#quoteResult").html("Estimated Quote: $" + total);
        $("#calculatedQuote").val(total);
      });
      
      $("#popupCalculateQuote").click(function(){
        var headcount = parseInt($("#popupGuestCount").val());
        var eventType = $("#popupEventType").val();
        var barService = $("#popupBarService").val();
        if (isNaN(headcount) || headcount <= 0) {
          $("#popupQuoteResult").html("Please enter a valid guest count.");
          return;
        }
        var basePrice = 200, pricePerGuest = 10;
        if (eventType === "wedding") { basePrice = 500; pricePerGuest = 20; }
        var total = basePrice + (headcount * pricePerGuest);
        if (barService === "yes") { total += 150; }
        $("#popupQuoteResult").html("Estimated Quote: $" + total);
      });
      
      // Pop-Up Handlers
      $("#openQuotePopup").click(function(){ $("#quotePopup").show(); });
      $("#quotePopup").draggable({ handle: ".popup-header" });
      $("#quotePopup .popup-close").click(function(){ $("#quotePopup").hide(); });
      $("#quotePopup .popup-minimize").click(function(){ $("#quotePopup .popup-content").toggle(); });
      
      $("#bookingConfirmPopup").draggable({ handle: ".popup-header" });
      $("#bookingConfirmPopup .popup-close").click(function(){ $("#bookingConfirmPopup").hide(); });
      
      $("#openSlotMachine").click(function(){ $("#slotMachinePopup").show(); });
      $("#slotMachinePopup").draggable({ handle: ".popup-header" });
      $("#slotMachinePopup .popup-close").click(function(){ $("#slotMachinePopup").hide(); });
      
      $("#openBlackjack").click(function(){ $("#blackjackPopup").show(); });
      $("#blackjackPopup").draggable({ handle: ".popup-header" });
      $("#blackjackPopup .popup-close").click(function(){ $("#blackjackPopup").hide(); });
      
      $("#openRocket").click(function(){ $("#rocketPopup").show(); });
      $("#rocketPopup").draggable({ handle: ".popup-header" });
      $("#rocketPopup .popup-close").click(function(){ $("#rocketPopup").hide(); });
      
      // Update Bank Display Across Games
      function updateBankDisplays() {
        $("#slotBankDisplay").html("Bank: $" + bank);
        $("#blackjackBankDisplay").html("Bank: $" + bank);
        $("#rocketBankDisplay").html("Bank: $" + bank);
      }
      
      // Slot Machine Logic
      const slotEmojis = ["🍔", "🍕", "🍸", "💍", "💎"];
      const slotPayScale = {
        "🍔": { triple: 5, two: 1.5, prob: 0.3 },
        "🍕": { triple: 10, two: 2, prob: 0.25 },
        "🍸": { triple: 15, two: 2, prob: 0.2 },
        "💍": { triple: 25, two: 2, prob: 0.15 },
        "💎": { triple: 50, two: 2, prob: 0.1 } // Rare diamond
      };
      
      $("#slotNavLink").click(function(){ $("#slotMachinePopup").show(); });
      
      $("#slotSpinButton").click(function(){
        var bet = parseInt($("#slotBetInput").val());
        if (isNaN(bet) || bet < 1 || bet > 500 || bet > bank) {
          $("#slotResult").html("Invalid bet! Must be $1-$500 and within bank.");
          return;
        }
        
        bank -= bet;
        updateBankDisplays();
        $("#slotResult").html("Spinning...");
        $(".slot-reel").addClass("spinning");
        
        setTimeout(function() {
          var s1 = weightedRandom(slotEmojis, Object.values(slotPayScale).map(p => p.prob));
          $("#slot1").html(s1).removeClass("spinning");
          
          setTimeout(function() {
            var s2 = weightedRandom(slotEmojis, Object.values(slotPayScale).map(p => p.prob));
            $("#slot2").html(s2).removeClass("spinning");
            
            setTimeout(function() {
              var s3 = weightedRandom(slotEmojis, Object.values(slotPayScale).map(p => p.prob));
              $("#slot3").html(s3).removeClass("spinning");
              
              var payout = 0;
              if (s1 === s2 && s2 === s3) {
                payout = bet * slotPayScale[s1].triple;
                bank += payout;
                $("#slotResult").html(`Jackpot! You won $${payout}!`);
              } else if (s1 === s2 || s2 === s3 || s1 === s3) {
                var winningEmoji = s1 === s2 ? s1 : s2 === s3 ? s2 : s1;
                payout = bet * slotPayScale[winningEmoji].two;
                bank += payout;
                $("#slotResult").html(`Nice! You won $${payout}!`);
              } else if (s1 === "💎" || s2 === "💎" || s3 === "💎") {
                payout = bet * 1.5;
                bank += payout;
                $("#slotResult").html(`Diamond Bonus! You won $${payout}!`);
              } else {
                $("#slotResult").html("No win. Spin again!");
              }
              updateBankDisplays();
            }, 600);
          }, 400);
        }, 200);
      });
      
      $("#slotCashOutButton").click(function(){
        alert("You cashed out with $" + bank + " in your bank!");
        bank = 1000;
        updateBankDisplays();
        $("#slotResult").html("");
        $("#slot1, #slot2, #slot3").html("?");
      });
      
      // Blackjack Logic
      const suits = ["♠", "♥", "♦", "♣"];
      const values = ["2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K", "A"];
      let deck = [];
      let playerHands = [[]];
      let dealerHand = [];
      let currentHand = 0;
      
      function buildDeck() {
        deck = [];
        for (let suit of suits) {
          for (let value of values) {
            deck.push(value + suit);
          }
        }
        shuffle(deck);
      }
      
      function shuffle(array) {
        for (let i = array.length - 1; i > 0; i--) {
          const j = Math.floor(Math.random() * (i + 1));
          [array[i], array[j]] = [array[j], array[i]];
        }
      }
      
      function getCardValue(card) {
        const value = card.slice(0, -1);
        if (["J", "Q", "K"].includes(value)) return 10;
        if (value === "A") return 11;
        return parseInt(value);
      }
      
      function calculateHand(hand) {
        let total = 0;
        let aces = 0;
        hand.forEach(card => {
          let value = getCardValue(card);
          if (value === 11) aces++;
          total += value;
        });
        while (total > 21 && aces > 0) {
          total -= 10;
          aces--;
        }
        return total;
      }
      
      $("#blackjackNavLink").click(function(){ $("#blackjackPopup").show(); });
      
      $("#blackjackStartButton").click(function(){
        var bet = parseInt($("#blackjackBetInput").val());
        if (isNaN(bet) || bet < 1 || bet > 500 || bet > bank) {
          $("#blackjackResult").html("Invalid bet! Must be $1-$500 and within bank.");
          return;
        }
        
        bank -= bet;
        updateBankDisplays();
        buildDeck();
        playerHands = [[deck.pop(), deck.pop()]];
        dealerHand = [deck.pop(), "??"];
        currentHand = 0;
        
        $("#playerHand").html("Player: " + playerHands[0].join(", "));
        $("#dealerHand").html("Dealer: " + dealerHand.join(", "));
        $("#blackjackControls").show();
        $("#blackjackResult").html("");
        
        if (playerHands[0].length === 2 && playerHands[0][0][0] === playerHands[0][1][0]) {
          $("#splitButton").show();
        } else {
          $("#splitButton").hide();
        }
        
        if (calculateHand(playerHands[0]) === 21) {
          endBlackjackRound(bet);
        }
      });
      
      $("#hitButton").click(function(){
        playerHands[currentHand].push(deck.pop());
        $("#playerHand").html("Player: " + playerHands[currentHand].join(", "));
        if (calculateHand(playerHands[currentHand]) > 21) {
          $("#blackjackResult").html("Bust! You lose.");
          $("#blackjackControls").hide();
        }
      });
      
      $("#standButton").click(function(){
        if (currentHand < playerHands.length - 1) {
          currentHand++;
          $("#playerHand").html("Player: " + playerHands[currentHand].join(", "));
        } else {
          endBlackjackRound(parseInt($("#blackjackBetInput").val()));
        }
      });
      
      $("#doubleButton").click(function(){
        var bet = parseInt($("#blackjackBetInput").val());
        if (bank < bet) {
          $("#blackjackResult").html("Not enough funds to double!");
          return;
        }
        bank -= bet;
        updateBankDisplays();
        playerHands[currentHand].push(deck.pop());
        $("#playerHand").html("Player: " + playerHands[currentHand].join(", "));
        if (calculateHand(playerHands[currentHand]) <= 21) {
          endBlackjackRound(bet * 2);
        } else {
          $("#blackjackResult").html("Bust! You lose.");
          $("#blackjackControls").hide();
        }
      });
      
      $("#splitButton").click(function(){
        var bet = parseInt($("#blackjackBetInput").val());
        if (bank < bet) {
          $("#blackjackResult").html("Not enough funds to split!");
          return;
        }
        bank -= bet;
        updateBankDisplays();
        let card1 = playerHands[0][0];
        let card2 = playerHands[0][1];
        playerHands = [[card1, deck.pop()], [card2, deck.pop()]];
        $("#playerHand").html("Player Hand 1: " + playerHands[0].join(", "));
        currentHand = 0;
      });
      
      function endBlackjackRound(bet) {
        $("#blackjackControls").hide();
        dealerHand[1] = deck.pop();
        while (calculateHand(dealerHand) < 17) {
          dealerHand.push(deck.pop());
        }
        $("#dealerHand").html("Dealer: " + dealerHand.join(", "));
        
        let dealerTotal = calculateHand(dealerHand);
        let playerTotal = calculateHand(playerHands[currentHand]);
        
        if (dealerTotal > 21) {
          bank += bet * 2;
          $("#blackjackResult").html("Dealer busts! You win $" + (bet * 2) + "!");
        } else if (playerTotal > 21) {
          $("#blackjackResult").html("Bust! You lose.");
        } else if (playerTotal === 21 && playerHands[currentHand].length === 2) {
          bank += bet * 2.5;
          $("#blackjackResult").html("Blackjack! You win $" + (bet * 2.5) + "!");
        } else if (playerTotal > dealerTotal) {
          bank += bet * 2;
          $("#blackjackResult").html("You win $" + (bet * 2) + "!");
        } else if (playerTotal === dealerTotal) {
          bank += bet;
          $("#blackjackResult").html("Push! Bet returned.");
        } else {
          $("#blackjackResult").html("Dealer wins!");
        }
        updateBankDisplays();
      }
      
      // Rocket Game Logic
      let rocketInterval = null;
      let currentMultiplier = 1.00;
      
      $("#rocketNavLink").click(function(){ $("#rocketPopup").show(); });
      
      $("#rocketStartButton").click(function(){
        var bet = parseInt($("#rocketBetInput").val());
        if (isNaN(bet) || bet < 1 || bet > 500 || bet > bank) {
          $("#rocketResult").html("Invalid bet! Must be $1-$500 and within bank.");
          return;
        }
        
        bank -= bet;
        updateBankDisplays();
        currentMultiplier = 1.00;
        $("#rocketMultiplier").html(currentMultiplier.toFixed(2) + "x");
        $("#rocketCashOutButton").show();
        $("#rocketStartButton").hide();
        $("#rocketResult").html("Rocket launched!");
        
        let crashPoint = generateCrashPoint();
        rocketInterval = setInterval(function(){
          currentMultiplier += 0.05;
          $("#rocketMultiplier").html(currentMultiplier.toFixed(2) + "x");
          if (currentMultiplier >= crashPoint) {
            clearInterval(rocketInterval);
            $("#rocketResult").html("Crash! You lost.");
            $("#rocketCashOutButton").hide();
            $("#rocketStartButton").show();
          }
        }, 100);
      });
      
      $("#rocketCashOutButton").click(function(){
        clearInterval(rocketInterval);
        let payout = Math.floor(parseInt($("#rocketBetInput").val()) * currentMultiplier);
        bank += payout;
        $("#rocketResult").html(`Cashed out! You won $${payout}!`);
        $("#rocketCashOutButton").hide();
        $("#rocketStartButton").show();
        updateBankDisplays();
      });
      
      function generateCrashPoint() {
        let r = Math.random();
        if (r < 0.5) return 1.1 + Math.random() * 3.9; // 1.1x - 5x (50%)
        if (r < 0.8) return 6 + Math.random() * 4; // 6x - 10x (30%)
        if (r < 0.95) return 20 + Math.random() * 80; // 20x - 100x (15%)
        if (r < 0.99) return 200 + Math.random() * 300; // 200x - 500x (4%)
        return 500 + Math.random() * 500; // 500x - 1000x (1%)
      }
      
      // Utility for Weighted Random Selection
      function weightedRandom(items, weights) {
        let totalWeight = weights.reduce((a, b) => a + b, 0);
        let r = Math.random() * totalWeight;
        for (let i = 0; i < items.length; i++) {
          r -= weights[i];
          if (r <= 0) return items[i];
        }
        return items[items.length - 1];
      }
      
      // Fun Fact Ticker
      var facts = [
        "Connecticut is known for its vibrant party scene in New Haven!",
        "Hartford has a rich history of speakeasies and underground bars.",
        "Mystic, CT boasts maritime charm and innovative cocktail culture.",
        "Connecticut hosts some of the most unique weddings in the Northeast.",
        "Every cocktail in CT tells a story of tradition and innovation.",
        "New London is a hotspot for creative mixologists.",
        "The scenic beauty of CT makes outdoor parties unforgettable.",
        "CT's craft cocktail scene is booming with local distilleries.",
        "From CT beaches to elegant ballrooms, celebrations here shine.",
        "Festivals in Connecticut celebrate food, drink, and local art.",
        "Connecticut’s seasonal events are perfect for cocktail enthusiasts.",
        "Many CT bars offer locally sourced ingredients in their drinks.",
        "Historic taverns in CT provide a cozy party atmosphere.",
        "CT’s mixology scene blends tradition with modern flair.",
        "The state's diverse venues make every event special.",
        "Connecticut is home to innovative craft cocktail competitions.",
        "CT breweries and distilleries collaborate on unique flavors.",
        "Outdoor gatherings in CT are enhanced by its scenic views.",
        "CT hosts festivals celebrating everything from food to fine wine.",
        "Local chefs and bartenders in CT create unforgettable pairings.",
        "Connecticut nightlife is as diverse as its communities.",
        "Many CT events feature live music and creative cocktails.",
        "CT's coastal towns are renowned for seaside celebrations.",
        "Local art and design influence CT’s trendy bar scenes.",
        "CT’s mixologists are pioneers in sustainable cocktail practices.",
        "The state’s historic inns host charming cocktail evenings.",
        "Connecticut offers a blend of urban chic and rustic charm in events.",
        "CT’s cocktail menus often reflect the state’s cultural diversity.",
        "Innovative cocktail presentations are a CT specialty.",
        "CT events combine tradition, elegance, and a dash of rebellion.",
        "Party-goers in CT enjoy both vintage and modern vibes.",
        "Connecticut is home to some of the country’s most creative bartenders.",
        "CT’s culinary scene perfectly complements its cocktail culture.",
        "Outdoor patios in CT provide a relaxed party ambiance.",
        "Many CT bars double as art galleries, enhancing the party scene.",
        "Connecticut’s scenic vistas set the perfect backdrop for celebrations.",
        "CT's wine bars offer a sophisticated twist on classic cocktails.",
        "The state is famous for hosting extravagant garden parties.",
        "CT’s local breweries often collaborate with mixologists for special events.",
        "Charming CT towns are ideal for intimate gatherings and celebrations.",
        "Many CT venues boast rooftop bars with stunning views.",
        "CT’s cocktail culture is enriched by its maritime history.",
        "Festive events in CT often feature creative themed cocktails.",
        "Connecticut’s historic districts provide a unique party atmosphere.",
        "CT is a blend of modern energy and storied tradition in celebrations.",
        "Local mixologists in CT are known for their innovative infusions.",
        "Connecticut’s events celebrate both luxury and local charm.",
        "CT’s food and drink festivals attract visitors from all over.",
        "Many CT venues have transformed old warehouses into chic party spots.",
        "The party scene in CT is as warm as its autumn hues.",
        "Connecticut’s cocktail culture is celebrated at local fairs and festivals.",
        "CT bars often host events that feature local live music.",
        "Connecticut is home to award-winning craft cocktail bars.",
        "Local legends and folklore add magic to CT parties.",
        "CT’s vibrant street festivals bring communities together over drinks.",
        "Many CT events are themed around the state’s rich maritime heritage.",
        "Connecticut’s creative cocktail competitions are a local favorite.",
        "CT’s bars are known for their signature, Instagram-worthy drinks.",
        "The mix of urban and rural settings makes CT events unique.",
        "Connecticut offers a fusion of international flavors in its cocktails.",
        "CT’s historical landmarks often serve as dramatic party venues.",
        "Many CT bartenders are true artists in their craft.",
        "CT’s festive celebrations are full of energy and creativity.",
        "Local farms in CT supply fresh ingredients for seasonal cocktails.",
        "CT’s cocktail bars often feature live art and music performances.",
        "The spirit of Connecticut is celebrated in its diverse party scenes.",
        "CT’s old inns and modern lounges blend seamlessly for events.",
        "Connecticut’s mixology innovation is recognized nationwide.",
        "CT is known for its cozy, intimate bar settings.",
        "Many CT parties are inspired by the state’s rich colonial history.",
        "CT’s outdoor events are popular in every season.",
        "Connecticut’s urban bars are hubs for creative networking events.",
        "CT festivals highlight the best of local food, drink, and music.",
        "Connecticut offers a perfect mix of elegance and down-to-earth fun.",
        "The cocktail culture in CT is rooted in local traditions.",
        "CT venues often mix vintage decor with modern cocktails.",
        "Many CT events celebrate the local arts and crafts scene.",
        "Connecticut’s bar scene is as diverse as its people.",
        "CT parties often feature interactive cocktail-making demos.",
        "The charm of Connecticut enhances every celebration.",
        "CT’s vibrant nightlife is full of hidden gem bars.",
        "Many CT bartenders are innovators in molecular mixology.",
        "CT hosts events that celebrate both tradition and innovation.",
        "Connecticut’s coastal towns are famous for lively beach parties.",
        "CT’s cocktail events often feature guest appearances by top mixologists.",
        "The creative energy in CT is reflected in its drink menus.",
        "CT’s historic venues provide a dramatic backdrop for events.",
        "Connecticut is a playground for those who love fine cocktails.",
        "CT’s parties often blend gourmet food with handcrafted drinks.",
        "Many CT events are set in beautifully restored historic buildings.",
        "The scenic beauty of CT makes every celebration picture-perfect.",
        "Connecticut’s vibrant party scene is fueled by creative energy.",
        "CT bars are known for their imaginative cocktail garnishes.",
        "Local festivals in CT are a showcase of food, art, and drink.",
        "CT’s cocktail culture continues to evolve with fresh ideas.",
        "Connecticut is a treasure trove of hidden cocktail bars.",
        "The state’s unique venues make CT events memorable.",
        "CT parties often celebrate the joy of community and creativity.",
        "Connecticut’s nightlife is as dynamic as its daytime charm.",
        "Many CT cocktail bars have a story behind every drink.",
        "CT’s festive gatherings are celebrated with style and flair.",
        "Connecticut offers endless inspiration for party planners.",
        "CT’s mixology scene is a blend of art, science, and passion.",
        "The magic of CT is captured in every cocktail served.",
        "Connecticut is home to some of the most innovative party concepts."
      ];
      
      function updateFunFact() {
        var fact = facts[Math.floor(Math.random() * facts.length)];
        $("#fun-fact-box").fadeOut(500, function(){
          $(this).text(fact).fadeIn(500);
        });
      }
      updateFunFact();
      setInterval(updateFunFact, 5000);
      
      // Smooth Scrolling for Nav Links
      $('a[href*="#"]').not('[href="#"]').click(function(event) {
        if (location.pathname.replace(/^\//, '') == this.pathname.replace(/^\//, '') && location.hostname == this.hostname) {
          event.preventDefault();
          var target = $(this.hash);
          target = target.length ? target : $('[name=' + this.hash.slice(1) + ']');
          if (target.length) {
            $('html, body').animate({
              scrollTop: target.offset().top - 70
            }, 800);
            return false;
          }
          
          if (this.hash === "#slots") $("#slotMachinePopup").show();
          if (this.hash === "#blackjack") $("#blackjackPopup").show();
          if (this.hash === "#rocket") $("#rocketPopup").show();
        }
      });
    });
  </script>
</body>
</html>
