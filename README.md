<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>FFDX4 | 3D Exhibition & Event Design by Ajay Khanna</title>
  <meta name="description" content="FFDX4 offers creative, immersive, and sustainable 3D exhibition stands, booths, and event design services by Ajay Khanna." />
  <!-- Open Graph & SEO -->
  <meta property="og:title" content="FFDX4 | 3D Exhibition & Event Design by Ajay Khanna" />
  <meta property="og:description" content="FFDX4 offers creative, immersive, and sustainable 3D exhibition stands, booths, and event design services." />
  <meta property="og:image" content="https://images.unsplash.com/photo-1503387762-592deb58ef4e?w=1200&q=60" />
  <meta property="og:site_name" content="FFDX4" />
  <meta name="twitter:card" content="summary_large_image" />
  <link rel="icon" href="https://upload.wikimedia.org/wikipedia/commons/a/a7/React-icon.svg">
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">

  <style>
    :root {
      --primary: #003b91;
      --secondary: #0078ff;
      --accent: #ffd700;
      --bkg: #f4f6fb;
      --foreground: #222;
      --glass: rgba(255,255,255,0.9);
      --dark-primary: #181a23;
      --dark-bkg: #10121A;
      --dark-foreground: #eaeaea;
    }
    [data-theme="dark"] {
      --bkg: var(--dark-bkg);
      --foreground: var(--dark-foreground);
      --glass: rgba(24,26,35,0.93);
      --primary: #20305b;
      --secondary: #0059b2;
      --accent: #ffe57f;
    }
    * {
      margin: 0; padding: 0; box-sizing: border-box;
      font-family: "Poppins", sans-serif;
    }
    html { scroll-behavior: smooth; }
    body {
      background: var(--bkg);
      color: var(--foreground);
      transition: background 0.3s, color 0.3s;
      min-height: 100vh;
    }
    /* Scrollbar */
    ::-webkit-scrollbar { width: 8px; background: #eee; }
    ::-webkit-scrollbar-thumb { background: var(--primary); border-radius: 7px; }

    /* Navbar Glassmorphic */
    header {
      position: relative;
      min-height: 95vh;
      display: flex;
      align-items: center; justify-content: center;
      flex-direction: column;
      background:
        linear-gradient(135deg,rgba(0,59,145,0.7) 67%,rgba(0,120,255,0.1) 100%),
        url('https://images.unsplash.com/photo-1581091215360-d9e80a8d143f?fit=crop&w=1600&q=80') center / cover no-repeat;
    }
    nav {
      position: fixed;
      top: 0; left: 0; right: 0; z-index: 99;
      background: var(--glass);
      backdrop-filter: blur(15px);
      display: flex; align-items: center; justify-content: space-between;
      padding: 12px 40px;
      box-shadow: 0 2px 14px rgba(0,59,145,0.10);
      transition: background 0.4s;
    }
    nav .logo {
      font-weight: 700; font-size: 1.4rem;
      color: var(--primary); letter-spacing: 2px;
      text-shadow: 0 1px 3px rgba(0,59,145,0.1);
    }
    nav ul {
      display: flex;
      list-style: none;
      gap: 28px;
    }
    nav ul li a {
      color: var(--foreground);
      text-decoration: none;
      font-weight: 500;
      position: relative;
      padding: 3px 8px;
      border-radius: 7px;
      transition: background 0.2s, color 0.2s;
    }
    nav ul li a:hover, nav ul li a.active {
      background: var(--accent);
      color: var(--primary);
    }
    .theme-toggle {
      cursor: pointer; font-size: 22px;
      margin-left: 18px;
      color: var(--primary);
      transition: color 0.3s, filter 0.3s;
      filter: drop-shadow(0 1px 2px var(--accent));
    }
    /* Hero Content */
    .hero {
      z-index: 1;
      text-align: center;
      margin-top: 120px;
      color: #fff;
      text-shadow: 0 10px 22px rgba(0,0,0,0.13);
    }
    .hero h1 {
      font-size: 3rem;
      font-weight: 700;
      letter-spacing: 2px;
      animation: fadeInDown 1s 0.25s both;
    }
    @keyframes fadeInDown { 0% {opacity:0; transform:translateY(-50px);} 100% {opacity:1; transform:translateY(0);} }
    .hero .dynamic {
      font-size: 2.1rem;
      font-weight: 600;
      background:linear-gradient(90deg,#ffd700 45%,#fff 99%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      display: inline;
      animation: typing 1s steps(10) infinite alternate;
    }
    .hero p {
      font-size: 1.3rem; margin-top: 18px; max-width: 520px; margin-left: auto; margin-right: auto;
      animation: fadeInUp 1.2s 0.75s both;
    }
    @keyframes fadeInUp { 0% {opacity: 0; transform:translateY(50px);} 100% {opacity: 1; transform:translateY(0);} }
    .cta-btn {
      margin-top: 38px;
      display: inline-block;
      padding: 15px 34px;
      background: linear-gradient(99deg,var(--accent) 70%,#fff 100%);
      color: var(--primary);
      font-weight: 700;
      font-size: 1.16rem;
      border-radius: 35px;
      border: none;
      box-shadow: 0 4px 18px rgba(0,59,145,0.10);
      cursor: pointer;
      position: relative;
      overflow: hidden;
      transition: filter 0.2s, transform 0.18s;
    }
    .cta-btn:hover {
      filter: brightness(1.05) drop-shadow(0 2px 12px var(--accent));
      transform: scale(1.04) translateY(-2px);
    }

    section {
      max-width: 1160px;
      margin: 0 auto;
      padding: 85px 18px 60px 18px;
      opacity: 0;
      transform: translateY(45px);
      transition: opacity 1.1s, transform 1.2s;
      will-change: opacity, transform;
      background: none;
    }
    section.show { opacity: 1; transform: translateY(0);}
    h2 { color: var(--primary); font-size: 2.2rem; margin-bottom: 28px; font-weight: 700; letter-spacing:1.2px;}
    /* About Split */
    #about-section { display: grid; grid-template-columns:1fr 1.3fr; gap: 38px; align-items: center;}
    .about-photo { 
      background:linear-gradient(135deg,#ffd70044 35%,#003b9140 100%);
      border-radius: 18px;
      overflow: hidden;
      box-shadow: 0 3px 18px rgba(0,59,145,0.12);
      text-align:center;
      padding:18px;
    }
    .about-photo img { width: 220px; border-radius:17px; border: 4px solid #fff; }
    .about-details p { font-size: 1.1rem; color: #444; margin-bottom: 10px;}
    /* Counters */
    .counters {display: flex; gap:32px; margin-top:14px;}
    .counter {padding:0 18px; text-align:center;}
    .counter span { font-size:2.2rem; color: var(--accent); font-weight: 700;}
    .counter p { font-size: 1rem; color: #555; }

    /* Gallery */
    #gallery-section { margin-top:40px;}
    .filter-btns { text-align:center; margin-bottom:30px;}
    .filter-btns button {
      background:var(--glass); color:var(--primary);
      border: 1px solid var(--primary);
      padding:7px 20px; border-radius:22px;
      font-weight:600; margin:5px 3px;
      cursor:pointer; transition:background 0.2s,color 0.2s;
    }
    .filter-btns button.active {background:var(--primary);color:#fff;}
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit,minmax(270px,1fr));
      gap:20px;
    }
    .gallery-item {
      position: relative;
      border-radius:14px;
      box-shadow: 0 1px 9px rgba(0,0,0,.09);
      overflow: hidden; background:#fff;
      cursor: pointer; transition: transform 0.18s;
    }
    .gallery-item img {
      width: 100%; display: block;
      height:180px; object-fit:cover;
      transition: transform 0.23s;
      border-radius:14px;
      background: #e3e8f9;
    }
    .gallery-item:hover img { transform:scale(1.07);}
    /* Lightbox */
    #lightbox {position:fixed;inset:0;background:rgba(0,0,0,.91);display:none;align-items:center;justify-content:center;z-index:10001;}
    #lightbox img{max-width:90vw;max-height:84vh;border-radius:14px;box-shadow:0 8px 24px rgba(0,0,0,0.65);}
    #lightbox span{position:absolute;top:24px;right:45px;color:#fff;font-size:34px;cursor:pointer;font-weight:bold;}
    .gallery-caption {position:absolute;bottom:0px;left:0;width:100%;background:linear-gradient(transparent 60%,rgba(0,0,0,0.62));color:#fff;padding:8px 10px;font-size:1.02rem;font-weight:500;}

    /* Timeline/Process */
    #process-section {margin:25px 0 10px 0;}
    .timeline {display: flex; justify-content: center; gap:30px;flex-wrap: wrap;}
    .process-card {
      background: var(--glass); border-radius:15px;
      box-shadow:0 2px 11px #003b9130; text-align:center; padding:30px 20px; max-width:212px;
      transition: transform .22s, background .15s;
    }
    .process-card:hover {background:var(--secondary);color:#fff;transform:translateY(-5px) scale(1.05);}
    .process-card .icon { font-size:36px;color:var(--secondary); }

    /* Innovation */
    #innovation-section {background:linear-gradient(135deg,#e6f9ff 55%,#f5e9cf 100%);border-radius:10px;margin-top:35px;}
    .innovation-list {display:flex;gap:26px;justify-content:center;flex-wrap:wrap;}
    .innovation-item {background:#fff;padding:20px 18px;border-radius:11px;box-shadow:0 1px 7px #003b9122;max-width:220px;text-align:center;}
    .innovation-item i {font-size:32px;color:var(--primary);margin-bottom:7px;}

    /* Testimonials */
    #testimonials-section {background:linear-gradient(120deg,#0078ff 28%,#003b91 100%);color:#fff;border-radius:18px;padding:38px 0;margin:30px 0;}
    .testimonial-carousel {display:flex;overflow:hidden;position:relative;width:90vw;max-width:640px;margin:auto;}
    .testimonial-card {
      flex: 1 0 100%; opacity:0; transition:opacity 0.7s, left 0.7s;
      padding:0 28px;text-align:center;min-height:120px;display:none;align-items:center;justify-content:center;
    }
    .testimonial-card.active {display:flex;opacity:1;}
    .testimonial-quote {font-size:1.15rem;}
    .testimonial-client {margin-top:12px;font-weight:600;color:var(--accent);}
    .testimonials-dots {display:flex;gap:8px;justify-content:center;margin:16px 0;}
    .dots {width:13px;height:13px;border-radius:50%;background:#ffe57f;opacity:0.40;cursor:pointer;}
    .dots.active {background:var(--accent);opacity:1;}
    @media (max-width:630px){
      .testimonial-card{padding:0 6vw;}
    }
    /* Contact */
    #contact-section {margin-top:35px;display:grid;grid-template-columns:1fr 1fr;gap:32px;align-items:center;background: linear-gradient(121deg,#ecefff,#d2e5ff 100%);border-radius:11px;padding:36px 18px;}
    .contact-form {max-width:410px;margin:auto;}
    .contact-form input,
    .contact-form textarea {
      width:100%;padding:14px;border-radius:10px;border:none;margin-bottom:14px;
      background:#fff;font-size:1rem;color:#222;
      box-shadow:0 1px 4px #003b9111;
      transition:border .2s,box-shadow .2s;
    }
    .contact-form input:focus,
    .contact-form textarea:focus {outline:2px solid var(--primary);box-shadow:0 0 7px var(--accent);}
    .contact-form input[type="submit"] {
      background:var(--accent);color:var(--primary);font-weight:700;cursor:pointer;transition:background 0.2s;}
    .contact-form input[type="submit"]:hover {background:var(--primary);color:#fff;}
    .contact-info {font-size:1.1rem;}
    .contact-info p {margin-bottom:10px;}
    .contact-socials {margin-top:18px;}
    .contact-socials a {margin-right:19px;font-size:28px;color:var(--primary);transition:color .2s;}
    .contact-socials a:hover {color:var(--accent);}
    .map-embed {margin-top:12px;}
    .map-embed iframe {border-radius:10px;border:0;width:100%;height:170px;}

    @media (max-width:900px){
      #about-section{grid-template-columns:1fr;}
      #contact-section{grid-template-columns:1fr;}
    }
    @media (max-width:700px){
      nav{padding:10px 7vw;}
      .hero h1{font-size:2.1rem;}
      .hero .dynamic{font-size:1.17rem;}
      .gallery-grid{grid-template-columns:1fr;}
      .gallery-item img{height:120px;}
      .innovation-list,
      .timeline{flex-direction:column;}
      .testimonial-card{font-size:0.98rem;}
      #contact-section{padding:18px 6px;}
    }

    /* Footer */
    footer{background:linear-gradient(89deg,#003062 70%,#ffd700 170%);color:#fff;text-align:center;padding:23px 0;margin-top:36px;font-size:1.04rem;border-radius:17px 17px 0 0;}
    .footer-socials a {margin:0 13px;font-size:23px;color:#ffd700;transition:color 0.21s;}
    .footer-socials a:hover {color:#fff;}
    .back-to-top {
      position:fixed;bottom:38px;right:23px;z-index:999;
      background:var(--primary);color:#fff;border:none;
      border-radius:50%;width:52px;height:52px;display:flex;align-items:center;justify-content:center;
      box-shadow:0 2px 8px #002b7340;font-size:27px;cursor:pointer;transition:background 0.3s,transform 0.2s;
      opacity:0.87;outline:none;
    }
    .back-to-top:hover{background:var(--accent);color:var(--primary);transform:scale(1.11);}
  </style>
</head>
<body>
  <nav>
    <span class="logo">FFDX4</span>
    <ul>
      <li><a href="#about-section" class="active">About</a></li>
      <li><a href="#gallery-section">Gallery</a></li>
      <li><a href="#process-section">Process</a></li>
      <li><a href="#innovation-section">Innovation</a></li>
      <li><a href="#testimonials-section">Testimonials</a></li>
      <li><a href="#contact-section">Contact</a></li>
    </ul>
    <span class="theme-toggle" title="Toggle Dark Mode" onclick="toggleTheme()">🌙</span>
  </nav>

  <header>
    <div class="hero">
      <h1>Exhibition & Event Design<br>by Ajay Khanna</h1>
      <div class="dynamic" id="dynamic-headline">Stall</div>
      <p>Premium 3D booth, stall, and event design services — creative, immersive, & sustainable. Transform your brand's presence, nationwide & worldwide.</p>
      <a href="#contact-section" class="cta-btn">Get a Quote</a>
    </div>
  </header>

  <!-- About Section -->
  <section id="about-section">
    <div class="about-photo">
      <img src="C:\Users\Dell\Pictures\1.png" alt="Ajay Khanna 3D Event Designer Photo" loading="lazy">
      <div style="font-weight:600;color:#003b91;margin-top:8px;">Ajay Khanna</div>
    </div>
    <div class="about-details">
      <h2>About Me</h2>
      <p>I’m Ajay Khanna, India’s premium 3D exhibition & event designer. I craft production-ready, stunning stalls, booths, and stages for expos, launches, and events — with a focus on sustainability & innovation.</p>
      <p><b>Pricing:</b> ₹50 per sq. meter – (fast, transparent, & affordable).</p>
      <div class="counters">
        <div class="counter"><span id="projectsCount">0</span><p>Projects</p></div>
        <div class="counter"><span id="yearsCount">0</span><p>Years Exp.</p></div>
        <div class="counter"><span id="clientsCount">0</span><p>Clients Served</p></div>
      </div>
    </div>
  </section>

  <!-- Gallery Section -->
  <section id="gallery-section">
    <h2>Gallery</h2>
    <div class="filter-btns">
      <button class="active" onclick="filterItems('all')">All</button>
      <button onclick="filterItems('stall')">Stall</button>
      <button onclick="filterItems('booth')">Booth</button>
      <button onclick="filterItems('stage')">Stage</button>
      <button onclick="filterItems('event')">Event</button>
    </div>
    <div class="gallery-grid" id="gallery-grid">
      <div class="gallery-item" data-cat="stall">
        <img src="C:\Users\Dell\Pictures\bd969e228131009.684d58d78fb80.jpeg" alt="Exhibition Stall 3D Design" loading="lazy"><div class="gallery-caption">Indus Food 2024 – Nova Dairy </div>
      </div>   <div class="gallery-item" data-cat="stall">
        <img src="C:\Users\Dell\Pictures\0c64c5226204253.684d1ee8c32b9.jpg" alt="Exhibition Stall 3D Design" loading="lazy"><div class="gallery-caption">Indus Food 2024 – PARAS FLOUR MILL</div>
      </div>
<div class="gallery-item" data-cat="stall">
        <img src="C:\Users\Dell\Pictures\ed47bd230192411.68725cec0c7fc.jpg" alt="Exhibition Stall 3D Design" loading="lazy"><div class="gallery-caption">Worlb Food India 2024 – Murti Foods</div>
      </div>   <div class="gallery-item" data-cat="stall">
        <img src="C:\Users\Dell\Pictures\f63494224464467.684d538988aba.jpg" alt="Exhibition Stall 3D Design" loading="lazy"><div class="gallery-caption">Indus Food 2024 – Quality Spices & Food Exports Pvt. Ltd </div>
      </div><div class="gallery-item" data-cat="stall">
        <img src="C:\Users\Dell\Pictures\f5d334224465665.684d202922755.jpeg" alt="Exhibition Stall 3D Design" loading="lazy"><div class="gallery-caption">Indus Food 2024 – Nova Dairy</div>
      </div>   <div class="gallery-item" data-cat="stall">
        <img src="C:\Users\Dell\Pictures\4affff228126995.684d466bcc680.jpg" alt="Exhibition Stall 3D Design" loading="lazy"><div class="gallery-caption">Indus Food 2024 - Premium Modular Stall</div>
      </div><div class="gallery-item" data-cat="stall">
        <img src="C:\Users\Dell\Pictures\96e20a228130281.684d564c71243.jpg" Exhibition Stall 3D Design" loading="lazy"><div class="gallery-caption">Indus Food 2024 – Premium Modular Stall</div>
      </div> 



      <div class="gallery-item" data-cat="booth">
        <img src="C:\Users\Dell\Pictures\b851e9228121411.684d29e5e9629.jpeg" alt="Technology Booth Modern Design" loading="lazy"><div class="gallery-caption">Tech Summit – Bespoke Booth Layout</div>
      </div>      
<div class="gallery-item" data-cat="booth">
        <img src="C:\Users\Dell\Pictures\0240cf226204541.684d3340e7954.jpg"alt="Technology Booth Modern Design" loading="lazy"><div class="gallery-caption">Tech Summit – Bespoke Booth Layout</div>
      </div>
<div class="gallery-item" data-cat="booth">
        <img src="C:\Users\Dell\Pictures\9eef7b228121693.684d2ad9cbc8b.jpeg" alt="Technology Booth Modern Design" loading="lazy"><div class="gallery-caption">Tech Summit – Bespoke Booth Layout</div>
      </div>      
<div class="gallery-item" data-cat="booth">
        <img src="C:\Users\Dell\Pictures\adb959230278781.687479a76b321.jpg" alt="Technology Booth Modern Design" loading="lazy"><div class="gallery-caption">Tech Summit – Bespoke Booth Layout</div>
      </div>
<div class="gallery-item" data-cat="booth">
        <img src="C:\Users\Dell\Pictures\14d3cb223632759.67fcc85964ccb.jpeg"alt="Technology Booth Modern Design" loading="lazy"><div class="gallery-caption">Tech Summit – Bespoke Booth Layout</div>
      </div>      
<div class="gallery-item" data-cat="booth">
        <img src="C:\Users\Dell\Pictures\eebe58231625483.688c7a5c7b57c.jpeg" alt="Technology Booth Modern Design" loading="lazy"><div class="gallery-caption">Tech Summit – Bespoke Booth Layout</div>
      </div>

      <div class="gallery-item" data-cat="stage">
        <img src="C:\Users\Dell\Pictures\4f7e24224464847.680b502613a46.jpg" alt="Stage Event Design Lighting" loading="lazy"><div class="gallery-caption">Fashion Gala – Immersive Stage Lighting</div>
      </div>
      <div class="gallery-item" data-cat="event">
        <img src="C:\Users\Dell\Pictures\0240cf226204541.684d3340e7954.jpg" alt="Event design 2025" loading="lazy"><div class="gallery-caption">Product Launch – Event Environment</div>
      </div>
      <div class="gallery-item" data-cat="stall booth">
        <img src="C:\Users\Dell\Pictures\1c30d3223478589.67f9350cb5514.webp"alt="Luxury double deck booth render" loading="lazy"><div class="gallery-caption">Luxury Auto Expo – Double Deck Booth</div>
      </div>
      <div class="gallery-item" data-cat="booth event">
        <img src="C:\Users\Dell\Pictures\d77e6f224459009.684d40f19e064.jpeg" alt="Trade Show Custom Booth" loading="lazy"><div class="gallery-caption">Trade Show – Custom Themed Booth</div>
      </div>
      <div class="gallery-item" data-cat="stage">
        <img src="C:\Users\Dell\Pictures\890b6d216623163.67833a6a4d11e.jpg" alt="360 LED Stage Setup" loading="lazy"><div class="gallery-caption">Music Awards – 360° LED Stage</div>
      </div>

<div class="gallery-item" data-cat="stage">
        <img src="C:\Users\Dell\Pictures\1f5b6e224464847.680b5026134a9.jpg" alt="360 LED Stage Setup" loading="lazy"><div class="gallery-caption">Music Awards – 360° LED Stage</div>
      </div>

    </div>
  </section>

  <!-- Lightbox for gallery -->
  <div id="lightbox" onclick="closeLightbox(event)">
    <span>&times;</span>
    <img id="lightbox-img" src="" alt="Gallery Full Preview">
  </div>

  <!-- Process/TImeline Section -->
  <section id="process-section">
    <h2>Process</h2>
    <div class="timeline">
      <div class="process-card"><div class="icon">💡</div><b>Concept</b><p>Discuss & ideate as per your brand vision.</p></div>
      <div class="process-card"><div class="icon">🛠️</div><b>3D Design</b><p>Detailed 3D renders & layouts for review/approval.</p></div>
      <div class="process-card"><div class="icon">📝</div><b>Review</b><p>Your feedback + real-time changes for perfection.</p></div>
      <div class="process-card"><div class="icon">🚚</div><b>Delivery</b><p>Final production files shared, always on time!</p></div>
    </div>
  </section>

  <!-- Innovation Section -->
  <section id="innovation-section">
    <h2>Innovation & Sustainability</h2>
    <div class="innovation-list">
      <div class="innovation-item"><i>🌱</i><br><b>Eco-Friendly</b><p>Sustainable booths built using recycled, modular materials.</p></div>
      <div class="innovation-item"><i>✨</i><br><b>Immersive 3D</b><p>Next-gen visualization with real 3D AR/VR previews.</p></div>
      <div class="innovation-item"><i>💡</i><br><b>Smart Lighting</b><p>Energy-efficient, multi-zone LED systems for impact.</p></div>
      <div class="innovation-item"><i>🔁</i><br><b>Reusable Frames</b><p>Flexible systems for rapid setup & re-use at all events.</p></div>
    </div>
  </section>

  <!-- Testimonials -->
  <section id="testimonials-section">
    <h2>Testimonials</h2>
    <div class="testimonial-carousel" id="testimonial-carousel">
      <div class="testimonial-card active">
        <div class="testimonial-quote">“Ajay delivered truly next-level 3D designs — our booth was the most talked-about at the expo!”</div>
        <div class="testimonial-client">– Mr. R. Sharma (ITEx 2025)</div>
      </div>
      <div class="testimonial-card">
        <div class="testimonial-quote">“Fast, creative, and always professional — can vouch for FFDX4 for any big event.”</div>
        <div class="testimonial-client">– Priya Kapoor (AutoExpo 2025)</div>
      </div>
      <div class="testimonial-card">
        <div class="testimonial-quote">“Stunning visuals, everything on time. Highly recommended for pan-India & global work!”</div>
        <div class="testimonial-client">– Vivek Jain (StartupSummit)</div>
      </div>
      <div class="testimonial-card">
        <div class="testimonial-quote">“Great experience! Transparent process, on-point communication, brilliant AR previews.”</div>
        <div class="testimonial-client">– Komal Batra (AgriBiz Fair)</div>
      </div>
    </div>
    <div class="testimonials-dots" id="testimonial-dots"> </div>
  </section>

  <!-- Contact Section -->
  <section id="contact-section">
    <div>
      <form class="contact-form" action="https://formsubmit.co/ffdx4design@gmail.com" method="POST">
        <h2>Contact & Enquiry</h2>
        <input type="text" name="name" placeholder="Your Name" required autocomplete="off">
        <input type="email" name="email" placeholder="Your Email" required autocomplete="off">
        <textarea name="message" rows="5" placeholder="Tell us about your project..." required></textarea>
        <input type="submit" value="Send Message">
      </form>
      <div class="contact-socials">
        <a href="https://www.linkedin.com/in/ajay-khanna-61a564365" target="_blank" title="LinkedIn">🔗</a>
        <a href="https://www.instagram.com/ffdx4exhibitiondesign" target="_blank" title="Instagram">📸</a>
        <a href="https://www.behance.net/ajaykhanna7" target="_blank" title="Behance">🅱️</a>
      </div>
      <div class="contact-info">
        <p>📧 <b>Email:</b> ffdx4design@gmail.com</p>
        <p>📱 <b>WhatsApp:</b> +91 9818569137</p>
        <p>📍 India / Global Projects Accepted</p>
      </div>
    </div>
    <div>
      <div class="map-embed">
        <iframe src="https://maps.google.com/maps?q=New+Delhi+India&t=&z=13&ie=UTF8&iwloc=&output=embed" allowfullscreen title="Location Map"></iframe>
      </div>
    </div>
  </section>

  <button onclick="window.scrollTo({top:0,behavior:'smooth'})" class="back-to-top" title="Back to Top">↑</button>
  <footer>
    <div class="footer-socials">
      <a href="https://www.linkedin.com/in/ajay-khanna-61a564365" target="_blank" title="LinkedIn">🔗</a>
      <a href="https://www.instagram.com/ffdx4exhibitiondesign" target="_blank" title="Instagram">📸</a>
      <a href="https://www.behance.net/ajaykhanna7" target="_blank" title="Behance">🅱️</a>
    </div>
    <div>© 2025 FFDX4 Exhibition & Event Design | Made by Ajay Khanna</div>
  </footer>

  <script>
    // Navbar scroll active section
    const navLinks = document.querySelectorAll("nav ul li a");
    window.onscroll = function () {
      let fromTop = window.scrollY + 120;
      navLinks.forEach(link => {
        let section = document.querySelector(link.getAttribute("href"));
        if (section && fromTop >= section.offsetTop && fromTop < section.offsetTop + section.offsetHeight) {
          navLinks.forEach(l => l.classList.remove('active'));
          link.classList.add('active');
        }
      });
    };

    // Dynamic headline animation
    (function(){
      const words = ["Stall", "Booth", "Stage", "Event"];
      let idx = 0;
      setInterval(() => {
        idx = (idx+1)%words.length;
        document.getElementById('dynamic-headline').textContent= words[idx];
      }, 1700);
    })();

    // Section reveal on scroll
    const revealEls = document.querySelectorAll("section");
    const obs = new IntersectionObserver(entries => {
      entries.forEach(entry => { entry.isIntersecting && entry.target.classList.add("show"); });
    }, { threshold: 0.15 });
    revealEls.forEach(el => obs.observe(el));

    // Animated counters
    function animateCount(elem, max) {
      let n = 0, step = Math.ceil(max/40);
      function run(){ n+=step; if(n>max) n=max; elem.textContent=n; if(n<max) requestAnimationFrame(run);}
      run();
    }
    window.addEventListener('DOMContentLoaded', ()=>{
      animateCount(document.getElementById('projectsCount'),124);
      animateCount(document.getElementById('yearsCount'),12);
      animateCount(document.getElementById('clientsCount'),78);
    });

    // Gallery filter
    function filterItems(cat){
      document.querySelectorAll('.filter-btns button').forEach(x=>x.classList.remove('active'));
      event.target.classList.add('active');
      let items = document.querySelectorAll('#gallery-grid .gallery-item');
      items.forEach(it=>{
        if(cat==='all' || it.dataset.cat.includes(cat)) it.style.display='block';
        else it.style.display='none';
      });
    }

    // Lightbox
    document.querySelectorAll('.gallery-item img').forEach(img=>{
      img.addEventListener('click', function(){
        document.getElementById('lightbox-img').src = this.src;
        document.getElementById('lightbox').style.display='flex';
      });
    });
    function closeLightbox(e){
      if(e.target.id=="lightbox" || e.target.tagName==="SPAN")document.getElementById('lightbox').style.display='none'
    }

    // Testimonials carousel
    let idx=0, cards=document.querySelectorAll('.testimonial-card'),dots=document.getElementById('testimonial-dots');
    for(let i=0;i<cards.length;i++){
      let d=document.createElement('div');d.className='dots'+(i===0?' active':'');d.addEventListener('click',()=>showTestimonial(i));dots.appendChild(d);
    }
    function showTestimonial(i){ cards.forEach(t=>t.classList.remove('active'));dots.childNodes.forEach(d=>d.classList.remove('active'));cards[i].classList.add('active');dots.childNodes[i].classList.add('active');idx=i;}
    setInterval(()=>showTestimonial((idx+1)%cards.length), 4400);

    // Dark/Light mode toggle
    function toggleTheme(){
      let theme = document.documentElement.getAttribute("data-theme")=="dark" ? "light":"dark";
      document.documentElement.setAttribute("data-theme", theme);
      localStorage.setItem("theme",theme);
    }
    // On load, set theme
    (function(){
      let theme = localStorage.getItem("theme")||"light";
      document.documentElement.setAttribute("data-theme",theme);
    })();
  </script>
</body>
</html>
