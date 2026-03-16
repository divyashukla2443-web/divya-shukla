<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Drury 188-189 – Specialty Coffee & Brunch in Covent Garden</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        h1, h2, h3 {
            font-family: 'Playfair Display', serif;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            padding: 0.5rem 0;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 700;
            color: #8B4513;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #8B4513;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: #8B4513;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #333;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.4)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800"><rect fill="%23f8f4f0" width="1200" height="800"/><text x="50%" y="50%" font-family="serif" font-size="120" fill="%23d4a574" text-anchor="middle" dy=".3em">Drury 188-189</text></svg>');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
        }

        .hero-content h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            margin-bottom: 1.5rem;
            font-weight: 600;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 2rem;
        }

        .btn {
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: 500;
            text-decoration: none;
            display: inline-block;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .btn-primary {
            background: #8B4513;
            color: white;
        }

        .btn-primary:hover {
            background: #A0522D;
            transform: translateY(-2px);
        }

        .btn-secondary {
            background: rgba(255,255,255,0.2);
            color: white;
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            background: rgba(255,255,255,0.3);
            transform: translateY(-2px);
        }

        /* Sections */
        section {
            padding: 5rem 0;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* About Section */
        .about {
            background: #f8f4f0;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text h2 {
            font-size: 2.5rem;
            color: #8B4513;
            margin-bottom: 1.5rem;
        }

        .about-text p {
            font-size: 1.1rem;
            color: #666;
            margin-bottom: 1.5rem;
        }

        .about-image {
            height: 400px;
            background: linear-gradient(45deg, #d4a574, #f4e4d1);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: rgba(255,255,255,0.1);
        }

        /* Menu Section */
        .menu {
            background: white;
        }

        .menu h2 {
            text-align: center;
            font-size: 3rem;
            color: #8B4513;
            margin-bottom: 3rem;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .menu-category {
            background: #f8f4f0;
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .menu-category h3 {
            font-size: 1.8rem;
            color: #8B4513;
            margin-bottom: 1.5rem;
        }

        .menu-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid rgba(0,0,0,0.1);
        }

        .menu-item:last-child {
            border-bottom: none;
            margin-bottom: 0;
        }

        .menu-item-name {
            font-weight: 500;
        }

        .menu-item-price {
            color: #8B4513;
            font-weight: 600;
        }

        /* Gallery Section */
        .gallery {
            background: #f8f4f0;
        }

        .gallery h2 {
            text-align: center;
            font-size: 3rem;
            color: #8B4513;
            margin-bottom: 3rem;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .gallery-item {
            height: 300px;
            background-size: cover;
            background-position: center;
            border-radius: 20px;
            position: relative;
            overflow: hidden;
            transition: transform 0.3s ease;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        /* Visit Section */
        .visit {
            background: white;
        }

        .visit-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .visit-info h2 {
            font-size: 2.5rem;
            color: #8B4513;
            margin-bottom: 2rem;
        }

        .visit-details {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .visit-detail {
            display: flex;
            align-items: flex-start;
            gap: 1rem;
        }

        .visit-icon {
            width: 50px;
            height: 50px;
            background: #8B4513;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
            flex-shrink: 0;
        }

        #map {
            height: 400px;
            border-radius: 20px;
            border: none;
        }

        /* Contact Section */
        .contact {
            background: #f8f4f0;
        }

        .contact h2 {
            text-align: center;
            font-size: 3rem;
            color: #8B4513;
            margin-bottom: 3rem;
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: #333;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            font-family: inherit;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #8B4513;
        }

        .form-group textarea {
            height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background: #2c1810;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu {
                display: block;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .about-content,
            .visit-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .menu-grid {
                grid-template-columns: 1fr;
            }

            .container {
                padding: 0 1rem;
            }

            section {
                padding: 3rem 0;
            }
        }

        @media (max-width: 480px) {
            .nav-container {
                padding: 0 1rem;
            }

            .hero-content h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="nav-container">
            <div class="logo">Drury 188-189</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#gallery">Gallery</a></li>
                <li><a href="#visit">Visit</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="mobile-menu">
                <i class="fas fa-bars"></i>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Drury 188-189</h1>
            <p>Specialty Coffee & Brunch in Covent Garden</p>
            <div class="hero-buttons">
                <a href="#menu" class="btn btn-primary">View Menu</a>
                <a href="#visit" class="btn btn-secondary">Visit Us</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text">
                    <h2>A Cozy Haven in Covent Garden</h2>
                    <p>Nestled on the charming Drury Lane, Drury 188-189 is more than just a café—it's a warm embrace in the heart of London's theatre district. Our specialty coffee is roasted in small batches, and our brunch dishes are crafted with seasonal, locally-sourced ingredients.</p>
                    <p>Step into our cozy space with exposed brick walls, soft lighting, and the comforting aroma of freshly brewed coffee. Whether you're starting your day or taking a moment to unwind, Drury 188-189 is your perfect London retreat.</p>
                </div>
                <div class="about-image">
                    <i class="fas fa-coffee"></i>
                </div>
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section id="menu" class="menu">
        <div class="container">
            <h2 class="section-title">Our Menu</h2>
            <div class="menu-grid">
                <div class="menu-category">
                    <h3>Breakfast & Brunch</h3>
                    <div class="menu-item">
                        <span class="menu-item-name">Avocado Toast</span>
                        <span class="menu-item-price">£9.50</span>
                    </div>
                    <div class="menu-item">
                        <span class="menu-item-name">Eggs Benedict</span>
                        <span class="menu-item-price">£12.00</span>
                    </div>
                    <div class="menu-item">
                        <span class="menu-item-name">Full English Breakfast</span>
                        <span class="menu-item-price">£14.50</span>
                    </div>
                    <div class="menu-item">
                        <span class="menu-item-name">Smoked Salmon Bagel</span>
                        <span class="menu-item-price">£11.00</span>
                    </div>
                </div>
                <div class="menu-category">
                    <h3>Coffee & Drinks</h3>
                    <div class="menu-item">
                        <span class="menu-item-name">Single Origin Espresso</span>
                        <span class="menu-item-price">£3.00</span>
                    </div>
                    <div class="menu-item">
                        <span class="menu-item-name">Flat White</span>
                        <span class="menu-item-price">£4.20</span>
                    </div>
                    <div class="menu-item">
                        <span class="menu-item-name">Pour Over Coffee</span>
                        <span class="menu-item-price">£5.00</span>
                    </div>
                    <div class="menu-item">
                        <span class="menu-item-name">Fresh Orange Juice</span>
                        <span class="menu-item-price">£4.50</span>
                    </div>
                </div>
                <div class="menu-category">
                    <h3>Pancakes & Desserts</h3>
                    <div class="menu-item">
                        <span class="menu-item-name">Classic Buttermilk Pancakes</span>
                        <span class="menu-item-price">£10.50</span>
                    </div>
                    <div class="menu-item">
                        <span class="menu-item-name">Nutella Stuffed Pancakes</span>
                        <span class="menu-item-price">£12.00</span>
                    </div>
                    <div class="menu-item">
                        <span class="menu-item-name">Lemon Drizzle Cake</span>
                        <span class="menu-item-price">£5.50</span>
                    </div>
                    <div class="menu-item">
                        <span class="menu-item-name">Chocolate Brownie</span>
                        <span class="menu-item-price">£6.00</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="gallery">
        <div class="container">
            <h2 class="section-title">Gallery</h2>
            <div class="gallery-grid">
                <div class="gallery-item" style="background-image: linear-gradient(45deg, #d4a574, #f4e4d1);"></div>
                <div class="gallery-item" style="background-image: linear-gradient(45deg, #8B4513, #A0522D);"></div>
                <div class="gallery-item" style="background-image: linear-gradient(45deg, #f8f4f0, #e8d9c6);"></div>
                <div class="gallery-item" style="background-image: linear-gradient(45deg, #d4a574, #f4e4d1);"></div>
                <div class="gallery-item" style="background-image: linear-gradient(45deg, #8B4513, #A0522D);"></div>
                <div class="gallery-item" style="background-image: linear-gradient(45deg, #f8f4f0, #e8d9c6);"></div>
            </div>
        </div>
    </section>

    <!-- Visit Section -->
    <section id="visit" class="visit">
        <div class="container">
            <div class="visit-content">
                <div class="visit-info">
                    <h2>Visit Us</h2>
                    <div class="visit-details">
                        <div class="visit-detail">
                            <div class="visit-icon">
                                <i class="fas fa-map-marker-alt"></i>
                            </div>
                            <div
