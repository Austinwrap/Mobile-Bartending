<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Raise A Glass LLC - Event Bartending</title>
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
    }
    h1 {
      font-family: 'Dancing Script', cursive;
      font-size: 3.5em;
      color: #fff7e6;
      text-align: center;
      margin-bottom: 10px;
      text-shadow: 3px 3px 8px rgba(0,0,0,0.5);
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
    }
    
    /* BUBBLES BACKGROUND */
    .bubbles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
      z-index: -1;
    }
    .bubble {
      position: absolute;
      bottom: -100px;
      background: rgba(255,255,255,0.5);
      border-radius: 50%;
      opacity: 0.7;
      animation: rise 10s infinite ease-in;
    }
    @keyframes rise {
      0% { transform: translateY(0) scale(0.5); opacity: 0.7; }
      50% { opacity: 0.9; }
      100% { transform: translateY(-110vh) scale(1); opacity: 0; }
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
      padding: 10px 0;
      margin-top: 20px;
      z-index: 1000;
    }
    .main-nav a {
      color: #fff;
      text-decoration: none;
      margin: 0 15px;
      font-size: 1.1em;
      transition: color 0.3s;
    }
    .main-nav a:hover { color: #ffddd2; }
    
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
    }
    .container { width: 80%; margin: 0 auto; }
    ul { list-style-type: none; margin: 40px 0; padding: 0; }
    ul li {
      font-size: 1.4em;
      margin-bottom: 20px;
      padding: 20px;
      background: rgba(255,255,255,0.9);
      border-radius: 15px;
      box-shadow: 4px 4px 15px rgba(0,0,0,0.2);
    }
    
    /* BUTTONS */
    .btn {
      display: inline-block;
      background: linear-gradient(to right, #e07a5f, #3d405b);
      color: #fff;
      padding: 15px 30px;
      text-decoration: none;
      margin-top: 30px;
      border-radius: 12px;
      box-shadow: 5px 5px 15px rgba(0,0,0,0.3);
      transition: background 0.3s, box-shadow 0.3s;
      font-size: 1.2em;
    }
    .btn:hover {
      background: linear-gradient(to right, #3d405b, #e07a5f);
      box-shadow: 7px 7px 20px rgba(0,0,0,0.4);
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
    }
    .info-form input,
    .info-form select,
    .info-form textarea {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border-radius: 10px;
      border: 1px solid #ccc;
      font-size: 1em;
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
      transition: background 0.3s;
    }
    .info-form button:hover {
      background: linear-gradient(to right, #3d405b, #e07a5f);
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
    
    /* RESPONSIVE */
    @media (max-width: 768px) {
      .container { width: 90%; }
      .main-nav { position: relative; top: 0; width: 100%; padding: 10px 0; }
      .main-nav a { margin: 5px; font-size: 1em; }
      .columns { display: none; }
      .btn { padding: 12px 25px; font-size: 1em; }
      .booking-calendar { flex-direction: column; }
      .booking-calendar > div { width: 100%; margin-bottom: 20px; }
    }
    
    /* Booking & Calendar Combined */
    .booking-calendar {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      gap: 20px;
    }
    .booking-calendar .booking-form {
      flex: 1;
    }
    .booking-calendar .calendar-container {
      flex: 1;
      max-width: 350px;
    }
    
    /* Floating Buttons for Pop-Ups */
    .floating-btn {
      position: fixed;
      bottom: 20px;
      right: 20px;
      margin: 5px;
      background: #3d405b;
      color: #fff;
      border: none;
      padding: 10px 15px;
      border-radius: 8px;
      cursor: pointer;
      z-index: 10001;
      box-shadow: 2px 2px 8px rgba(0,0,0,0.4);
    }
    .floating-btn:hover { background: #e07a5f; }
    
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
    .popup-content {
      padding: 10px;
    }
    .popup .hidden { display: none; }
    
    /* Custom Styles for Pop-Ups */
    /* Quick Quote Pop-Up: Bigger & Different Color */
    #quotePopup {
      width: 350px;
      background: #fef9e7;
      border-color: #d4ac0d;
    }
    /* Slot Machine Pop-Up: Cuter with Pastel/Neon Accents */
    #slotMachinePopup {
      width: 350px;
      background: #e8f8f5;
      border-color: #16a085;
    }
    /* Neon Effect for Slot Machine Display */
    .neon {
      font-size: 3em;
      padding: 10px;
      border: 3px solid #0ff;
      border-radius: 8px;
      text-align: center;
      animation: neonGlow 1.5s ease-in-out infinite alternate;
      margin-bottom: 10px;
    }
    @keyframes neonGlow {
      from { box-shadow: 0 0 10px #0ff, 0 0 20px #0ff, 0 0 30px #0ff; }
      to { box-shadow: 0 0 20px #0ff, 0 0 30px #0ff, 0 0 40px #0ff; }
    }
    
  </style>
</head>
<body>
  <!-- Fun Fact Ticker -->
  <div id="fun-fact-box">Did you know? Loading fun facts...</div>
  
  <!-- Bubbles Background -->
  <div class="bubbles">
    <div class="bubble" style="left: 10%; width: 40px; height: 40px; animation-delay: 0s;"></div>
    <div class="bubble" style="left: 20%; width: 30px; height: 30px; animation-delay: 2s;"></div>
    <div class="bubble" style="left: 35%; width: 50px; height: 50px; animation-delay: 4s;"></div>
    <div class="bubble" style="left: 50%; width: 20px; height: 20px; animation-delay: 1s;"></div>
    <div class="bubble" style="left: 65%; width: 45px; height: 45px; animation-delay: 3s;"></div>
    <div class="bubble" style="left: 80%; width: 35px; height: 35px; animation-delay: 5s;"></div>
    <div class="bubble" style="left: 90%; width: 25px; height: 25px; animation-delay: 7s;"></div>
    <div class="bubble" style="left: 15%; width: 30px; height: 30px; animation-delay: 6s;"></div>
    <div class="bubble" style="left: 40%; width: 40px; height: 40px; animation-delay: 8s;"></div>
    <div class="bubble" style="left: 75%; width: 50px; height: 50px; animation-delay: 4s;"></div>
  </div>
  
  <!-- HEADER -->
  <header class="header" id="home">
    <div class="container">
      <h1>Raise A Glass LLC</h1>
      <p class="tagline">Mobile Bartending Services for All Occasions</p>
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
        <h2>About Raeanne</h2>
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
          <!-- Booking Form Column -->
          <div class="booking-form">
            <form class="info-form" id="bookingForm" action="#" method="POST">
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
          <!-- Calendar Column -->
          <div class="calendar-container">
            <h3>Choose Your Date</h3>
            <div id="datepicker" style="margin: 0 auto;"></div>
          </div>
        </div>
      </div>
    </section>
    
    <!-- QUOTE GENERATOR SECTION (Existing Section) -->
    <section class="info-section" id="quote">
      <div class="container">
        <h2>Quote Generator</h2>
        <form class="info-form" id="quoteForm" action="#" method="POST">
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
          
          <!-- Hidden field to store calculated quote -->
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
        <a href="#packages" class="btn">Book Now</a>
      </div>
    </section>
  </main>
  
  <!-- FOOTER -->
  <footer class="footer">
    <div class="container">
      <p>&copy; 2024 Raise A Glass LLC - Mobile Event Bartending</p>
    </div>
  </footer>
  
  <!-- Floating Buttons to Open Pop-Ups -->
  <button id="openQuotePopup" class="floating-btn" style="right:20px;">Quick Quote</button>
  <button id="openSlotMachine" class="floating-btn" style="right:150px;">Play Slots</button>
  
  <!-- Pop-Up: Quick Quote Calculator (Draggable) -->
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
      <button id="popupCalculateQuote">Calculate Quote</button>
      <div id="popupQuoteResult" style="margin-top:10px; font-weight:bold;"></div>
    </div>
  </div>
  
  <!-- Pop-Up: Bartender Slot Machine Game (Draggable) -->
  <div id="slotMachinePopup" class="popup" style="display:none;">
    <div class="popup-header">
      <span class="popup-title">Bartender Slot Machine</span>
      <button class="popup-close">X</button>
    </div>
    <div class="popup-content">
      <div id="bankDisplay" style="font-weight:bold; margin-bottom:10px;">Bank: $1000</div>
      <div id="slotDisplay" class="neon">
        <span id="slot1">?</span>
        <span id="slot2">?</span>
        <span id="slot3">?</span>
      </div>
      <button id="spinButton">Spin (Cost: $50)</button>
      <button id="cashOutButton" style="margin-top:10px;">Cash Out</button>
      <div id="slotResult" style="margin-top:10px; font-weight:bold;"></div>
    </div>
  </div>
  
  <!-- jQuery, jQuery UI, and Inline Scripts -->
  <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
  <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
  <script>
    $(document).ready(function(){
      // Initialize datepickers
      $("#eventDate").datepicker({ minDate: 0, dateFormat: "mm/dd/yy" });
      $("#datepicker").datepicker({ minDate: 0 });
      
      // Quote generator logic (in main section)
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
      
      // Quick Quote Pop-Up Logic
      $("#openQuotePopup").click(function(){
        $("#quotePopup").show();
      });
      $("#quotePopup").draggable({ handle: ".popup-header" });
      $("#quotePopup .popup-close").click(function(){
        $("#quotePopup").hide();
      });
      $("#quotePopup .popup-minimize").click(function(){
        $("#quotePopup .popup-content").toggle();
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
      
      // Slot Machine Game Logic
      var bank = 1000;
      var bet = 50;
      var slotEmojis = ["🍹", "🍸", "🍺", "🍷", "🍾"];
      var multipliers = { "🍹": 5, "🍸": 10, "🍺": 3, "🍷": 8, "🍾": 15 };
      
      $("#openSlotMachine").click(function(){
        $("#slotMachinePopup").show();
      });
      $("#slotMachinePopup").draggable({ handle: ".popup-header" });
      $("#slotMachinePopup .popup-close").click(function(){
        $("#slotMachinePopup").hide();
      });
      
      $("#spinButton").click(function(){
        if (bank < bet) {
          $("#slotResult").html("Insufficient funds!");
          return;
        }
        bank -= bet;
        $("#bankDisplay").html("Bank: $" + bank);
        // Randomly choose three emojis
        var s1 = slotEmojis[Math.floor(Math.random() * slotEmojis.length)];
        var s2 = slotEmojis[Math.floor(Math.random() * slotEmojis.length)];
        var s3 = slotEmojis[Math.floor(Math.random() * slotEmojis.length)];
        $("#slot1").html(s1);
        $("#slot2").html(s2);
        $("#slot3").html(s3);
        // Check if all three match
        if (s1 === s2 && s2 === s3) {
          var payout = bet * multipliers[s1];
          bank += payout;
          $("#slotResult").html("Jackpot! You won $" + payout + "!");
        } else {
          $("#slotResult").html("No win. Try again!");
        }
        $("#bankDisplay").html("Bank: $" + bank);
      });
      
      $("#cashOutButton").click(function(){
        alert("You cashed out with $" + bank + " in your bank!");
        bank = 1000;
        $("#bankDisplay").html("Bank: $" + bank);
        $("#slotResult").html("");
        $("#slot1, #slot2, #slot3").html("?");
      });
      
      // Fun Fact Ticker: 100 Fun Facts about Connecticut & Parties
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
    });
  </script>
</body>
</html>
