<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Holla Homes Inspired - Home</title>
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

        /* Hero */
        .hero { background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://via.placeholder.com/1920x600?text=Luxury+Homes') center/cover; height: 70vh; display: flex; align-items: center; justify-content: center; text-align: center; color: white; animation: fadeIn 2s; }
        .hero-content h1 { font-size: 3.5rem; margin-bottom: 1rem; }
        .hero-content p { font-size: 1.3rem; margin-bottom: 2rem; }
        .btn { padding: 0.8rem 1.8rem; background: #007bff; color: white; border: none; border-radius: 5px; cursor: pointer; transition: all 0.3s; font-size: 1rem; }
        .btn:hover { background: #0056b3; transform: scale(1.05); }

        /* Footer */
        footer { background: #333; color: white; text-align: center; padding: 2rem; }
        footer .footer-links { display: flex; justify-content: center; gap: 2rem; margin-bottom: 1rem; flex-wrap: wrap; }
        footer a { color: #ccc; transition: color 0.3s; }
        footer a:hover { color: white; }

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
            .footer-links { flex-direction: column; gap: 1rem; }
        }

        @media (max-width: 480px) {
            .hero-content h1 { font-size: 2rem; }
            .hero-content p { font-size: 1rem; }
            .btn { padding: 0.6rem 1.4rem; font-size: 0.9rem; }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <div class="logo">Yash Architect</div>
            <ul class="nav-links">
                <li><a href="#home" class="active">Home</a></li>
                <li><a href="services.html">Services</a></li>
                <li><a href="#properties">Properties</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#blog">Blog</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="menu-toggle" onclick="toggleMenu()">&#9776;</div>
        </nav>
    </header>

    <!-- Hero -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Find Your Dream Home</h1>
            <p>Expert interior design, architecture, and property services for modern living.</p>
            <a href="services.html" class="btn">Explore Services</a>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-links">
            <a href="#home">Home</a>
            <a href="services.html">Services</a>
            <a href="#properties">Properties</a>
            <a href="#about">About</a>
            <a href="#blog">Blog</a>
            <a href="#contact">Contact</a>
        </div>
        <p>&copy; 2026 Holla Homes Inspired. All rights reserved.</p>
    </footer>

    <script>
        // Toggle mobile menu
        function toggleMenu() {
            document.querySelector('.nav-links').classList.toggle('active');
        }
    </script>
</body>
</html>
