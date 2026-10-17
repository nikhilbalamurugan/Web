<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Apex Innovation | Web Design & Digital Solutions</title>
  
  <!-- Google Fonts & Font Awesome Icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

  <style>
    /* ================= CSS VARIABLES & RESET ================= */
    :root {
      --bg-dark: #0a0f1d;
      --bg-card: rgba(255, 255, 255, 0.04);
      --bg-card-hover: rgba(255, 255, 255, 0.08);
      --primary: #4f46e5;
      --primary-glow: #6366f1;
      --secondary: #06b6d4;
      --text-main: #f8fafc;
      --text-muted: #94a3b8;
      --border-color: rgba(255, 255, 255, 0.1);
      --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Plus Jakarta Sans', sans-serif;
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--bg-dark);
      color: var(--text-main);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* Background Ambient Glows */
    .glow-blob {
      position: absolute;
      width: 450px;
      height: 450px;
      background: radial-gradient(circle, rgba(99, 102, 241, 0.25) 0%, rgba(6, 182, 212, 0) 70%);
      filter: blur(80px);
      z-index: -1;
      pointer-events: none;
    }

    .blob-1 { top: 0%; left: 10%; }
    .blob-2 { top: 40%; right: 5%; }
    .blob-3 { bottom: 10%; left: 20%; }

    /* ================= NAVIGATION ================= */
    nav {
      position: fixed;
      top: 0;
      width: 100%;
      padding: 1.2rem 8%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(10, 15, 29, 0.7);
      backdrop-filter: blur(15px);
      border-bottom: 1px solid var(--border-color);
      z-index: 1000;
      transition: var(--transition);
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 800;
      letter-spacing: -0.5px;
      background: linear-gradient(135deg, #fff 30%, var(--secondary));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      text-decoration: none;
    }

    .nav-links {
      display: flex;
      list-style: none;
      gap: 2rem;
      align-items: center;
    }

    .nav-links a {
      color: var(--text-muted);
      text-decoration: none;
      font-weight: 500;
      transition: var(--transition);
    }

    .nav-links a:hover {
      color: var(--text-main);
    }

    .btn-nav {
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      color: #fff !important;
      padding: 0.6rem 1.4rem;
      border-radius: 50px;
      font-weight: 600;
      box-shadow: 0 4px 15px rgba(99, 102, 241, 0.3);
      transition: var(--transition);
    }

    .btn-nav:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 20px rgba(99, 102, 241, 0.5);
    }

    /* ================= HERO SECTION ================= */
    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 8rem 8% 4rem;
      position: relative;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.4rem 1.2rem;
      background: rgba(99, 102, 241, 0.1);
      border: 1px solid rgba(99, 102, 241, 0.3);
      border-radius: 50px;
      font-size: 0.85rem;
      color: var(--secondary);
      margin-bottom: 1.5rem;
      animation: pulse 2s infinite ease-in-out;
    }

    .hero h1 {
      font-size: clamp(2.5rem, 5vw, 4.5rem);
      font-weight: 800;
      line-height: 1.15;
      max-width: 900px;
      margin-bottom: 1.5rem;
      letter-spacing: -1px;
    }

    .hero h1 span {
      background: linear-gradient(135deg, #6366f1, #06b6d4);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero p {
      font-size: clamp(1rem, 2vw, 1.25rem);
      color: var(--text-muted);
      max-width: 650px;
      margin-bottom: 2.5rem;
    }

    .hero-btns {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      justify-content: center;
    }

    .btn-primary, .btn-secondary {
      padding: 0.85rem 2rem;
      border-radius: 50px;
      font-weight: 600;
      font-size: 1rem;
      text-decoration: none;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      transition: var(--transition);
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      color: white;
      box-shadow: 0 4px 20px rgba(99, 102, 241, 0.4);
    }

    .btn-primary:hover {
      transform: translateY(-3px);
      box-shadow: 0 8px 25px rgba(99, 102, 241, 0.6);
    }

    .btn-secondary {
      background: rgba(255, 255, 255, 0.05);
      color: white;
      border: 1px solid var(--border-color);
    }

    .btn-secondary:hover {
      background: rgba(255, 255, 255, 0.1);
      transform: translateY(-3px);
    }

    /* ================= SECTION HEADINGS ================= */
    .section-title {
      text-align: center;
      margin-bottom: 3.5rem;
    }

    .section-title span {
      text-transform: uppercase;
      font-size: 0.85rem;
      font-weight: 700;
      color: var(--secondary);
      letter-spacing: 2px;
    }

    .section-title h2 {
      font-size: 2.3rem;
      margin-top: 0.5rem;
      font-weight: 700;
    }

    /* ================= WHO WE SERVE / SERVICES ================= */
    .services {
      padding: 6rem 8%;
    }

    .grid-cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 2rem;
    }

    .card {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: 16px;
      padding: 2.2rem;
      position: relative;
      transition: var(--transition);
      backdrop-filter: blur(10px);
    }

    .card:hover {
      transform: translateY(-6px);
      background: var(--bg-card-hover);
      border-color: rgba(99, 102, 241, 0.5);
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    }

    .card-icon {
      width: 55px;
      height: 55px;
      border-radius: 12px;
      background: rgba(99, 102, 241, 0.15);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.5rem;
      color: var(--secondary);
      margin-bottom: 1.5rem;
    }

    .card h3 {
      font-size: 1.3rem;
      margin-bottom: 0.8rem;
    }

    .card p {
      color: var(--text-muted);
      font-size: 0.95rem;
    }

    /* ================= SAMPLE IDEAS / PORTFOLIO ================= */
    .portfolio {
      padding: 6rem 8%;
      background: rgba(0, 0, 0, 0.2);
    }

    .portfolio-tabs {
      display: flex;
      justify-content: center;
      gap: 1rem;
      margin-bottom: 3rem;
      flex-wrap: wrap;
    }

    .tab-btn {
      background: transparent;
      border: 1px solid var(--border-color);
      color: var(--text-muted);
      padding: 0.5rem 1.5rem;
      border-radius: 30px;
      cursor: pointer;
      font-weight: 600;
      transition: var(--transition);
    }

    .tab-btn.active, .tab-btn:hover {
      background: var(--primary);
      color: #fff;
      border-color: var(--primary);
    }

    .portfolio-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 2rem;
    }

    .portfolio-item {
      background: var(--bg-card);
      border-radius: 16px;
      overflow: hidden;
      border: 1px solid var(--border-color);
      transition: var(--transition);
    }

    .portfolio-item:hover {
      transform: translateY(-8px);
      box-shadow: 0 15px 35px rgba(0,0,0,0.5);
    }

    .portfolio-img {
      width: 100%;
      height: 200px;
      background: #1e293b;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 3rem;
      color: var(--secondary);
      position: relative;
      overflow: hidden;
    }

    .portfolio-img::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(180deg, transparent 60%, rgba(10, 15, 29, 0.9));
    }

    .portfolio-info {
      padding: 1.5rem;
    }

    .portfolio-tag {
      font-size: 0.75rem;
      text-transform: uppercase;
      color: var(--secondary);
      font-weight: 700;
    }

    .portfolio-info h4 {
      font-size: 1.2rem;
      margin: 0.4rem 0 0.8rem;
    }

    .portfolio-info p {
      color: var(--text-muted);
      font-size: 0.9rem;
      margin-bottom: 1.2rem;
    }

    .custom-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      font-size: 0.8rem;
      color: #a5b4fc;
    }

    /* ================= HOW IT WORKS / CUSTOMIZATION ================= */
    .steps {
      padding: 6rem 8%;
    }

    .steps-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 2rem;
      text-align: center;
    }

    .step-box {
      padding: 2rem 1.5rem;
    }

    .step-number {
      width: 45px;
      height: 45px;
      line-height: 45px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      color: white;
      font-weight: 800;
      margin: 0 auto 1.5rem;
    }

    .step-box h4 {
      font-size: 1.15rem;
      margin-bottom: 0.5rem;
    }

    .step-box p {
      font-size: 0.9rem;
      color: var(--text-muted);
    }

    /* ================= CONTACT SECTION ================= */
    .contact {
      padding: 6rem 8%;
      background: linear-gradient(180deg, transparent, rgba(99, 102, 241, 0.05));
    }

    .contact-container {
      max-width: 800px;
      margin: 0 auto;
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: 20px;
      padding: 3rem;
      backdrop-filter: blur(15px);
    }

    .contact-info-banner {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.8rem;
      margin-bottom: 2rem;
      padding: 1rem;
      border-radius: 12px;
      background: rgba(99, 102, 241, 0.1);
      border: 1px dashed rgba(99, 102, 241, 0.4);
      color: var(--text-main);
      font-size: 1.05rem;
    }

    .contact-info-banner a {
      color: var(--secondary);
      text-decoration: none;
      font-weight: 700;
    }

    .contact-form {
      display: flex;
      flex-direction: column;
      gap: 1.2rem;
    }

    .form-group {
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
    }

    .form-group label {
      font-size: 0.9rem;
      font-weight: 600;
    }

    .form-control {
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid var(--border-color);
      border-radius: 8px;
      padding: 0.9rem 1.2rem;
      color: white;
      font-size: 0.95rem;
      outline: none;
      transition: var(--transition);
    }

    .form-control:focus {
      border-color: var(--secondary);
      background: rgba(255, 255, 255, 0.06);
    }

    textarea.form-control {
      resize: vertical;
      min-height: 120px;
    }

    /* ================= FOOTER ================= */
    footer {
      border-top: 1px solid var(--border-color);
      padding: 3rem 8%;
      text-align: center;
      color: var(--text-muted);
      font-size: 0.9rem;
    }

    /* ================= KEYFRAME ANIMATIONS ================= */
    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.03); }
    }

    /* ================= RESPONSIVENESS ================= */
    @media (max-width: 768px) {
      .nav-links {
        display: none; /* Can be expanded to mobile drawer */
      }
      .contact-container {
        padding: 2rem 1.5rem;
      }
    }
  </style>
