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
            transition: background 0.3s, color 0.3s;
        }
        body.dark-mode {
            background: linear-gradient(to bottom right, #2c2c2c, #4a4a4a);
            color: #ddd;
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
        body.dark-mode h2 { color: #f2cc8f; }

        /* Toggle Button */
        #mode-toggle {
            position: fixed;
            top: 10px;
            left: 10px;
            z-index: 10001;
            padding: 8px 15px;
            background: #e07a5f;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1em;
            box-shadow: 0 2px 5px rgba(0,0,0,0.3);
            transition: background 0.3s;
        }
        #mode-toggle:hover { background: #3d405b; }
        body.dark-mode #mode-toggle { background: #ffddd2; color: #333; }

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
        body.dark-mode #fun-fact-box { background-color: rgba(61, 64, 91, 0.95); color: #ffddd2; }

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
        .bubble.suds { background: radial-gradient(circle, rgba(255,255,255,0.9), rgba(255,255,255,0)); animation: sudsPop 4s infinite ease-out; }
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

        /* FANCY TOASTING CHAMPAGNE GLASSES */
        .champagne-glasses {
            position: absolute;
            top: 10px;
            right: 20px;
            width: 60px;
            height: 60px;
            z-index: 10;
            animation: clinkAndFizz 3s infinite ease-in-out;
        }
        @keyframes clinkAndFizz {
            0% { transform: translateX(0) rotate(0deg); }
            25% { transform: translateX(-12px) rotate(15deg); }
            50% { transform: translateX(0) rotate(0deg); }
            75% { transform: translateX(8px) rotate(-10deg); }
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
        body.dark-mode .header { background: #1a1a2e; border-bottom-color: #ffddd2; }
        .header .tagline { text-align: center; font-size: 1.8em; color: #f2cc8f; }

        /* NAVIGATION */
        .main-nav {
            background-color: #e07a5f;
            text-align: center;
            padding: 15px 0;
            z-index: 1000;
            position: sticky;
            top: 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
        }
        body.dark-mode .main-nav { background-color: #3d405b; }
        .main-nav a {
            color: #fff;
            text-decoration: none;
            font-size: 1.2em;
            transition: color 0.3s, transform 0.2s;
            white-space: nowrap;
        }
        .main-nav a:hover { color: #ffddd2; transform: scale(1.1); }

        /* Glamorous Rae's Casino Link */
        .casino-link {
            font-family: 'Dancing Script', cursive;
            font-size: 1.4em;
            color: #ffd700;
            text-shadow: 0 0 10px #ffd700, 0 0 20px #ff4500;
            padding: 5px 15px;
            border: 2px solid #ffd700;
            border-radius: 8px;
            animation: casinoPulse 1.5s infinite;
            background: radial-gradient(circle, rgba(255,215,0,0.2), transparent);
        }
        @keyframes casinoPulse {
            0% { transform: scale(1); box-shadow: 0 0 10px #ffd700, 0 0 20px #ff4500; }
            50% { transform: scale(1.05); box-shadow: 0 0 20px #ffd700, 0 0 30px #ff4500; }
            100% { transform: scale(1); box-shadow: 0 0 10px #ffd700, 0 0 20px #ff4500; }
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
        body.dark-mode .casino-dropdown-content { background-color: #1a1a2e; }
        .casino-dropdown-content a {
            color: #fff;
            padding: 12px 16px;
            text-decoration: none;
            display: block;
            font-family: 'Montserrat', sans-serif;
            font-size: 1em;
            margin: 0;
        }
        .casino-dropdown-content a:hover { background-color: #e07a5f; color: #ffd700; }
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
        body.dark-mode .columns { background: rgba(61, 64, 91, 0.8); }
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
        body.dark-mode section { background: rgba(40, 40, 40, 0.95); border-color: #ffddd2; }
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
        body.dark-mode ul li { background: rgba(61, 64, 91, 0.9); color: #ddd; }
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
            position: relative;
            overflow: hidden;
        }
        body.dark-mode .btn { background: linear-gradient(to right, #ffddd2, #1a1a2e); }
        .btn:hover {
            background: linear-gradient(to right, #3d405b, #e07a5f);
            box-shadow: 7px 7px 20px rgba(0,0,0,0.4);
            transform: scale(1.05);
        }
        body.dark-mode .btn:hover { background: linear-gradient(to right, #1a1a2e, #ffddd2); }
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
        body.dark-mode .footer { background-color: #1a1a2e; border-top-color: #ffddd2; }
        .footer a { color: #ffddd2; text-decoration: none; margin: 0 10px; font-size: 1.3em; }
        .footer a:hover { text-decoration: underline; color: #ffffff; }

        /* INFO SECTIONS */
        .info-section { padding: 80px 0; background: rgba(255,245,238,0.95); border: 4px solid #e07a5f; margin: 40px 0; box-shadow: 8px 8px 20px rgba(0,0,0,0.3); border-radius: 25px; }
        body.dark-mode .info-section { background: rgba(40, 40, 40, 0.95); border-color: #ffddd2; }
        .info-form { max-width: 600px; margin: 0 auto; text-align: left; }
        .info-form label { font-size: 1em; display: block; margin-bottom: 5px; color: #3d405b; }
        body.dark-mode .info-form label { color: #f2cc8f; }
        .info-form input, .info-form select, .info-form textarea {
            width: 100%;
            padding: 12px;
            margin-bottom: 15px;
            border-radius: 10px;
            border: 1px solid #ccc;
            font-size: 1em;
            font-family: 'Montserrat', sans-serif;
            transition: border-color 0.3s;
        }
        body.dark-mode .info-form input, body.dark-mode .info-form select, body.dark-mode .info-form textarea { background: #333; color: #ddd; border-color: #555; }
        .info-form input:focus, .info-form select:focus, .info-form textarea:focus { border-color: #e07a5f; outline: none; }
        body.dark-mode .info-form input:focus, body.dark-mode .info-form select:focus, body.dark-mode .info-form textarea:focus { border-color: #ffddd2; }
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
        body.dark-mode .info-form button { background: linear-gradient(to right, #ffddd2, #1a1a2e); }
        .info-form button:hover { background: linear-gradient(to right, #3d405b, #e07a5f); transform: scale(1.02); }
        body.dark-mode .info-form button:hover { background: linear-gradient(to right, #1a1a2e, #ffddd2); }
        #quoteResult { font-size: 1.5em; text-align: center; color: #3d405b; margin-top: 20px; }
        body.dark-mode #quoteResult { color: #f2cc8f; }

        /* ABOUT SECTION */
        .about-section { padding: 80px 0; background: rgba(255,245,238,0.98); border: 4px solid #e07a5f; margin: 40px 0; box-shadow: 8px 8px 20px rgba(0,0,0,0.3); border-radius: 25px; }
        body.dark-mode .about-section { background: rgba(40, 40, 40, 0.98); border-color: #ffddd2; }
        .about-section p { font-size: 1.3em; max-width: 700px; margin: 0 auto; line-height: 1.6; text-align: center; color: #3d405b; }
        body.dark-mode .about-section p { color: #ddd; }

        /* RESPONSIVE DESIGN */
        @media (max-width: 768px) {
            .container { width: 90%; }
            .main-nav { padding: 10px 0; gap: 15px; }
            .main-nav a { font-size: 1em; }
            .casino-link { font-size: 1.2em; padding: 3px 10px; }
            .casino-dropdown-content { position: static; transform: none; width: 100%; }
            .columns { display: none; }
            .btn { padding: 12px 25px; font-size: 1em; }
            .booking-calendar { flex-direction: column; }
            .booking-calendar > div { width: 100%; margin-bottom: 20px; }
            h1 { font-size: 2.5em; }
            h2 { font-size: 2em; }
            .header { padding: 40px 0; }
            .info-form input, .info-form select, .info-form textarea { font-size: 1em; padding: 10px; }
            .champagne-glasses { width: 40px; height: 40px; }
        }

        /* Booking & Calendar Combined */
        .booking-calendar { display: flex; justify-content: space-between; align-items: flex-start; gap: 20px; }
        .booking-calendar .booking-form { flex: 1; }
        .booking-calendar .calendar-container { flex: 1; max-width: 350px; }
        .availability-status { margin-top: 10px; font-size: 1.1em; color: #3d405b; }
        body.dark-mode .availability-status { color: #f2cc8f; }

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
        body.dark-mode .sticky-book-btn { background: #ffddd2; color: #333; }
        .sticky-book-btn:hover { transform: scale(1.1); background: #3d405b; }
        body.dark-mode .sticky-book-btn:hover { background: #1a1a2e; color: #fff; }

        /* Floating Buttons for Pop-Ups - Adjusted Positioning */
        .floating-btn {
            position: fixed;
            bottom: 70px;
            margin: 10px;
            background: #3d405b;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            z-index: 10001;
            box-shadow: 2px 2px 8px rgba(0,0,0,0.4);
            font-size: 1em;
            transition: background 0.3s, transform 0.2s;
        }
        body.dark-mode .floating-btn { background: #ffddd2; color: #333; }
        .floating-btn:hover { background: #e07a5f; transform: scale(1.05); }
        body.dark-mode .floating-btn:hover { background: #1a1a2e; color: #fff; }
        #openQuotePopup { right: 20px; }
        #openSlotMachine { right: 150px; }
        #openBlackjack { right: 280px; }
        #openRocket { right: 410px; }

        /* Pop-Up Windows */
        .popup { position: fixed; top: 50px; left: 50px; background: #fff; border: 2px solid #3d405b; border-radius: 10px; z-index: 10000; box-shadow: 5px 5px 20px rgba(0,0,0,0.5); max-width: 90%; }
        body.dark-mode .popup { background: #333; border-color: #ffddd2; }
        .popup-header { background: #3d405b; color: #fff; padding: 8px; cursor: move; display: flex; justify-content: space-between; align-items: center; border-top-left-radius: 8px; border-top-right-radius: 8px; }
        body.dark-mode .popup-header { background: #1a1a2e; }
        .popup-header .popup-title { font-weight: bold; }
        .popup-header button { background: transparent; border: none; color: #fff; font-size: 1em; cursor: pointer; margin-left: 5px; }
        .popup-content { padding: 15px; }
        body.dark-mode .popup-content { color: #ddd; }
        .popup .hidden { display: none; }

        /* Enhanced Casino Game Styles */
        /* Slot Machine Popup */
        #slotMachinePopup { width: 450px; background: linear-gradient(135deg, #ffeb3b, #ff5722); border-color: #ff9800; border-radius: 15px; box-shadow: 0 0 20px rgba(255, 165, 0, 0.5); }
        #slotDisplay { display: flex; justify-content: center; gap: 15px; font-size: 4em; margin: 20px 0; background: rgba(0,0,0,0.1); padding: 15px; border-radius: 10px; box-shadow: inset 0 0 10px rgba(0,0,0,0.3); }
        .slot-reel { width: 80px; height: 80px; text-align: center; line-height: 80px; background: linear-gradient(#ffffff, #e0e0e0); border-radius: 10px; border: 2px solid #ffd700; box-shadow: 0 4px 10px rgba(0,0,0,0.2); font-weight: bold; color: #d32f2f; }
        body.dark-mode .slot-reel { background: linear-gradient(#555, #333); color: #ffeb3b; }
        .slot-reel.spinning { animation: spinReel 0.3s linear infinite; background: linear-gradient(#fff, #ffeb3b); }
        @keyframes spinReel { 0% { transform: translateY(-100%) rotate(0deg); } 100% { transform: translateY(100%) rotate(360deg); } }
        #slotBetInput { margin: 15px 0; padding: 10px; font-size: 1.1em; border-radius: 8px; border: 2px solid #ff9800; background: rgba(255,255,255,0.9); }
        body.dark-mode #slotBetInput { background: #444; color: #ddd; }

        /* Blackjack Popup */
        #blackjackPopup { width: 550px; background: linear-gradient(135deg, #2e7d32, #4caf50); border-color: #388e3c; border-radius: 15px; box-shadow: 0 0 20px rgba(76, 175, 80, 0.5); }
        #blackjackHands { display: flex; justify-content: space-between; margin: 20px 0; gap: 15px; }
        .hand { width: 48%; padding: 15px; background: rgba(255,255,255,0.9); border-radius: 10px; border: 2px solid #fff; box-shadow: 0 4px 10px rgba(0,0,0,0.2); font-size: 1.2em; color: #1b5e20; background-image: url('https://www.transparenttextures.com/patterns/cardboard-flat.png'); }
        body.dark-mode .hand { background: rgba(61, 64, 91, 0.9); color: #ddd; border-color: #ffddd2; }
        #blackjackResult { margin-top: 15px; font-weight: bold; color: #fff; text-shadow: 1px 1px 2px #000; }
        body.dark-mode #blackjackResult { color: #ffddd2; }

        /* Rocket Game Popup */
        #rocketPopup { width: 450px; background: linear-gradient(135deg, #0288d1, #4fc3f7); border-color: #0277bd; border-radius: 15px; box-shadow: 0 0 20px rgba(2, 136, 209, 0.5); }
        #rocketDisplay { font-size: 2em; text-align: center; margin: 20px 0; color: #fff; background: rgba(0,0,0,0.2); padding: 15px; border-radius: 10px; position: relative; overflow: hidden; }
        body.dark-mode #rocketDisplay { color: #ffddd2; }
        #rocketDisplay::before { content: ''; position: absolute; top: -50%; left: 50%; width: 20px; height: 100px; background: #ffeb3b; transform: translateX(-50%) rotate(45deg); animation: rocketTrail 1s infinite linear; }
        @keyframes rocketTrail { 0% { top: 100%; } 100% { top: -50%; } }
        #rocketMultiplier { font-size: 3.5em; color: #ffeb3b; text-shadow: 0 0 10px #ff5722; }
        #rocketResult { margin-top: 15px; font-weight: bold; color: #fff; text-shadow: 1px 1px 2px #000; }
        body.dark-mode #rocketResult { color: #ffddd2; }

        /* Shared Casino Styles */
        .casino-btn { padding: 10px 20px; margin: 5px; background: linear-gradient(to right, #ff9800, #f44336); border: none; color: #fff; border-radius: 8px; cursor: pointer; transition: transform 0.2s, box-shadow 0.2s; font-size: 1.1em; box-shadow: 0 2px 5px rgba(0,0,0,0.3); }
        body.dark-mode .casino-btn { background: linear-gradient(to right, #ffddd2, #1a1a2e); }
        .casino-btn:hover { background: linear-gradient(to right, #f44336, #ff9800); transform: scale(1.05); box-shadow: 0 4px 10px rgba(0,0,0,0.4); }
        body.dark-mode .casino-btn:hover { background: linear-gradient(to right, #1a1a2e, #ffddd2); }
        .casino-input { padding: 10px; margin: 5px; border-radius: 8px; font-size: 1.1em; border: 2px solid #fff; background: rgba(255,255,255,0.9); }
        body.dark-mode .casino-input { background: #444; color: #ddd; border-color: #ffddd2; }
    </style>
</head>
<body>
    <!-- Mode Toggle -->
    <button id="mode-toggle">Toggle Dark Mode</button>

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
                <svg class="champagne-glasses" viewBox="0 0 60 60" fill="none" stroke="#f4f1de" stroke-width="2">
                    <path d="M15 15 L15 35 Q15 40 20 40 L25 40" />
                    <path d="M25 40 L25 50" />
                    <circle cx="25" cy="50" r="5" />
                    <path d="M45 15 L45 35 Q45 40 40 40 L35 40" />
                    <path d="M35 40 L35 50" />
                    <circle cx="35" cy="50" r="5" />
                    <path d="M25 35 Q30 30 35 35" stroke-dasharray="5,5" />
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
                    <svg class="champagne-glasses" style="width: 40px; height: 40px;" viewBox="0 0 60 60" fill="none" stroke="#3d405b" stroke-width="2">
                        <path d="M15 15 L15 35 Q15 40 20 40 L25 40" />
                        <path d="M25 40 L25 50" />
                        <circle cx="25" cy="50" r="5" />
                        <path d="M45 15 L45 35 Q45 40 40 40 L35 40" />
                        <path d="M35 40 L35 50" />
                        <circle cx="35" cy="50" r="5" />
                        <path d="M25 35 Q30 30 35 35" stroke-dasharray="5,5" />
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
            <div id="slotBankDisplay" style="font-weight:bold; margin-bottom:10px; color: #fff; text-shadow: 1px 1px 2px #000;">Bank: $1000</div>
            <div id="slotDisplay">
                <div class="slot-reel" id="slot1">?</div>
                <div class="slot-reel" id="slot2">?</div>
                <div class="slot-reel" id="slot3">?</div>
            </div>
            <input type="number" id="slotBetInput" class="casino-input" min="1" max="500" value="10" placeholder="Bet ($1-$500)" />
            <button id="slotSpinButton" class="casino-btn">Spin</button>
            <button id="slotCashOutButton" class="casino-btn">Cash Out</button>
            <div id="slotResult" style="margin-top:10px; font-weight:bold; color: #fff; text-shadow: 1px 1px 2px #000;"></div>
        </div>
    </div>
    
    <!-- Pop-Up: Blackjack Game -->
    <div id="blackjackPopup" class="popup" style="display:none;">
        <div class="popup-header">
            <span class="popup-title">Blackjack</span>
            <button class="popup-close">X</button>
        </div>
        <div class="popup-content">
            <div id="blackjackBankDisplay" style="font-weight:bold; margin-bottom:10px; color: #fff; text-shadow: 1px 1px 2px #000;">Bank: $1000</div>
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
            <div id="rocketBankDisplay" style="font-weight:bold; margin-bottom:10px; color: #fff; text-shadow: 1px 1px 2px #000;">Bank: $1000</div>
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
        
        // Simulated booked dates
        const bookedDates = ["11/15/2024", "11/20/2024", "12/01/2024"];
        
        // Mode Toggle
        $("#mode-toggle").click(function() {
            $("body").toggleClass("dark-mode");
            $(this).text($("body").hasClass("dark-mode") ? "Toggle Light Mode" : "Toggle Dark Mode");
        });

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
            const slotEmojis = ["🍒", "🍋", "🍊", "🍇", "💎"];
            const slotPayScale = {
                "🍒": { triple: 5, two: 1.5, prob: 0.3 },
                "🍋": { triple: 10, two: 2, prob: 0.25 },
                "🍊": { triple: 15, two: 2, prob: 0.2 },
                "🍇": { triple: 25, two: 2, prob: 0.15 },
                "💎": { triple: 50, two: 2, prob: 0.1 }
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
                if (r < 0.5) return 1.1 + Math.random() * 3.9;
                if (r < 0.8) return 6 + Math.random() * 4;
                if (r < 0.95) return 20 + Math.random() * 80;
                if (r < 0.99) return 200 + Math.random() * 300;
                return 500 + Math.random() * 500;
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
                "A bartender can shake up to 100 cocktails in an hour!",
                "The shortest war in history lasted 38 minutes.",
                "Champagne was originally a mistake—winemakers thought the bubbles meant it had gone bad.",
                "The world’s oldest known recipe is for beer, dating back 4,000 years.",
                "In the 1800s, bartenders used to wear bow ties because they were harder to grab in a bar fight.",
                "The term 'mixology' was coined in 1872!",
                "Casinos in Las Vegas use chips to make you forget you're spending real money.",
                "The fastest bartender in the world can open 12 bottles in under a minute."
            ];
            
            function updateFunFact() {
                var fact = facts[Math.floor(Math.random() * facts.length)];
                $("#fun-fact-box").fadeOut(500, function(){
                    $(this).text("Did you know? " + fact).fadeIn(500);
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
