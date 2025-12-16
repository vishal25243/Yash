<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Holla Homes Inspired - Full Site</title>
    <style>
        /* Reset and Base */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Arial', sans-serif; line-height: 1.6; color: #333; background: #f4f4f4; }
        a { text-decoration: none; color: inherit; }
        img { max-width: 100%; height: auto; }
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }

        /* Header & Nav */
        header { background: #fff; box-shadow: 0 2px 5px rgba(0,0,0,0.1); position: sticky; top: 0; z-index: 100; }
        nav { display: flex; justify-content: space-between; align-items: center; padding: 1rem 2rem; }
        .logo { font-size: 1.8rem; font-weight: bold; color: #007bff; }
        .nav-links { list-style: none; display: flex; gap: 1.5rem; }
        .nav-links li { display: inline; }
        .nav-links a { padding: 0.5rem 1rem; transition: all 0.3s; border-radius: 5px; }
        .nav-links a:hover, .nav-links a.active { background: #007bff; color: white; }
        .menu-toggle { display: none; font-size: 1.5rem; cursor: pointer; }

        /* Sections */
        section { padding: 5rem 0; display: none; } /* Hide all sections by default */
        #home { display: block; } /* Show Home by default */
        h2 { text-align: center; margin-bottom: 3rem; font-size: 2.5rem; color: #007bff; }
        h3 { margin-bottom: 1rem; font-size: 1.8rem; }

        /* Hero */
        .hero { background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://via.placeholder.com/1920x600?text=Luxury+Homes') center/cover; height: 70vh; display: flex; align-items: center; justify-content: center; text-align: center; color: white; animation: fadeIn 2s; }
        .hero-content h1 { font-size: 3.5rem; margin-bottom: 1rem; }
        .hero-content p { font-size: 1.3rem; margin-bottom: 2rem; }
        .btn { padding: 0.8rem 1.8rem; background: #007bff; color: white; border: none; border-radius: 5px; cursor: pointer; transition: all 0.3s; font-size: 1rem; }
        .btn:hover { background: #0056b3; transform: scale(1.05); }

        /* Services */
        .services { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; }
        .service { background: #fff; padding: 2rem; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.1); text-align: center; transition: transform 0.3s; }
        .service:hover { transform: translateY(-10px); }
        .service h3 { color: #007bff; }
        .service ul { list-style: none; text-align: left; margin-top: 1rem; }
        .service li { margin: 0.5rem 0; padding-left: 1rem; position: relative; }
        .service li::before { content: '✓'; color: #28a745; position: absolute; left: 0; }

        /* Properties */
        .properties { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; }
        .property { background: #fff; border-radius: 10px; overflow: hidden; box-shadow: 0 4px 10px rgba(0,0,0,0.1); transition: transform 0.3s; }
        .property:hover { transform: scale(1.05); }
        .property img { width: 100%; height: 200px; object-fit: cover; }
        .property-content { padding: 1.5rem; }
        .property h4 { color: #007bff; margin-bottom: 0.5rem; }
        .property p { font-size: 0.9rem; color: #666; margin-bottom: 0.5rem; }
        .property .price { font-weight: bold; color: #28a745; }

        /* Filters */
        .filters { display: flex; justify-content: center; gap: 1rem; margin-bottom: 2rem; flex-wrap: wrap; }
        .filters select, .filters input { padding: 0.5rem; border: 1px solid #ddd; border-radius: 5px; }

        /* Testimonials */
        .testimonials { position: relative; overflow: hidden; }
        .testimonial-slider { display: flex; transition: transform 0.5s; }
        .testimonial { min-width: 100%; padding: 2rem; background: #fff; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.1); text-align: center; }
        .testimonial p { font-style: italic; margin-bottom: 1rem; }
        .testimonial cite { font-weight: bold; color: #007bff; }
        .slider-btn { position: absolute; top: 50%; transform: translateY(-50%); background: #007bff; color: white; border: none; padding: 0.5rem; cursor: pointer; border-radius: 50%; }
        .slider-btn.prev { left: 10px; }
        .slider-btn.next { right: 10px; }

        /* About */
        .about { display: flex; align-items: center; gap: 2rem; flex-wrap: wrap; }
        .about img { width: 300px; border-radius: 10px; }
        .about-content { flex: 1; }

        /* Contact */
        .contact-form { max-width: 600px; margin: 0 auto; background: #fff; padding: 2rem; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
        .contact-form input, .contact-form select, .contact-form textarea { width: 100%; padding: 0.8rem; margin-bottom: 1rem; border: 1px solid #ddd; border-radius: 5px; }
        .contact-form button { width: 100%; }

        /* Blog */
        .blog { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; }
        .blog-post { background: #fff; padding: 1.5rem; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
        .blog-post h4 { color: #007bff; }
        .blog-post p { margin-bottom: 1rem; }

        /* Footer */
        footer { background: #333; color: white; text-align: center; padding: 2rem; }
        footer .footer-links { display: flex; justify-content: center; gap: 2rem; margin-bottom: 1rem; flex-wrap: wrap; }
        footer a { color: #ccc; transition: color 0.3s; }
        footer a:hover { color: white; }

        /* Modal */
        .modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); justify-content: center; align-items: center; z-index: 1000; }
        .modal-content { background: white; padding: 2rem; border-radius: 10px; max-width: 600px; width: 90%; text-align: center; position: relative; }
        .close { position: absolute; top: 10px; right: 20px; font-size: 2rem; cursor: pointer; }

        /* Animations */
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        .fade-in { animation: fadeIn 1s; }

        /* Responsive Design */
        @media (max-width: 768px) {
            nav { padding: 1rem; }
            .nav-links { display: none; flex-direction: column; position: absolute; top: 100%; left: 0; width: 100%; background: white; box-shadow: 0 2px 5px rgba(0,0,0,0.1); padding: 1rem 0; }
            .nav-links.active { display: flex; }
            .menu-toggle { display: block; }
            .hero { height: 50vh; }
            .hero-content h1 { font-size: 2.5rem; }
            .hero-content p { font-size: 1.1rem; }
            .services, .properties, .blog { grid-template-columns: 1fr; }
            .about { flex-direction: column; text-align: center; }
            .filters { flex-direction: column; align-items: center; }
            .testimonial-slider { flex-direction: column; }
            .footer-links { flex-direction: column; gap: 1rem; }
            section { padding: 3rem 0; }
            h2 { font-size: 2rem; }
        }

        @media (max-width: 480px) {
            .hero-content h1 { font-size: 2rem; }
            .hero-content p { font-size: 1rem; }
            .btn { padding: 0.6rem 1.4rem; font-size: 0.9rem; }
            .service, .property, .blog-post { padding: 1rem; }
            .modal-content { padding: 1rem; }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <div class="logo">Holla Homes</div>
            <ul class="nav-links">
                <li><a href="#home" class="active" onclick="showSection('home')">Home</a></li>
                <li><a href="#services" onclick="showSection('services')">Services</a></li>
                <li><a href="#properties" onclick="showSection('properties')">Properties</a></li>
                <li><a href="#about" onclick="showSection('about')">About</a></li>
                <li><a href="#blog" onclick="showSection('blog')">Blog</a></li>
                <li><a href="#contact" onclick="showSection('contact')">Contact</a></li>
            </ul>
            <div class="menu-toggle" onclick="toggleMenu()">&#9776;</div>
        </nav>
    </header>

    <!-- Hero -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Find Your Dream Home</h1>
            <p>Expert interior design, architecture, and property services for modern living.</p>
            <button class="btn" onclick="showSection('services')">Explore Services</button>
        </div>
    </section>

    <!-- Services -->
    <section id="services" class="container">
        <h2>Our Services</h2>
        <div class="services">
            <div class="service">
                <h3>Interior Design</h3>
                <p>Transform spaces with custom designs.</p>
                <ul>
                    <li>Modern Style</li>
                    <li>Traditional Style</li>
                    <li>Minimalist Style</li>
                    <li>Eco-Friendly Options</li>
                </ul>
                <button class="btn" onclick="alert('Interior Design selected!')">Get Quote</button>
            </div>
            <div class="service">
                <h3>Architecture Planning</h3>
                <p>Full planning from concept to completion.</p>
                <ul>
                    <li>Residential Buildings</li>
                    <li>Commercial Spaces</li>
                    <li>Renovations</li>
                    <li>Permits & Blueprints</li>
                </ul>
                <button class="btn" onclick="alert('Architecture Planning selected!')">Get Quote</button>
            </div>
            <div class="service">
                <h3>Property Management</h3>
                <p>Manage and maintain your properties.</p>
                <ul>
                    <li>Rental Services</li>
                    <li>Maintenance</li>
                    <li>Legal Support</li>
                    <li>Investment Advice</li>
                </ul>
                <button class="btn" onclick="alert('Property Management selected!')">Get Quote</button>
            </div>
            <div class="service">
                <h3>Consultation</h3>
                <p>Free expert advice for your projects.</p>
                <ul>
                    <li>Virtual Consult</li>
                    <li>In-Person Meet</li>
                    <li>Project Assessment</li>
                    <li>Budget Planning</li>
                </ul>
                <button class="btn" onclick="alert('Consultation selected!')">Book Now</button>
            </div>
        </div>
    </section>

    <!-- Properties -->
    <section id="properties" class="container">
        <h2>Featured Properties</h2>
        <div class="filters">
            <input type="text" id="search" placeholder="Search properties...">
            <select id="type">
                <option value="">All Types</option>
                <option value="Villa">Villa</option>
                <option value="Apartment">Apartment</option>
                <option value="Office">Office</option>
            </select>
            <select id="price">
                <option value="">All Prices</option>
                <option value="low">Under ₹50L</option>
                <option value="mid">₹50L - ₹1Cr</option>
                <option value="high">Over ₹1Cr</option>
            </select>
        </div>
        <div class="properties" id="propertyList">
            <div class="property" data-type="Villa" data-price="mid" onclick="openModal('Luxury Villa', '3BHK, Garden, Pool. Price: ₹75L. Features: Gym, Parking.')">
                <img src="https://via.placeholder.com/300x200?text=Luxury+Villa" alt="Luxury Villa">
                <div class="property-content">
                    <h4>Luxury Villa</h4>
                    <p>3BHK with garden and pool.</p>
                    <p class="price">₹75L</p>
                </div>
            </div>
            <div class="property" data-type="Apartment" data-price="low" onclick="openModal('Cozy Apartment', '2BHK, Balcony. Price: ₹35L. Features: Security, AC.')">
                <img src="https://via.placeholder.com/300x200?text=Cozy+Apartment" alt="Cozy Apartment">
                <div class="property-content">
                    <h4>Cozy Apartment</h4>
                    <p>2BHK with balcony.</p>
                    <p class="price">₹35L</p>
                </div>
            </div>
            <div class="property" data-type="Office" data-price="high" onclick="openModal('Modern Office', 'Commercial space. Price: ₹1.5Cr. Features: Conference Room, Parking.')">
                <img src="https://via.placeholder.com/300x200?text=Modern+Office" alt="Modern Office">
                <div class="property-content">
                    <h4>Modern Office</h4>
                    <p>Commercial space in city center.</p>
                    <p class="price">₹1.5Cr</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section id="testimonials" class="container">
        <h2>What Our Clients Say</h2>
        <div class="testimonials">
            <div class="testimonial-slider" id="slider">
                <div class="testimonial">
                    <p>"Holla Homes made our dream home a reality!"</p>
                    <cite>- John Doe</cite>
                </div>
                <div class="testimonial">
                    <p>"Excellent architecture services."</p>
                    <cite>- Jane Smith</cite>
                </div>
                <div class="testimonial">
                    <p>"Top-notch interior design."</p>
                    <cite>- Alex Johnson</cite>
                </div>
            </div>
            <button class="slider-btn prev" onclick="prevSlide()">&#10094;</button>
            <button class="slider-btn next" onclick="nextSlide()">&#10095;</button>
        </div>
    </section>

    <!-- About -->
    <section id="about" class="container">
        <h2>About Us</h2>
        <div class="about">
            <img src="https://via.placeholder.com/300x300?text=Team+Photo"
