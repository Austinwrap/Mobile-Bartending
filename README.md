<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Raise A Glass LLC - Event Bartending</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
    <!-- Styles -->
    <style>
        /* Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Typography */
        body {
            font-family: 'Montserrat', sans-serif;
            color: #333;
            background: linear-gradient(to bottom right, #ffdde1, #ee9ca7);
            background-size: cover;
            background-attachment: fixed;
        }

        h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 3.5em;
            color: #fff7e6;
            text-align: center;
            margin-bottom: 10px;
            text-shadow: 3px 3px 8px rgba(0, 0, 0, 0.5);
        }

        h2 {
            color: #3d405b;
            font-size: 2.5em;
            margin-bottom: 20px;
            text-align: center;
        }

        /* Header */
        .header {
            background: #3d405b;
            color: #f4f1de;
            padding: 60px 0;
            border-bottom: 4px solid #e07a5f;
            text-shadow: 2px 2px 5px #333;
            position: relative;
        }

        .header .tagline {
            text-align: center;
            font-size: 1.8em;
            color: #f2cc8f;
        }

        /* Navigation */
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

        .main-nav a:hover {
            color: #ffddd2;
        }

        /* Buttons */
        .btn {
            display: inline-block;
            background: linear-gradient(to right, #e07a5f, #3d405b);
            color: #fff;
            padding: 15px 30px;
            text-decoration: none;
            margin-top: 30px;
            border-radius: 12px;
            box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.3);
            transition: background 0.3s, box-shadow 0.3s;
            font-size: 1.2em;
        }

        .btn:hover {
            background: linear-gradient(to right, #3d405b, #e07a5f);
            box-shadow: 7px 7px 20px rgba(0, 0, 0, 0.4);
        }

        /* Columns for Old Mansion Vibe */
        .columns {
            position: absolute;
            height: 100%;
            width: 10%;
            background: rgba(255, 223, 211, 0.8);
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

        /* Sections */
        section {
            padding: 100px 0;
            text-align: center;
            background: rgba(255, 245, 238, 0.95);
            border: 4px solid #e07a5f;
            margin: 40px 0;
            box-shadow: 8px 8px 20px rgba(0, 0, 0, 0.3);
            border-radius: 25px;
        }

        .container {
            width: 80%;
            margin: 0 auto;
        }

        ul {
            list-style-type: none;
            margin: 40px 0;
            padding: 0;
        }

        ul li {
            font-size: 1.4em;
            margin-bottom: 20px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            box-shadow: 4px 4px 15px rgba(0, 0, 0, 0.2);
        }

        /* Footer */
        .footer {
            background-color: #3d405b;
            color: #ffddd2;
            padding: 40px 0;
            text-align: center;
            font-size: 1.1em;
            border-top: 4px solid #81b29a;
            box-shadow: 0 -4px 8px rgba(0, 0, 0, 0.3);
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

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                width: 90%;
            }

            .main-nav {
                position: relative;
                top: 0;
                width: 100%;
                padding: 10px 0;
            }

            .main-nav a {
                margin: 5px;
                font-size: 1em;
            }

            .columns {
                display: none;
            }

            .btn {
                padding: 12px 25px;
                font-size: 1em;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header" id="home">
        <div class="container">
            <h1>Raise A Glass LLC</h1>
            <p class="tagline">Mobile Bartending Services for All Occasions</p>
        </div>
    </header>

    <!-- Navigation -->
    <nav class="main-nav">
        <a href="#home">Home</a>
        <a href="#services">Services</a>
        <a href="#packages">Packages</a>
        <a href="#contact">Contact Us</a>
    </nav>

    <!-- Columns for Old Mansion Vibe -->
    <div class="columns left-column"></div>
    <div class="columns right-column"></div>

    <!-- Main Content -->
    <main>
        <!-- Services Section -->
        <section class="services" id="services">
            <div class="container">
                <h2>Our Services</h2>
                <ul>
                    <li><strong><i class="fas fa-user-tie"></i> Professional Bartending Staff:</strong> Trained bartenders to make your event unforgettable.</li>
                    <li><strong><i class="fas fa-cocktail"></i> Signature Cocktails & Specialty Menus:</strong> Crafted with care for an exceptional experience.</li>
                    <li><strong><i class="fas fa-coffee"></i> Hot Coffee & Tea Bar:</strong> Cozy drinks to keep everyone warm and happy.</li>
                </ul>
            </div>
        </section>

        <!-- Packages Section -->
        <section class="packages" id="packages">
            <div class="container">
                <h2>Our Packages</h2>
                <ul>
                    <li><strong><i class="fas fa-user-tie"></i> Bartender Only:</strong> You provide everything (bar, alcohol, ice, etc.). Raeanne bartends for up to 100 guests. Call for pricing.</li>
                    <li><strong><i class="fas fa-glass-whiskey"></i> Essentials Package:</strong> We provide cups, straws, mixers, garnishes, ice, and a display. You provide the alcohol. Call for pricing.</li>
                    <li><strong><i class="fas fa-cocktail"></i> Ultimate Package:</strong> Includes everything in the Essentials Package plus unlimited water, lemonade, iced tea, and a coffee & tea bar. Call for pricing.</li>
                    <li><strong><i class="fas fa-wine-glass-alt"></i> Farmhouse Experience Package:</strong> Includes everything in the Ultimate Package plus our stunning old farmhouse wood bar. We literally bring the bar to your event, offering a rustic yet elegant experience that guests will never forget. Call for pricing.</li>
                    <li><strong><i class="fas fa-users"></i> Additional Bartender:</strong> For events over 100 guests, an additional bartender will be provided. Alcohol is always provided by the client. Call for pricing.</li>
                </ul>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="contact" id="contact">
            <div class="container">
                <h2>Contact Us</h2>
                <p>Call: Raeanne (860) 517-6602</p>
                <p>Email: <a href="mailto:raiseaglassservices@gmail.com">raiseaglassservices@gmail.com</a></p>
                <a href="#packages" class="btn">Book Now</a>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2024 Raise A Glass LLC - Mobile Event Bartending</p>
        </div>
    </footer>
</body>
</html>
