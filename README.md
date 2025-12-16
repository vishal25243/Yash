 <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Holla Homes Inspired</title>

<!-- ====== ORIGINAL COMBINED CSS (INDEX + SERVICES) ====== -->
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:Arial,sans-serif;line-height:1.6;color:#333;background:#f4f4f4}
a{text-decoration:none;color:inherit}
img{max-width:100%;height:auto}
.container{max-width:1200px;margin:0 auto;padding:0 20px}

header{background:#fff;box-shadow:0 2px 5px rgba(0,0,0,.1);position:sticky;top:0;z-index:100}
nav{display:flex;justify-content:space-between;align-items:center;padding:1rem 2rem}
.logo{font-size:1.8rem;font-weight:bold;color:#007bff}
.nav-links{list-style:none;display:flex;gap:1.5rem}
.nav-links a{padding:.5rem 1rem;transition:.3s;border-radius:5px}
.nav-links a:hover,.nav-links a.active{background:#007bff;color:#fff}
.menu-toggle{display:none;font-size:1.5rem;cursor:pointer}

.hero{background:linear-gradient(rgba(0,0,0,.5),rgba(0,0,0,.5)),url('https://via.placeholder.com/1920x600?text=Luxury+Homes') center/cover;height:70vh;display:flex;align-items:center;justify-content:center;text-align:center;color:#fff}
.hero h1{font-size:3.5rem;margin-bottom:1rem}
.hero p{font-size:1.3rem;margin-bottom:2rem}
.btn{padding:.8rem 1.8rem;background:#007bff;color:#fff;border-radius:5px;display:inline-block;transition:.3s}
.btn:hover{background:#0056b3;transform:scale(1.05)}

section{padding:5rem 0}
#servicesPage{display:none}

h2{text-align:center;margin-bottom:3rem;font-size:2.5rem;color:#007bff}
.services{display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:2rem}
.service{background:#fff;padding:2rem;border-radius:10px;box-shadow:0 4px 10px rgba(0,0,0,.1);text-align:center;transition:.3s}
.service:hover{transform:translateY(-10px)}
.service ul{list-style:none;text-align:left;margin-top:1rem}
.service li{margin:.5rem 0;padding-left:1rem;position:relative}
.service li::before{content:'✓';color:#28a745;position:absolute;left:0}

footer{background:#333;color:#fff;text-align:center;padding:2rem}
footer a{color:#ccc;margin:0 10px}
footer a:hover{color:#fff}

@media(max-width:768px){
.nav-links{display:none;flex-direction:column;position:absolute;top:100%;left:0;width:100%;background:#fff}
.nav-links.active{display:flex}
.menu-toggle{display:block}
.hero h1{font-size:2.5rem}
}
</style>
</head>
<body>

<!-- ================= HEADER ================= -->
<header>
<nav class="container">
<div class="logo">Yash Architect</div>
<ul class="nav-links">
<li><a class="active" onclick="showHome()">Home</a></li>
<li><a onclick="showServices()">Services</a></li>
</ul>
<div class="menu-toggle" onclick="toggleMenu()">☰</div>
</nav>
</header>

<!-- ================= HOME PAGE (DITTO INDEX) ================= -->
<section id="homePage">
<div class="hero">
<div>
<h1>Find Your Dream Home</h1>
<p>Expert interior design, architecture, and property services for modern living.</p>
<a class="btn" onclick="showServices()">Explore Services</a>
</div>
</div>
</section>

<!-- ================= SERVICES PAGE (DITTO SERVICES) ================= -->
<section id="servicesPage">
<div class="container">
<h2>Our Services</h2>
<div class="services">
<div class="service"><h3>Interior Design</h3><p>Transform spaces with custom designs.</p><ul><li>Modern Style</li><li>Traditional Style</li><li>Minimalist Style</li><li>Eco-Friendly</li></ul></div>
<div class="service"><h3>Architecture Planning</h3><p>Full planning from concept to completion.</p><ul><li>Residential</li><li>Commercial</li><li>Renovations</li><li>Permits</li></ul></div>
<div class="service"><h3>Property Management</h3><p>Manage and maintain properties.</p><ul><li>Rental</li><li>Maintenance</li><li>Legal</li><li>Investment</li></ul></div>
<div class="service"><h3>Consultation</h3><p>Free expert advice.</p><ul><li>Virtual</li><li>In-Person</li><li>Assessment</li><li>Budget</li></ul></div>
</div>
<br><center><a class="btn" onclick="showHome()">Back to Home</a></center>
</div>
</section>

<!-- ================= FOOTER ================= -->
<footer>
<a onclick="showHome()">Home</a> |
<a onclick="showServices()">Services</a>
<p>© 2026 Holla Homes Inspired</p>
</footer>

<!-- ================= JS ================= -->
<script>
function toggleMenu(){document.querySelector('.nav-links').classList.toggle('active')}
function showHome(){
document.getElementById('homePage').style.display='block';
document.getElementById('servicesPage').style.display='none';
setActive(0);
}
function showServices(){
document.getElementById('homePage').style.display='none';
document.getElementById('servicesPage').style.display='block';
setActive(1);
}
function setActive(i){document.querySelectorAll('.nav-links a').forEach(a=>a.classList.remove('active'));document.querySelectorAll('.nav-links a')[i].classList.add('active');}
</script>

</body>
</html>

