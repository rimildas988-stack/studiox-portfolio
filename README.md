# studiox-portfolio
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <link href="https://fonts.googleapis.com/css2?family=Black+Ops+One&family=Orbitron:wght@400;500;700;900&family=Space+Grotesk:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* === CSS VARIABLES: BLUE FLAME BEAST THEME === */
        :root {
            --bg-base: #020617; /* Very dark blue/black */
            --bg-surface: rgba(15, 23, 42, 0.7);
            --neon-primary: #00e5ff; /* Cyan blue flame */
            --neon-secondary: #0055ff; /* Deep royal blue flame */
            --neon-accent: #3b82f6; 
            --text-main: #ffffff;
            --text-muted: #94a3b8;
            --font-logo: 'Black Ops One', sans-serif;
            --font-display: 'Orbitron', sans-serif;
            --font-body: 'Space Grotesk', sans-serif;
            --glass-border: rgba(0, 229, 255, 0.15);
            --transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }

        /* === RESET & GLOBAL === */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            cursor: none; /* Custom Cursor */
        }
        
        html {
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-base);
            color: var(--text-main);
            font-family: var(--font-body);
            overflow-x: hidden;
            position: relative;
        }

        /* === CUSTOM CURSOR === */
        .cursor-dot, .cursor-outline {
            position: fixed;
            top: 0;
            left: 0;
            transform: translate(-50%, -50%);
            border-radius: 50%;
            z-index: 9999;
            pointer-events: none;
        }
        .cursor-dot {
            width: 8px;
            height: 8px;
            background-color: var(--neon-primary);
            box-shadow: 0 0 10px var(--neon-primary), 0 0 20px var(--neon-secondary);
        }
        .cursor-outline {
            width: 40px;
            height: 40px;
            border: 2px solid rgba(0, 229, 255, 0.5);
            transition: width 0.2s, height 0.2s, background-color 0.2s;
            box-shadow: inset 0 0 10px rgba(0, 85, 255, 0.3);
        }

        /* === BLUE FLAME BEAST BACKGROUND === */
        .bg-grid {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background-image: 
                linear-gradient(to right, rgba(0, 229, 255, 0.03) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(0, 229, 255, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            z-index: -3;
        }
        
        /* Simulating the beast aura/flames */
        .flame-aura {
            position: fixed;
            border-radius: 50%;
            filter: blur(120px);
            z-index: -2;
            opacity: 0.4;
            animation: breathe 8s infinite alternate ease-in-out;
            mix-blend-mode: screen;
        }
        .flame-1 {
            width: 60vw; height: 60vh;
            bottom: -20vh; left: -10vw;
            background: radial-gradient(circle, var(--neon-secondary) 0%, transparent 70%);
        }
        .flame-2 {
            width: 50vw; height: 50vh;
            top: -10vh; right: -10vw;
            background: radial-gradient(circle, var(--neon-primary) 0%, transparent 70%);
            animation-delay: -4s;
        }
        .flame-3 {
            width: 40vw; height: 40vh;
            top: 30vh; left: 30vw;
            background: radial-gradient(circle, #0011ff 0%, transparent 70%);
            animation-duration: 6s;
        }
        
        @keyframes breathe {
            0% { transform: scale(0.8) translateY(20px); opacity: 0.3; }
            100% { transform: scale(1.2) translateY(-20px); opacity: 0.6; }
        }

        /* === TYPOGRAPHY & UTILITIES === */
        h1, h2, h3, h4 { font-family: var(--font-display); text-transform: uppercase; }
        
        /* New Logo Font - Black Ops One with Blue Flame glow */
        .brand { 
            font-family: var(--font-logo); 
            font-size: 2.5rem; 
            letter-spacing: 3px; 
            color: #fff;
            text-decoration: none;
            text-shadow: 
                0 0 5px var(--neon-primary),
                0 0 10px var(--neon-primary),
                0 0 20px var(--neon-secondary),
                0 0 40px var(--neon-secondary);
            animation: flicker 3s infinite alternate;
        }
        .brand span { color: var(--neon-primary); }

        @keyframes flicker {
            0%, 100% { text-shadow: 0 0 5px var(--neon-primary), 0 0 10px var(--neon-primary), 0 0 20px var(--neon-secondary), 0 0 40px var(--neon-secondary); }
            50% { text-shadow: 0 0 2px var(--neon-primary), 0 0 5px var(--neon-primary), 0 0 10px var(--neon-secondary), 0 0 20px var(--neon-secondary); }
        }

        .text-gradient {
            background: linear-gradient(90deg, var(--neon-primary), var(--neon-secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 20px rgba(0, 229, 255, 0.3);
        }
        .glass-card {
            background: var(--bg-surface);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 2rem;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            box-shadow: inset 0 0 20px rgba(0, 229, 255, 0.02);
        }
        .glass-card:hover {
            border-color: var(--neon-primary);
            transform: translateY(-5px);
            box-shadow: 0 10px 40px rgba(0, 85, 255, 0.2), inset 0 0 20px rgba(0, 229, 255, 0.1);
        }

        /* === BUTTONS === */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            padding: 1rem 2rem;
            border-radius: 4px; /* Sharper edges for gaming vibe */
            font-family: var(--font-display);
            font-weight: 700;
            text-decoration: none;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            z-index: 1;
            clip-path: polygon(10px 0, 100% 0, 100% calc(100% - 10px), calc(100% - 10px) 100%, 0 100%, 0 10px); /* Cyberpunk cut corners */
        }
        .btn-glow {
            background: rgba(0, 85, 255, 0.2);
            color: var(--text-main);
            border: 1px solid var(--neon-primary);
            box-shadow: 0 0 15px rgba(0, 229, 255, 0.3);
        }
        .btn-glow::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 0%; height: 100%;
            background: linear-gradient(90deg, var(--neon-secondary), var(--neon-primary));
            z-index: -1;
            transition: var(--transition);
        }
        .btn-glow:hover {
            color: #fff;
            box-shadow: 0 0 40px rgba(0, 229, 255, 0.8);
            border-color: #fff;
        }
        .btn-glow:hover::before { width: 100%; }

        .btn-outline {
            background: rgba(0,0,0,0.5);
            color: var(--neon-primary);
            border: 1px solid rgba(0, 229, 255, 0.3);
        }
        .btn-outline:hover {
            background: rgba(0, 229, 255, 0.1);
            border-color: var(--neon-primary);
            box-shadow: 0 0 20px rgba(0, 229, 255, 0.4);
        }

        /* === NAVBAR === */
        header {
            position: fixed;
            top: 0; width: 100%;
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            transition: var(--transition);
        }
        header.scrolled {
            background: rgba(2, 6, 23, 0.9);
            backdrop-filter: blur(20px);
            padding: 1rem 5%;
            border-bottom: 1px solid var(--neon-secondary);
            box-shadow: 0 4px 30px rgba(0, 85, 255, 0.3);
        }
        .nav-links { display: flex; gap: 2rem; list-style: none; }
        .nav-links a { color: var(--text-main); text-decoration: none; font-weight: 600; text-transform: uppercase; font-size: 0.9rem; letter-spacing: 1px; transition: var(--transition); }
        .nav-links a:hover { color: var(--neon-primary); text-shadow: 0 0 15px var(--neon-primary); }

        /* === LAYOUT / SECTIONS === */
        section { padding: 8rem 5% 4rem; min-height: 100vh; display: flex; flex-direction: column; justify-content: center; }
        .section-header { text-align: center; margin-bottom: 4rem; }
        .section-header h2 { font-size: 3.5rem; margin-bottom: 1rem; text-shadow: 0 0 20px rgba(0, 85, 255, 0.5); }
        .section-header p { color: var(--text-muted); font-size: 1.2rem; max-width: 600px; margin: 0 auto; }

        /* === HERO SECTION === */
        .hero { text-align: center; position: relative; padding-top: 12rem; }
        .hero h1 { font-size: clamp(2.5rem, 6vw, 5rem); line-height: 1.2; margin-bottom: 1.5rem; text-shadow: 0 0 30px rgba(0, 229, 255, 0.2); }
        .hero p { font-size: 1.2rem; color: var(--text-muted); max-width: 800px; margin: 0 auto 3rem; line-height: 1.6; }
        .hero-btns { display: flex; gap: 1.5rem; justify-content: center; margin-bottom: 4rem; }
        .quote-box {
            display: inline-block;
            padding: 1.5rem 2.5rem;
            border-left: 4px solid var(--neon-primary);
            background: linear-gradient(90deg, rgba(0, 85, 255, 0.15), transparent);
            font-style: italic;
            color: #e2e8f0;
            font-size: 1.1rem;
            border-radius: 0 10px 10px 0;
            box-shadow: inset 20px 0 30px -20px var(--neon-secondary);
        }

        /* === ABOUT SECTION (WITH GAMING DEV IMAGE) === */
        .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center; }
        .about-text p { font-size: 1.1rem; color: var(--text-muted); line-height: 1.8; margin-bottom: 2rem; }
        .industries { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; list-style: none; margin-bottom: 2rem; }
        .industries li { display: flex; align-items: center; gap: 0.5rem; color: var(--neon-primary); font-weight: 600; text-shadow: 0 0 10px rgba(0, 229, 255, 0.4); }
        .industries li i { font-size: 1rem; }
        
        /* New Image Wrapper Styling */
        .about-image-wrapper {
            position: relative;
            border-radius: 16px;
            padding: 10px;
            background: linear-gradient(135deg, var(--neon-primary), var(--neon-secondary));
            box-shadow: 0 0 40px rgba(0, 85, 255, 0.4);
            animation: floatImg 6s ease-in-out infinite;
        }
        .about-image-wrapper::before {
            content: '';
            position: absolute;
            top: -10px; left: -10px; right: -10px; bottom: -10px;
            border: 2px dashed var(--neon-primary);
            border-radius: 20px;
            animation: rotateBorder 20s linear infinite;
            opacity: 0.5;
            pointer-events: none;
        }
        .about-image-wrapper img {
            width: 100%;
            height: auto;
            border-radius: 12px;
            display: block;
            filter: contrast(1.2) saturate(1.2);
        }
        .dev-badge {
            position: absolute;
            bottom: -20px;
            right: -20px;
            background: var(--bg-base);
            border: 2px solid var(--neon-primary);
            padding: 1rem;
            border-radius: 8px;
            font-family: var(--font-display);
            font-weight: 700;
            color: var(--neon-primary);
            box-shadow: 0 0 20px rgba(0, 229, 255, 0.5);
        }

        @keyframes floatImg {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }
        @keyframes rotateBorder {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* === SERVICES SECTION === */
        .services-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; }
        .service-icon { font-size: 2.5rem; color: var(--neon-primary); margin-bottom: 1.5rem; display: inline-block; filter: drop-shadow(0 0 15px rgba(0, 229, 255, 0.8)); transition: var(--transition); }
        .service-card:hover .service-icon { transform: scale(1.1) rotate(-5deg); color: #fff; filter: drop-shadow(0 0 20px var(--neon-primary)); }
        .service-card h3 { font-size: 1.5rem; margin-bottom: 1rem; color: #fff; }
        .service-card p { color: var(--text-muted); line-height: 1.6; }

        /* === PORTFOLIO SECTION === */
        .portfolio-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); gap: 2.5rem; }
        .portfolio-card { padding: 1rem; background: var(--bg-surface); border-radius: 16px; border: 1px solid var(--glass-border); transition: var(--transition); }
        .portfolio-card:hover { transform: translateY(-10px) scale(1.02); border-color: var(--neon-primary); box-shadow: 0 15px 50px rgba(0, 85, 255, 0.3); }
        .mockup {
            height: 220px; border-radius: 8px; margin-bottom: 1.5rem; position: relative; overflow: hidden;
            background: linear-gradient(135deg, #0f172a 0%, #020617 100%);
            display: flex; align-items: center; justify-content: center;
            border: 1px solid rgba(0, 229, 255, 0.1);
        }
        .mockup i { font-size: 5rem; color: rgba(0, 229, 255, 0.15); transition: var(--transition); }
        .portfolio-card:hover .mockup i { color: var(--neon-primary); filter: drop-shadow(0 0 15px var(--neon-primary)); transform: scale(1.1); }
        .portfolio-info h3 { font-size: 1.3rem; margin-bottom: 0.5rem; }
        .portfolio-info p { color: var(--text-muted); font-size: 0.9rem; margin-bottom: 1.5rem; }
        .portfolio-info .btn { width: 100%; padding: 0.8rem; font-size: 0.9rem; }

        /* === REVIEWS SECTION === */
        .reviews-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; }
        .review-card { padding: 2.5rem 2rem; border-top: 4px solid var(--neon-secondary); }
        .stars { color: var(--neon-primary); margin-bottom: 1rem; letter-spacing: 2px; font-size: 1.2rem; text-shadow: 0 0 10px var(--neon-primary); }
        .review-text { font-size: 1.1rem; font-style: italic; margin-bottom: 1.5rem; line-height: 1.6; color: #cbd5e1; }
        .reviewer { font-weight: 700; color: #fff; font-family: var(--font-display); }

        /* === CONTACT SECTION === */
        .contact-container { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; background: rgba(15, 23, 42, 0.4); border: 1px solid var(--glass-border); border-radius: 24px; padding: 4rem; box-shadow: 0 0 50px rgba(0,0,0,0.5); }
        .contact-info h2 { font-size: 2.5rem; margin-bottom: 1rem; }
        .contact-info p { color: var(--text-muted); margin-bottom: 3rem; font-size: 1.1rem; }
        .contact-methods { display: flex; flex-direction: column; gap: 1.5rem; }
        .contact-method { display: flex; align-items: center; gap: 1.5rem; padding: 1.5rem; background: rgba(0, 0, 0, 0.5); border: 1px solid var(--glass-border); border-radius: 12px; transition: var(--transition); }
        .contact-method:hover { border-color: var(--neon-primary); background: rgba(0, 85, 255, 0.1); box-shadow: inset 0 0 20px rgba(0, 229, 255, 0.1); }
        .contact-method i { font-size: 2.2rem; color: var(--neon-primary); filter: drop-shadow(0 0 5px var(--neon-primary)); }
        .contact-method div h4 { font-size: 1.1rem; color: var(--text-muted); margin-bottom: 0.2rem; text-transform: uppercase; font-family: var(--font-display); }
        .contact-method div a { color: var(--text-main); text-decoration: none; font-size: 1.2rem; font-weight: 600; }
        
        /* === FOOTER === */
        footer { border-top: 1px solid rgba(0, 229, 255, 0.2); padding: 4rem 5% 2rem; text-align: center; background: #010208; position: relative; overflow: hidden; }
        footer::before { content: ''; position: absolute; bottom: 0; left: 50%; transform: translateX(-50%); width: 50%; height: 50px; background: var(--neon-secondary); filter: blur(80px); opacity: 0.5; }
        .social-icons { display: flex; justify-content: center; gap: 1.5rem; margin: 2rem 0; position: relative; z-index: 1; }
        .social-icons a { color: var(--text-muted); font-size: 1.8rem; transition: var(--transition); }
        .social-icons a:hover { color: var(--neon-primary); transform: translateY(-5px); filter: drop-shadow(0 0 15px var(--neon-primary)); }
        .footer-bottom { color: var(--text-muted); font-size: 0.9rem; margin-top: 2rem; position: relative; z-index: 1; }

        /* === ANIMATIONS (SCROLL REVEAL) === */
        .reveal { opacity: 0; transform: translateY(50px); transition: all 0.8s cubic-bezier(0.5, 0, 0, 1); }
        .reveal.active { opacity: 1; transform: translateY(0); }

        /* === RESPONSIVE === */
        @media (max-width: 968px) {
            .about-grid, .contact-container { grid-template-columns: 1fr; }
            .nav-links { display: none; } 
            header { padding: 1rem 5%; }
            .contact-container { padding: 2rem; }
            .about-image-wrapper { margin-top: 2rem; }
        }
    </style>
</head>
<body>

    <div class="bg-grid"></div>
    <div class="flame-aura flame-1"></div>
    <div class="flame-aura flame-2"></div>
    <div class="flame-aura flame-3"></div>

    <div class="cursor-dot"></div>
    <div class="cursor-outline"></div>

    <header id="header">
        <a href="#" class="brand">STUDIO<span>X</span></a>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#portfolio">Portfolio</a></li>
            <li><a href="#reviews">Reviews</a></li>
        </ul>
        <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-glow">Start Project</a>
    </header>

    <section id="home" class="hero">
        <h1 class="reveal">We Build Websites That <br><span class="text-gradient">Sell, Scale & Dominate</span></h1>
        <p class="reveal" style="transition-delay: 0.1s;">Premium websites for brands, startups, cafes, restaurants, stores, creators, and gaming businesses. Built by elite developers for maximum performance.</p>
        <div class="hero-btns reveal" style="transition-delay: 0.2s;">
            <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-glow"><i class="fa-solid fa-power-off" style="margin-right: 10px;"></i> Start Project</a>
            <a href="#portfolio" class="btn btn-outline">View Portfolio</a>
        </div>
        <div class="quote-box reveal" style="transition-delay: 0.3s;">
            "Your brand deserves more than a website — it deserves dominance."
        </div>
    </section>

    <section id="about">
        <div class="about-grid">
            <div class="about-text reveal">
                <h2 class="text-gradient" style="font-size: 2.5rem; margin-bottom: 1.5rem;">The StudioX Standard</h2>
                <p>StudioX is a premium web design and digital experience agency focused on building powerful websites that create trust, attract customers, and grow businesses. We combine modern design, strategy, and developer-level execution to deliver websites that look elite and perform like machines.</p>
                <p>We create dominating digital presences for:</p>
                <ul class="industries">
                    <li><i class="fa-solid fa-crosshairs"></i> Restaurants & Cafes</li>
                    <li><i class="fa-solid fa-crosshairs"></i> Gaming & Esports</li>
                    <li><i class="fa-solid fa-crosshairs"></i> Furniture Stores</li>
                    <li><i class="fa-solid fa-crosshairs"></i> Clothing Brands</li>
                    <li><i class="fa-solid fa-crosshairs"></i> Tech Startups</li>
                    <li><i class="fa-solid fa-crosshairs"></i> Personal Brands</li>
                    <li><i class="fa-solid fa-crosshairs"></i> E-commerce Stores</li>
                    <li><i class="fa-solid fa-crosshairs"></i> Agencies</li>
                </ul>
                <div class="quote-box" style="margin-top: 1rem;">
                    "Success begins where ordinary design ends."
                </div>
            </div>
            
            <div class="reveal" style="transition-delay: 0.2s; display: flex; justify-content: center; align-items: center;">
                <div class="about-image-wrapper">
                    <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?auto=format&fit=crop&w=800&q=80" alt="Gaming Web Developer">
                    <div class="dev-badge">
                        <i class="fa-solid fa-code"></i> Elite Dev Level
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="services">
        <div class="section-header reveal">
            <h2>Elite <span class="text-gradient">Services</span></h2>
            <p>We don't just build websites; we engineer digital ecosystems designed for conversion, speed, and absolute aesthetic dominance.</p>
        </div>
        <div class="services-grid">
            <div class="glass-card service-card reveal">
                <i class="fa-solid fa-laptop-code service-icon"></i>
                <h3>Premium Web Design</h3>
                <p>Custom-coded, high-performance websites with ultra-modern aesthetics and developer-level execution.</p>
            </div>
            <div class="glass-card service-card reveal" style="transition-delay: 0.1s;">
                <i class="fa-solid fa-gamepad service-icon"></i>
                <h3>Gaming & Esports</h3>
                <p>Aggressive, high-energy layouts with 3D elements and blue neon glows tailored specifically for the gaming industry.</p>
            </div>
            <div class="glass-card service-card reveal" style="transition-delay: 0.2s;">
                <i class="fa-solid fa-cart-shopping service-icon"></i>
                <h3>E-commerce Stores</h3>
                <p>Conversion-optimized online stores designed to make your products look expensive and maximize sales.</p>
            </div>
            <div class="glass-card service-card reveal">
                <i class="fa-solid fa-vr-cardboard service-icon"></i>
                <h3>UI/UX Design</h3>
                <p>Flawless user journeys, micro-interactions, and glassmorphism effects that feel like a premium application.</p>
            </div>
            <div class="glass-card service-card reveal" style="transition-delay: 0.1s;">
                <i class="fa-solid fa-bolt service-icon"></i>
                <h3>Fast Performance</h3>
                <p>Optimized assets, clean code architecture, and lightning-fast load times to outrank competitors instantly.</p>
            </div>
            <div class="glass-card service-card reveal" style="transition-delay: 0.2s;">
                <i class="fa-solid fa-rocket service-icon"></i>
                <h3>Landing Pages</h3>
                <p>High-converting, single-page architectures built specifically for ad campaigns and product launches.</p>
            </div>
        </div>
        <div class="text-center" style="margin-top: 4rem; text-align: center;">
            <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-glow">Start Project</a>
        </div>
    </section>

    <section id="portfolio">
        <div class="section-header reveal">
            <h2>Featured <span class="text-gradient">Projects</span></h2>
            <p>Explore our premium mockups. Every interface is built with military-grade precision and luxury aesthetics.</p>
        </div>
        <div class="portfolio-grid">
            <div class="portfolio-card reveal">
                <div class="mockup"><i class="fa-solid fa-headset"></i></div>
                <div class="portfolio-info">
                    <h3>Esports Team Hub</h3>
                    <p>Dynamic roster layout, tournament tracking, and neon merchandise store.</p>
                    <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-outline">View Demo</a>
                </div>
            </div>
            <div class="portfolio-card reveal" style="transition-delay: 0.1s;">
                <div class="mockup"><i class="fa-solid fa-utensils"></i></div>
                <div class="portfolio-info">
                    <h3>Luxury Restaurant</h3>
                    <p>Immersive menu experience with parallax scrolling and reservation integration.</p>
                    <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-outline">View Demo</a>
                </div>
            </div>
            <div class="portfolio-card reveal" style="transition-delay: 0.2s;">
                <div class="mockup"><i class="fa-solid fa-building"></i></div>
                <div class="portfolio-info">
                    <h3>Business Agency</h3>
                    <p>Corporate trust-building architecture with glassmorphic data visualization.</p>
                    <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-outline">View Demo</a>
                </div>
            </div>
            <div class="portfolio-card reveal">
                <div class="mockup"><i class="fa-solid fa-couch"></i></div>
                <div class="portfolio-info">
                    <h3>Premium Furniture</h3>
                    <p>Minimalist, high-end catalog with 3D product viewing capabilities.</p>
                    <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-outline">View Demo</a>
                </div>
            </div>
            <div class="portfolio-card reveal" style="transition-delay: 0.1s;">
                <div class="mockup"><i class="fa-solid fa-mobile-screen"></i></div>
                <div class="portfolio-info">
                    <h3>App Landing Page</h3>
                    <p>High-conversion scroll-jacking layout for a SaaS tech startup.</p>
                    <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-outline">View Demo</a>
                </div>
            </div>
            <div class="portfolio-card reveal" style="transition-delay: 0.2s;">
                <div class="mockup"><i class="fa-solid fa-shirt"></i></div>
                <div class="portfolio-info">
                    <h3>Clothing Brand</h3>
                    <p>Streetwear e-commerce drop site with countdown timers and secure checkout.</p>
                    <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-outline">View Demo</a>
                </div>
            </div>
        </div>
        <div class="text-center" style="margin-top: 4rem; text-align: center;">
            <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-glow">Start Your Project</a>
        </div>
    </section>

    <section id="reviews">
        <div class="section-header reveal">
            <h2>Client <span class="text-gradient">Domination</span></h2>
            <p>Motivation Line: "People trust what looks powerful."</p>
        </div>
        <div class="reviews-grid">
            <div class="glass-card review-card reveal">
                <div class="stars"><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i></div>
                <p class="review-text">“StudioX made my restaurant website look world-class. Customers trust us more now. The design is absolutely flawless.”</p>
                <p class="reviewer">— Rahul S.</p>
            </div>
            <div class="glass-card review-card reveal" style="transition-delay: 0.1s;">
                <div class="stars"><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i></div>
                <p class="review-text">“The design quality feels like a ₹1 lakh agency project. Highly recommended for any serious business owner.”</p>
                <p class="reviewer">— Priya M.</p>
            </div>
            <div class="glass-card review-card reveal" style="transition-delay: 0.2s;">
                <div class="stars"><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i></div>
                <p class="review-text">“Professional, fast, and premium. My gaming store website looks amazing and sales have actually increased.”</p>
                <p class="reviewer">— Arjun K.</p>
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="contact-container reveal">
            <div class="contact-info">
                <h2>Let’s Build Something <br><span class="text-gradient">Powerful Together</span></h2>
                <p>Ready to upgrade your digital presence to the elite level? Reach out to us directly or fill out the project form to get started instantly.</p>
                
                <div class="contact-methods">
                    <div class="contact-method">
                        <i class="fa-brands fa-whatsapp"></i>
                        <div>
                            <h4>WhatsApp Direct</h4>
                            <a href="https://wa.me/917029828029">+91 7029828029</a>
                        </div>
                    </div>
                    <div class="contact-method">
                        <i class="fa-regular fa-envelope"></i>
                        <div>
                            <h4>Email for Enquiry</h4>
                            <a href="mailto:rimildas988@gmail.com">rimildas988@gmail.com</a>
                        </div>
                    </div>
                </div>
            </div>
            <div style="display: flex; align-items: center; justify-content: center;">
                <div class="glass-card" style="text-align: center; width: 100%; padding: 4rem 2rem;">
                    <i class="fa-solid fa-power-off" style="font-size: 4rem; color: var(--neon-primary); margin-bottom: 1.5rem; filter: drop-shadow(0 0 20px var(--neon-primary));"></i>
                    <h3 style="margin-bottom: 2rem; font-size: 1.5rem; color: #fff;">Initialize Project</h3>
                    <a href="https://forms.gle/Eg22wwkZbMUaqMHK6" target="_blank" class="btn btn-glow" style="width: 100%;">Access Secure Form</a>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <a href="#" class="brand">STUDIO<span>X</span></a>
        <div class="social-icons">
            <a href="#"><i class="fa-brands fa-instagram"></i></a>
            <a href="#"><i class="fa-brands fa-x-twitter"></i></a>
            <a href="#"><i class="fa-brands fa-discord"></i></a>
            <a href="#"><i class="fa-brands fa-linkedin"></i></a>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2026 StudioX Premium Digital Agency. Built for Dominance.</p>
        </div>
    </footer>

    <script>
        // Custom Cursor Logic
        const cursorDot = document.querySelector('.cursor-dot');
        const cursorOutline = document.querySelector('.cursor-outline');

        window.addEventListener('mousemove', (e) => {
            const posX = e.clientX;
            const posY = e.clientY;

            cursorDot.style.left = `${posX}px`;
            cursorDot.style.top = `${posY}px`;

            cursorOutline.animate({
                left: `${posX}px`,
                top: `${posY}px`
            }, { duration: 500, fill: "forwards" });
        });

        // Hover effect for cursor
        const interactables = document.querySelectorAll('a, .btn, .service-card, .portfolio-card, .review-card, .about-image-wrapper');
        interactables.forEach(el => {
            el.addEventListener('mouseenter', () => {
                cursorOutline.style.width = '70px';
                cursorOutline.style.height = '70px';
                cursorOutline.style.backgroundColor = 'rgba(0, 229, 255, 0.1)';
                cursorOutline.style.borderColor = 'rgba(0, 85, 255, 0.8)';
            });
            el.addEventListener('mouseleave', () => {
                cursorOutline.style.width = '40px';
                cursorOutline.style.height = '40px';
                cursorOutline.style.backgroundColor = 'transparent';
                cursorOutline.style.borderColor = 'rgba(0, 229, 255, 0.5)';
            });
        });

        // Sticky Header Effect
        const header = document.getElementById('header');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Scroll Reveal Animation (Intersection Observer)
        const reveals = document.querySelectorAll('.reveal');
        const revealOptions = {
            threshold: 0.15,
            rootMargin: "0px 0px -50px 0px"
        };

        const revealOnScroll = new IntersectionObserver(function(entries, observer) {
            entries.forEach(entry => {
                if (!entry.isIntersecting) return;
                entry.target.classList.add('active');
                observer.unobserve(entry.target);
            });
        }, revealOptions);

        reveals.forEach(reveal => {
            revealOnScroll.observe(reveal);
        });
    </script>
</body>
</html>
