<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Lumière Beauty - Modern aesthetic care, skincare treatments, and wellness experiences.">
    <title>Lumière Beauty | Modern Aesthetic Care</title>
    <style>
        /* ================= VARIABLES & RESET ================= */
        :root {
            --bg: #faf9f6;
            --surface: #ffffff;
            --primary: #c9a882;
            --primary-dark: #a6845e;
            --text: #1f1f1f;
            --text-muted: #6b6b6b;
            --border: #e8e4df;
            --radius: 14px;
            --shadow: 0 4px 20px rgba(0,0,0,0.05);
            --shadow-hover: 0 8px 28px rgba(0,0,0,0.09);
            --transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }
        html { scroll-behavior: smooth; }
        body {
            font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
            background: var(--bg);
            color: var(--text);
            line-height: 1.6;
            -webkit-font-smoothing: antialiased;
        }

        /* ================= UTILITIES ================= */
        .container { max-width: 1120px; margin: 0 auto; padding: 0 1.5rem; }
        .btn {
            display: inline-block;
            padding: 0.9rem 2rem;
            background: var(--text);
            color: var(--surface);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 500;
            font-size: 0.95rem;
            transition: var(--transition);
            border: 1.5px solid transparent;
            cursor: pointer;
        }
        .btn:hover { background: var(--primary-dark); transform: translateY(-2px); }
        .btn-outline { background: transparent; border-color: var(--text); color: var(--text); }
        .btn-outline:hover { background: var(--text); color: var(--surface); }

        /* ================= HEADER ================= */
        header {
            padding: 1.5rem 0;
            position: sticky;
            top: 0;
            background: rgba(250,249,246,0.92);
            backdrop-filter: blur(12px);
            z-index: 10;
            border-bottom: 1px solid var(--border);
        }
        nav { display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem; }
        .logo { font-size: 1.5rem; font-weight: 700; letter-spacing: -0.5px; color: var(--text); text-decoration: none; }
        .nav-links { display: flex; gap: 1.8rem; list-style: none; }
        .nav-links a { text-decoration: none; color: var(--text-muted); font-weight: 500; font-size: 0.95rem; transition: var(--transition); position: relative; }
        .nav-links a:hover { color: var(--text); }
        .nav-links a::after {
            content: ''; position: absolute; bottom: -4px; left: 0; width: 0; height: 2px; background: var(--primary); transition: var(--transition);
        }
        .nav-links a:hover::after { width: 100%; }

        /* ================= HERO ================= */
        .hero { padding: 5rem 0 3rem; text-align: center; }
        .hero h1 {
            font-size: clamp(2.8rem, 6vw, 4.2rem);
            line-height: 1.1;
            margin-bottom: 1rem;
            font-weight: 800;
            letter-spacing: -0.5px;
        }
        .hero p { font-size: 1.15rem; color: var(--text-muted); max-width: 620px; margin: 0 auto 2.5rem; }
        .hero-actions { display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; }
        .hero-visual {
            margin-top: 4rem;
            height: 320px;
            background: linear-gradient(135deg, #f5ebe0, #e8d5c4, #d4a373);
            border-radius: var(--radius);
            position: relative;
            overflow: hidden;
            box-shadow: var(--shadow);
        }
        .hero-visual::before, .hero-visual::after {
            content: ''; position: absolute; border-radius: 50%;
        }
        .hero-visual::before { width: 180px; height: 180px; background: var(--primary); opacity: 0.25; top: 10%; left: 12%; }
        .hero-visual::after { width: 220px; height: 220px; background: var(--text); opacity: 0.04; bottom: -30px; right: 15%; }

        /* ================= SECTIONS ================= */
        .section { padding: 5rem 0; }
        .section-title { text-align: center; margin-bottom: 3rem; }
        .section-title h2 { font-size: clamp(1.8rem, 4vw, 2.4rem); margin-bottom: 0.6rem; }
        .section-title p { color: var(--text-muted); max-width: 550px; margin: 0 auto; }

        /* SERVICES */
        .services-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
        .service-card {
            background: var(--surface);
            padding: 2rem;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid var(--border);
            text-align: center;
        }
        .service-card:hover { transform: translateY(-6px); box-shadow: var(--shadow-hover); border-color: var(--primary); }
        .icon { font-size: 2.2rem; margin-bottom: 1rem; display: block; }
        .service-card h3 { margin-bottom: 0.5rem; font-size: 1.25rem; }
        .service-card p { color: var(--text-muted); font-size: 0.95rem; }

        /* ABOUT */
        .about { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center; }
        .about-img { height: 380px; background: linear-gradient(45deg, #f0e6d6, #e8d5c4); border-radius: var(--radius); position: relative; }
        .about-img::after {
            content: ''; position: absolute; bottom: -15px; right: -15px; width: 100%; height: 100%;
            border: 2px solid var(--primary); border-radius: var(--radius); z-index: -1; opacity: 0.6;
        }
        .about-content h2 { font-size: 2rem; margin-bottom: 1rem; }
        .about-content p { color: var(--text-muted); margin-bottom: 1rem; }
        .features-list { list-style: none; margin-top: 1.5rem; }
        .features-list li { margin-bottom: 0.8rem; padding-left: 1.8rem; position: relative; color: var(--text); }
        .features-list li::before { content: '✓'; position: absolute; left: 0; color: var(--primary-dark); font-weight: bold; }

        /* TESTIMONIALS */
        .testimonials-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1.5rem; }
        .testimonial { background: var(--surface); padding: 2rem; border-radius: var(--radius); border-left: 4px solid var(--primary); box-shadow: var(--shadow); }
        .quote { font-style: italic; color: var(--text-muted); margin-bottom: 1rem; font-size: 1.05rem; line-height: 1.5; }
        .author { font-weight: 600; color: var(--text); }
        .role { font-size: 0.85rem; color: var(--text-muted); }

        /* NEWSLETTER */
        .contact { background: var(--surface); border-radius: var(--radius); padding: 3.5rem 2rem; text-align: center; box-shadow: var(--shadow); border: 1px solid var(--border); margin-bottom: 2rem; }
        .contact h2 { margin-bottom: 0.5rem; }
        .contact p { color: var(--text-muted); margin-bottom: 2rem; max-width: 500px; margin-left: auto; margin-right: auto; }
        .form-row { display: flex; gap: 0.5rem; justify-content: center; flex-wrap: wrap; max-width: 500px; margin: 0 auto; }
        .form-row input {
            flex: 1; min-width: 220px; padding: 0.9rem 1.2rem; border: 1px solid var(--border);
            border-radius: 50px; font-size: 1rem; outline: none; transition: var(--transition); background: var(--bg);
        }
        .form-row input:focus { border-color: var(--primary); box-shadow: 0 0 0 3px rgba(201,168,130,0.2); }

        /* FOOTER */
        footer { padding: 3rem 0 2rem; border-top: 1px solid var(--border); margin-top: 4rem; }
        .footer-content { display: flex; justify-content: space-between; flex-wrap: wrap; gap: 2rem; align-items: center; }
        .footer-logo { font-size: 1.4rem; font-weight: 700; color: var(--text); }
        .footer-links { display: flex; gap: 1.5rem; list-style: none; flex-wrap: wrap; }
        .footer-links a { text-decoration: none; color: var(--text-muted); font-size: 0.9rem; transition: var(--transition); }
        .footer-links a:hover { color: var(--text); }
        .copyright { text-align: center; margin-top: 2.5rem; color: var(--text-muted); font-size: 0.85rem; }

        /* ================= RESPONSIVE ================= */
        @media (max-width: 768px) {
            .hero { padding: 3.5rem 0 2rem; }
            .nav-links { gap: 1rem; justify-content: center; width: 100%; order: 3; padding-top: 1rem; border-top: 1px solid var(--border); margin-top: 1rem; }
            .about { grid-template-columns: 1fr; gap: 2rem; }
            .about-img { height: 280px; margin-bottom: 1rem; }
            .section { padding: 3rem 0; }
            .contact { padding: 2.5rem 1.5rem; }
        }
    </style>
</head>
<body>

    <header>
        <div class="container">
            <nav>
                <a href="#" class="logo">Lumière</a>
                <ul class="nav-links">
                    <li><a href="#services">Treatments</a></li>
                    <li><a href="#about">Philosophy</a></li>
                    <li><a href="#testimonials">Reviews</a></li>
                    <li><a href="#contact" class="btn" style="padding: 0.6rem 1.5rem; font-size: 0.85rem;">Book Now</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main>
        <section class="hero">
            <div class="container">
                <h1>Redefine Your<br> Natural Radiance</h1>
                <p>Evidence-based skincare, minimalist aesthetics, and personalized wellness rituals designed for modern life.</p>
                <div class="hero-actions">
                    <a href="#contact" class="btn">Start Your Journey</a>
                    <a href="#services" class="btn btn-outline">Explore Treatments</a>
                </div>
                <div class="hero-visual"></div>
            </div>
        </section>

        <section id="services" class="section">
            <div class="container">
                <div class="section-title">
                    <h2>Curated Treatments</h2>
                    <p>Science-backed procedures tailored to your skin's unique biology and lifestyle.</p>
                </div>
                <div class="services-grid">
                    <div class="service-card">
                        <span class="icon">✨</span>
                        <h3>HydraGlow Facial</h3>
                        <p>Deep cleansing, hydration infusion, and LED therapy for instant luminosity and long-term barrier repair.</p>
                    </div>
                    <div class="service-card">
                        <span class="icon">💆‍♀️</span>
                        <h3>Microneedling + PRP</h3>
                        <p>Stimulates collagen production and accelerates cellular renewal for smoother, firmer skin.</p>
                    </div>
                    <div class="service-card">
                        <span class="icon">🌿</span>
                        <h3>Chemical Peels</h3>
                        <p>Targeted exfoliation to correct hyperpigmentation, texture, and breakouts with minimal downtime.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="about" class="section">
            <div class="container">
                <div class="about">
                    <div class="about-img"></div>
                    <div class="about-content">
                        <h2>Beauty Rooted in Science & Balance</h2>
                        <p>We believe true radiance comes from harmony. Our approach blends clinical precision with mindful wellness, avoiding harsh treatments in favor of sustainable, visible results.</p>
                        <p>Every protocol is customized after a thorough skin analysis, ensuring your treatment aligns with your goals, skin type, and lifestyle.</p>
                        <ul class="features-list">
                            <li>Board-certified aestheticians & dermatologists</li>
                            <li>Cruelty-free, medical-grade formulations</li>
                            <li>Transparent pricing & zero pressure consultations</li>
                            <li>Results-focused, not trend-driven</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section id="testimonials" class="section">
            <div class="container">
                <div class="section-title">
                    <h2>Client Stories</h2>
                    <p>Real experiences from those who transformed their skincare routines with us.</p>
                </div>
                <div class="testimonials-grid">
                    <div class="testimonial">
                        <p class="quote">"I've tried countless clinics, but Lumière's approach actually healed my skin barrier instead of stripping it. The results speak for themselves."</p>
                        <p class="author">Elena M.</p>
                        <p class="role">Sensitive Skin Client</p>
                    </div>
                    <div class="testimonial">
                        <p class="quote">"The consultation felt like a wellness check, not a sales pitch. My microneedling sessions have completely erased my acne scarring."</p>
                        <p class="author">David R.</p>
                        <p class="role">Acne Recovery</p>
                    </div>
                    <div class="testimonial">
                        <p class="quote">"Clean, minimalist, and incredibly professional. I finally found a place that respects my skin's natural rhythm."</p>
                        <p class="author">Sophia L.</p>
                        <p class="role">Anti-Aging Program</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact" class="section">
            <div class="container">
                <div class="contact">
                    <h2>Begin Your Transformation</h2>
                    <p>Join our newsletter for skincare tips, seasonal promotions, and early access to new treatments.</p>
                    <form class="form-row" action="#" method="post">
                        <input type="email" placeholder="Enter your email address" required aria-label="Email Address">
                        <button type="submit" class="btn">Subscribe</button>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div>
                    <p class="footer-logo">Lumière</p>
                    <p style="color: var(--text-muted); font-size: 0.9rem;">Modern aesthetic care, redefined.</p>
                </div>
                <ul class="footer-links">
                    <li><a href="#services">Treatments</a></li>
                    <li><a href="#about">Philosophy</a></li>
                    <li><a href="#contact">Contact</a></li>
                    <li><a href="#">Privacy Policy</a></li>
                </ul>
            </div>
            <p class="copyright">&copy; 2026 Lumière Beauty. All rights reserved. Designed for educational & reference use.</p>
        </div>
    </footer>

</body>
</html>
