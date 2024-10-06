
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Raise A Glass LLC - Mobile Bartending</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">
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
            background-color: #fafafa;
        }

        h1 {
            font-family: 'Great Vibes', cursive;
            font-size: 3em;
            color: #8B5E3C;
            text-align: center;
            margin-bottom: 10px;
        }

        /* Header */
        .header {
            background-color: #fff;
            padding: 20px 0;
            border-bottom: 1px solid #ddd;
        }

        .header .logo {
            text-align: center;
            margin-bottom: 10px;
        }

        .header .logo img {
            height: 80px;
        }

        .header .tagline {
            text-align: center;
            font-size: 1.2em;
            color: #555;
        }

        /* Navigation */
        .main-nav {
            background-color: #8B5E3C;
            text-align: center;
            padding: 10px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .main-nav a {
            color: #fff;
            text-decoration: none;
            margin: 0 15px;
            font-size: 1.1em;
        }

        .main-nav a:hover {
            border-bottom: 2px solid #fff;
        }

        /* Buttons */
        .btn {
            display: inline-block;
            background-color: #8B5E3C;
            color: #fff;
            padding: 10px 20px;
            text-decoration: none;
            margin-top: 20px;
            border-radius: 5px;
        }

        .btn:hover {
            background-color: #A76F50;
        }

        /* Sections */
        section {
            padding: 40px 0;
            text-align: center;
        }

        .container {
            width: 80%;
            margin: 0 auto;
        }

        ul {
            list-style-type: none;
            margin: 20px 0;
        }

        ul li {
            font-size: 1.1em;
            margin-bottom: 10px;
        }

        /* Footer */
        .footer {
            background-color: #333;
            color: #ccc;
            padding: 20px 0;
            text-align: center;
            font-size: 0.9em;
        }

        .footer a {
            color: #ccc;
            text-decoration: none;
        }

        .footer a:hover {
            text-decoration: underline;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                width: 90%;
            }

            .main-nav a {
                display: block;
                margin: 10px 0;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header" id="home">
        <div class="container">
            <div class="logo">
                <img src="logo.png" alt="Raise A Glass LLC">
            </div>
            <h1>Raise A Glass LLC</h1>
            <p class="tagline">Mobile Bartending Services for All Occasions</p>
        </div>
    </header>

    <!-- Navigation -->
    <nav class="main-nav">
        <a href="#services">Services</a>
        <a href="#packages">Packages</a>
        <a href="#contact">Contact</a>
    </nav>

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
                <a href="#contact" class="btn">Book Now</a>
            </div>
        </section>

        <!-- Packages Section -->
        <section class="packages" id="packages">
            <div class="container">
                <h2>Our Packages</h2>
                <ul>
                    <li><strong><i class="fas fa-beer"></i> Beer & Wine Package:</strong> Enjoy unlimited beer and wine service for your guests. Perfect for any event looking for simplicity and elegance.</li>
                    <li><strong><i class="fas fa-glass-cheers"></i> Signature Cocktails Package:</strong> Delight your guests with a selection of signature cocktails crafted to perfection. Includes two seasonal specialty drinks.</li>
                    <li><strong><i class="fas fa-water"></i> Hydration Station:</strong> Add unlimited water, lemonade, and iced tea for just $100.</li>
                    <li><strong><i class="fas fa-mug-hot"></i> Hot Coffee & Tea Bar:</strong> Warm up your guests with our coffee and tea station, available for $250.</li>
                </ul>
                <a href="#contact" class="btn">See Packages</a>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="contact" id="contact">
            <div class="container">
                <h2>Contact Us</h2>
                <p>Call: (555) 555-5555</p>
                <p>Email: <a href="mailto:info@raiseaglass.com">info@raiseaglass.com</a></p>
                <form action="submit_inquiry.php" method="post">
                    <label for="name">Name:</label>
                    <input type="text" id="name" name="name" required>
                    
                    <label for="email">Email:</label>
                    <input type="email" id="email" name="email" required>
                    
                    <label for="message">Message:</label>
                    <textarea id="message" name="message" required></textarea>
                    
                    <button type="submit" class="btn">Send Message</button>
                </form>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2024 Raise A Glass LLC - Mobile Event Bartending</p>
            <p>Follow us:
                <a href="#"><i class="fab fa-instagram"></i> Instagram</a> |
                <a href="#"><i class="fab fa-facebook"></i> Facebook</a>
            </p>
        </div>
    </footer>
</body>
</html>