</head>
<body>

  <!-- Ambient Light Accents -->
  <div class="glow-blob blob-1"></div>
  <div class="glow-blob blob-2"></div>
  <div class="glow-blob blob-3"></div>

  <!-- Header Navigation -->
  <nav>
    <a href="#" class="logo">
      <i class="fa-solid fa-shapes"></i> Apex Innovation
    </a>
    <ul class="nav-links">
      <li><a href="#services">Who We Help</a></li>
      <li><a href="#samples">Sample Ideas</a></li>
      <li><a href="#how-it-works">How It Works</a></li>
      <li><a href="#contact" class="btn-nav">Start Your Upgrade</a></li>
    </ul>
  </nav>

  <!-- Hero Section -->
  <header class="hero">
    <div class="badge">
      <i class="fa-solid fa-bolt"></i> Elevate Your Online Presence
    </div>
    <h1>Build A Website That <span>Attracts Customers</span> & Skyrockets Sales</h1>
    <p>
      We craft high-performing, custom-built websites for startups, hotels, local businesses, and growing enterprises ready to upskill their digital footprint.
    </p>
    <div class="hero-btns">
      <a href="#samples" class="btn-primary">
        <i class="fa-solid fa-eye"></i> Explore Sample Ideas
      </a>
      <a href="mailto:apex.innove@gmail.com?subject=New%20Website%20Inquiry" class="btn-secondary">
        <i class="fa-solid fa-envelope"></i> apex.innove@gmail.com
      </a>
    </div>
  </header>

  <!-- Who We Serve / Services -->
  <section class="services" id="services">
    <div class="section-title">
      <span>Tailored Solutions</span>
      <h2>Websites Built For Your Industry</h2>
    </div>
    <div class="grid-cards">
      <div class="card">
        <div class="card-icon"><i class="fa-solid fa-rocket"></i></div>
        <h3>Startups & Tech</h3>
        <p>Modern, high-converting landing pages built to impress investors, validate ideas, and generate user sign-ups fast.</p>
      </div>
      <div class="card">
        <div class="card-icon"><i class="fa-solid fa-hotel"></i></div>
        <h3>Hotels & Hospitality</h3>
        <p>Stunning, visual-first platforms featuring direct booking integrations, guest testimonials, and photo galleries.</p>
      </div>
      <div class="card">
        <div class="card-icon"><i class="fa-solid fa-store"></i></div>
        <h3>Small Businesses</h3>
        <p>Local SEO-ready storefronts and service catalogs designed to capture nearby customers and drive foot traffic.</p>
      </div>
      <div class="card">
        <div class="card-icon"><i class="fa-solid fa-chart-line"></i></div>
        <h3>Business Upskilling</h3>
        <p>Upgrade sluggish, outdated websites into blazing-fast digital assets with payment gateways, booking forms, and modern UI.</p>
      </div>
    </div>
  </section>

  <!-- Sample Ideas / Concept Showcase -->
  <section class="portfolio" id="samples">
    <div class="section-title">
      <span>Inspiration & Concepts</span>
      <h2>Check Our Sample Ideas</h2>
      <p style="color: var(--text-muted); margin-top: 0.5rem;">
        Every sample is 100% customizable to match your exact branding and feature requirements.
      </p>
    </div>

    <div class="portfolio-grid">
      <!-- Item 1 -->
      <div class="portfolio-item">
        <div class="portfolio-img">
          <i class="fa-solid fa-bed"></i>
        </div>
        <div class="portfolio-info">
          <span class="portfolio-tag">Hotels & Resorts</span>
          <h4>The Grand Oasis Concept</h4>
          <p>Features room showcase grids, direct booking forms, dynamic calendar pricing, and customer review sliders.</p>
          <div class="custom-badge">
            <i class="fa-solid fa-wand-magic-sparkles"></i> Fully Customizable as per your wishes
          </div>
        </div>
      </div>

      <!-- Item 2 -->
      <div class="portfolio-item">
        <div class="portfolio-img">
          <i class="fa-solid fa-laptop-code"></i>
        </div>
        <div class="portfolio-info">
          <span class="portfolio-tag">Startup & SaaS</span>
          <h4>NovaLaunch Tech Concept</h4>
          <p>Designed with interactive product demos, pricing tiers, lead magnet capture, and automated live chat.</p>
          <div class="custom-badge">
            <i class="fa-solid fa-wand-magic-sparkles"></i> Fully Customizable as per your wishes
          </div>
        </div>
      </div>

      <!-- Item 3 -->
      <div class="portfolio-item">
        <div class="portfolio-img">
          <i class="fa-solid fa-utensils"></i>
        </div>
        <div class="portfolio-info">
          <span class="portfolio-tag">Local Business / Dining</span>
          <h4>Urban Bistro Showcase</h4>
          <p>Online reservation management, rich digital menus, QR integration, and fast mobile-optimized pages.</p>
          <div class="custom-badge">
            <i class="fa-solid fa-wand-magic-sparkles"></i> Fully Customizable as per your wishes
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- How It Works Section -->
  <section class="steps" id="how-it-works">
    <div class="section-title">
      <span>Process</span>
      <h2>How We Upskill Your Business</h2>
    </div>
    <div class="steps-grid">
      <div class="step-box">
        <div class="step-number">1</div>
        <h4>Share Your Vision</h4>
        <p>Pick a sample idea or bring your own requirements. We brainstorm your layout and branding goals.</p>
      </div>
      <div class="step-box">
        <div class="step-number">2</div>
        <h4>Custom Design</h4>
        <p>We tailor layout, colors, copy, and functionality strictly aligned with your customer targets.</p>
      </div>
      <div class="step-box">
        <div class="step-number">3</div>
        <h4>Launch & Grow</h4>
        <p>Deploy a fast, responsive, conversion-focused site that turns daily visitors into paying clients.</p>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section class="contact" id="contact">
    <div class="contact-container">
      <div class="section-title" style="margin-bottom: 2rem;">
        <span>Get In Touch</span>
        <h2>Start Your Newest Upgrade</h2>
      </div>

      <div class="contact-info-banner">
        <i class="fa-solid fa-envelope"></i>
        <span>Direct Email: <a href="mailto:apex.innove@gmail.com">apex.innove@gmail.com</a></span>
      </div>

      <form class="contact-form" action="mailto:apex.innove@gmail.com" method="post" enctype="text/plain">
        <div class="form-group">
          <label>Your Name</label>
          <input type="text" class="form-control" name="Name" placeholder="e.g. John Doe" required>
        </div>

        <div class="form-group">
          <label>Your Email Address</label>
          <input type="email" class="form-control" name="Email" placeholder="e.g. contact@yourbusiness.com" required>
        </div>

        <div class="form-group">
          <label>Business Type</label>
          <select class="form-control" name="BusinessType">
            <option value="Startup">Startup</option>
            <option value="Hotel/Hospitality">Hotel / Hospitality</option>
            <option value="Small Business">Small Business</option>
            <option value="Website Upgrade/Upskill">Website Redesign / Upskill</option>
            <option value="Other">Other</option>
          </select>
        </div>

        <div class="form-group">
          <label>Tell us about your project & custom ideas</label>
          <textarea class="form-control" name="ProjectDetails" placeholder="Describe the features, animations, or styling you want..." required></textarea>
        </div>

        <button type="submit" class="btn-primary" style="justify-content: center; width: 100%; border: none;">
          <i class="fa-solid fa-paper-plane"></i> Send Inquiry via Email
        </button>
      </form>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; <span id="year"></span> <strong>Apex Innovation</strong>. All rights reserved.</p>
    <p style="margin-top: 0.5rem; font-size: 0.8rem;">Empowering businesses with modern digital presence.</p>
  </footer>

  <script>
    // Dynamic Year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Scroll Navbar Effect
    window.addEventListener('scroll', () => {
      const nav = document.querySelector('nav');
      if (window.scrollY > 50) {
        nav.style.background = 'rgba(10, 15, 29, 0.95)';
        nav.style.boxShadow = '0 10px 25px rgba(0,0,0,0.5)';
      } else {
        nav.style.background = 'rgba(10, 15, 29, 0.7)';
        nav.style.boxShadow = 'none';
      }
    });
  </script>
</body>
</html>
