<?php
// Process the booking form submission if the form is submitted
$booking_message = "";
if ($_SERVER["REQUEST_METHOD"] === "POST" && isset($_POST["submit_booking"])) {
    // Sanitize and assign form variables
    $name      = htmlspecialchars(trim($_POST['name']));
    $email     = htmlspecialchars(trim($_POST['email']));
    $phone     = htmlspecialchars(trim($_POST['phone']));
    $address   = htmlspecialchars(trim($_POST['address']));
    $eventDate = htmlspecialchars(trim($_POST['eventDate']));
    $headcount = htmlspecialchars(trim($_POST['headcount']));
    $eventType = htmlspecialchars(trim($_POST['eventType']));
    $location  = htmlspecialchars(trim($_POST['location']));
    $barService= htmlspecialchars(trim($_POST['barService']));
    $comments  = htmlspecialchars(trim($_POST['comments']));

    // Set the recipient email (Raise A Glass Gmail)
    $to = "raiseaglassservices@gmail.com";
    $subject = "New Booking Request from " . $name;

    // Build a neatly formatted email body
    $message_body  = "Hello Raeanne,\n\n";
    $message_body .= "You have received a new booking request. Here are the details:\n";
    $message_body .= "--------------------------------------------\n";
    $message_body .= "Name:              " . $name . "\n";
    $message_body .= "Email:             " . $email . "\n";
    $message_body .= "Phone:             " . $phone . "\n";
    $message_body .= "Address:           " . $address . "\n";
    $message_body .= "Event Date:        " . $eventDate . "\n";
    $message_body .= "Guest Count:       " . $headcount . "\n";
    $message_body .= "Event Type:        " . $eventType . "\n";
    $message_body .= "Event Location:    " . $location . "\n";
    $message_body .= "Mobile Bar Needed: " . $barService . "\n";
    $message_body .= "Comments:          " . $comments . "\n";
    $message_body .= "--------------------------------------------\n\n";
    $message_body .= "This email was sent from your website booking form.\n";

    // Set email headers
    $headers = "From: noreply@yourdomain.com\r\n" .
               "Reply-To: " . $email . "\r\n" .
               "X-Mailer: PHP/" . phpversion();

    // Send the email and set a confirmation message
    if (mail($to, $subject, $message_body, $headers)) {
        $booking_message = "Thank you for your booking request. Raeanne will be in touch soon!";
    } else {
        $booking_message = "There was an error sending your booking request. Please try again later.";
    }
}
?>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Raise A Glass LLC - Event Bartending</title>
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <!-- jQuery UI CSS for the datepicker -->
  <link rel="stylesheet" href="https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
  <!-- Inline CSS -->
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
    
    /* FUN FACT TICKER */
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
    
    /* NEW SECTIONS: ABOUT, BOOKING/INFO, QUOTE, CALENDAR, CONTACT */
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
    
    /* ABOUT SECTION (Written by Raeanne) */
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
    <a href="#calendar">Calendar</a>
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
    
    <!-- BOOKING / INFORMATION SHEET SECTION -->
    <section class="info-section" id="booking">
      <div class="container">
        <h2>Book Your Event</h2>
        <?php 
          if (!empty($booking_message)) { 
              echo '<p style="text-align:center; font-size:1.2em; color:#3d405b;">
        <form class="info-form" id="bookingForm" action="" method="POST">
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
          
          <button type="submit" name="submit_booking">Submit Booking Request</button>
        </form>
      </div>
    </section>
    
    <!-- QUOTE GENERATOR SECTION -->
    <section class="info-section" id="quote">
      <div class="container">
        <h2>Quote Generator</h2>
        <form class="info-form" id="quoteForm">
          <label for="qHeadcount">Number of Guests</label>
          <input type="number" id="qHeadcount" placeholder="Enter guest count" required>
          
          <label for="qEventType">Event Type</label>
          <select id="qEventType" required>
            <option value="backyard">Backyard Party</option>
            <option value="wedding">Wedding</option>
            <option value="other">Other</option>
          </select>
          
          <label for="qBarService">Need a Mobile Bar?</label>
          <select id="qBarService" required>
            <option value="yes">Yes</option>
            <option value="no">No</option>
          </select>
          
          <button type="button" id="calculateQuote">Calculate Quote</button>
        </form>
        <div id="quoteResult"></div>
      </div>
    </section>
    
    <!-- CALENDAR SECTION -->
    <section class="info-section" id="calendar">
      <div class="container">
        <h2>Event Calendar</h2>
        <p>Select a date to see if Raeanne is available!</p>
        <div id="datepicker" style="margin: 0 auto; width: 300px;"></div>
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
  
  <!-- JavaScript: jQuery, jQuery UI, and Inline Scripts -->
  <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
  <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
  <script>
    $(document).ready(function(){
      // Initialize datepicker for booking form and calendar
      $("#eventDate").datepicker({ minDate: 0, dateFormat: "mm/dd/yy" });
      $("#datepicker").datepicker({
        minDate: 0,
        onSelect: function(dateText) {
          alert("You selected " + dateText + ". To book this date, please use the booking form above!");
        }
      });
      
      // Quote generator logic
      $("#calculateQuote").click(function(){
        var headcount = parseInt($("#qHeadcount").val());
        var eventType = $("#qEventType").val();
        var barService = $("#qBarService").val();
        
        if(isNaN(headcount) || headcount <= 0) {
          $("#quoteResult").html("Please enter a valid number of guests.");
          return;
        }
        
        var basePrice = 200, pricePerGuest = 10;
        if(eventType === "wedding") { basePrice = 500; pricePerGuest = 20; }
        var total = basePrice + (headcount * pricePerGuest);
        if(barService === "yes") { total += 150; }
        $("#quoteResult").html("Estimated Quote: $" + total);
      });
      
      // Fun Fact Ticker: Array of updated bartending facts
      var facts = [
        "Mixology blends art and science in every cocktail.",
        "Modern bartenders combine tradition with innovation.",
        "The craft cocktail movement is thriving worldwide.",
        "Sustainable practices are reshaping bar culture.",
        "Seasonal ingredients add a fresh twist to classic drinks.",
        "Unique garnishes elevate both aroma and presentation.",
        "Signature cocktails tell a story with every sip.",
        "Bartenders are creative problem solvers behind the bar.",
        "Local craft spirits fuel modern mixology.",
        "Molecular techniques inspire new drink recipes.",
        "Creative ice shapes add personality to cocktails.",
        "Custom infusions can transform a standard drink.",
        "Presentation is as crucial as flavor in a cocktail.",
        "Menus are curated with passion and precision.",
        "Every drink can be a mini masterpiece.",
        "Mixing cocktails is a sensory journey.",
        "Rigorous training perfects the art of bartending.",
        "A perfect cocktail balances sweet, sour, bitter, and savory.",
        "Classic drinks inspire bold, modern creations.",
        "Craft cocktails elevate any social experience.",
        "Local ingredients spark innovative recipes.",
        "Ambiance and presentation make every event special.",
        "Personalized drinks make events unforgettable.",
        "Tradition meets modern technique in every cocktail.",
        "Every sip of a well-crafted drink tells a story.",
        "Signature drinks can become cultural icons.",
        "Artisan bars are emerging in every major city.",
        "Competitions showcase the best in mixology.",
        "Immersive experiences are redefining cocktail culture.",
        "Handcrafted drinks celebrate quality and passion.",
        "Attention to detail is key in every cocktail.",
        "Performance art meets mixology behind the bar.",
        "Social media transforms cocktail trends.",
        "Local distilleries drive innovative recipes.",
        "Precision in measuring ingredients ensures perfect flavor.",
        "Innovative tools simplify cocktail making.",
        "Every cocktail is a canvas for creative expression.",
        "Garnishes can be as inventive as the drink itself.",
        "Collaboration between chefs and bartenders sparks flavor pairings.",
        "Custom cocktails create lasting memories.",
        "Experimentation is at the heart of modern mixology.",
        "Refreshing cocktails are a summer staple.",
        "Quality ingredients make all the difference.",
        "Live cocktail demos engage and delight audiences.",
        "Shaking and stirring are foundational mixology techniques.",
        "Handcrafted drinks honor both tradition and creativity.",
        "Every cocktail blends science, art, and passion.",
        "Creative recipes are shared around the globe.",
        "Presentation and flavor go hand in hand.",
        "Customizable drinks let guests choose their adventure.",
        "Signature cocktails set the tone for celebrations.",
        "Intricate ice cubes add an elegant touch.",
        "Each cocktail celebrates its unique ingredients.",
        "Exploring new flavor combinations is part of the fun.",
        "Personal style sets the best bartenders apart.",
        "Every drink is crafted with care and precision.",
        "Seasonal recipes keep cocktail menus fresh.",
        "Innovative pairings are transforming menus.",
        "Unique bar setups create immersive experiences.",
        "Mixology is an ever-evolving art form.",
        "Each cocktail reflects a blend of culture and creativity.",
        "Fresh, high-quality ingredients are essential.",
        "Sustainability shapes modern mixology.",
        "Garnishes can be edible art.",
        "Artisan cocktails capture the essence of their components.",
        "Visual appeal and taste make cocktails memorable.",
        "Mixology is about creating moments of joy.",
        "Precision and creativity unite behind every bar.",
        "Bartenders are the unsung heroes of great nights.",
        "Every cocktail pays tribute to innovation.",
        "Classic techniques blend with modern trends.",
        "The cocktail experience is both ritual and art.",
        "Mixologists push flavor boundaries.",
        "Great cocktails bring people together.",
        "Personalized drinks reflect the creator’s vision.",
        "Innovative presentations are a feast for the eyes.",
        "Each cocktail is a journey of taste and aroma.",
        "Artisanal techniques highlight the beauty of simplicity.",
        "Heritage and innovation coexist in modern mixology.",
        "Excellence is poured into every cocktail.",
        "Sharing the creative process adds to the experience.",
        "Community, creativity, and quality define cocktail culture.",
        "Every sip is a delightful surprise.",
        "Global trends inspire fresh cocktail ideas.",
        "Fresh herbs and fruits elevate every drink.",
        "Balance in flavor and style creates the perfect cocktail.",
        "Dedication and passion are the spirits behind every drink.",
        "A cocktail is an invitation to celebrate life."
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
