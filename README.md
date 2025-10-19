<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexora - Build a Website That Converts</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif;
            line-height: 1.6;
            color: #1a1a1a;
            background: #ffffff;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 40px;
        }
        
        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid #e5e5e5;
            z-index: 1000;
            transition: all 0.3s ease;
        }
        
        nav.scrolled {
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.05);
        }
        
        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 28px;
            font-weight: 700;
            color: #6366f1;
            letter-spacing: -1px;
        }
        
        .nav-links {
            display: flex;
            gap: 40px;
            align-items: center;
        }
        
        .nav-links a {
            color: #4a4a4a;
            text-decoration: none;
            font-size: 15px;
            font-weight: 500;
            transition: color 0.3s ease;
        }
        
        .nav-links a:hover {
            color: #6366f1;
        }
        
        .nav-cta {
            background: #6366f1;
            color: white;
            padding: 12px 24px;
            border-radius: 6px;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .nav-cta:hover {
            background: #4f46e5;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(99, 102, 241, 0.3);
        }
        
        /* Hero Section */
        .hero {
            padding: 180px 0 120px;
            background: linear-gradient(135deg, #f8f9ff 0%, #ffffff 100%);
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 800px;
            height: 800px;
            background: radial-gradient(circle, rgba(99, 102, 241, 0.1) 0%, transparent 70%);
            animation: float 20s infinite ease-in-out;
        }
        
        @keyframes float {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            50% { transform: translate(-50px, -50px) rotate(180deg); }
        }
        
        .hero-content {
            max-width: 700px;
            position: relative;
            z-index: 1;
        }
        
        .hero h1 {
            font-size: 64px;
            font-weight: 700;
            line-height: 1.1;
            letter-spacing: -2px;
            margin-bottom: 24px;
            color: #0a0a0a;
            animation: fadeInUp 0.8s ease;
        }
        
        .hero h1 .highlight {
            color: #6366f1;
        }
        
        .hero p {
            font-size: 20px;
            color: #4a4a4a;
            line-height: 1.6;
            margin-bottom: 40px;
            animation: fadeInUp 0.8s ease 0.2s backwards;
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .hero-cta {
            display: flex;
            gap: 16px;
            animation: fadeInUp 0.8s ease 0.4s backwards;
        }
        
        .btn-primary {
            background: #6366f1;
            color: white;
            padding: 18px 36px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }
        
        .btn-primary:hover {
            background: #4f46e5;
            transform: translateY(-3px);
            box-shadow: 0 8px 24px rgba(99, 102, 241, 0.4);
        }
        
        .btn-secondary {
            background: white;
            color: #6366f1;
            padding: 18px 36px;
            border: 2px solid #6366f1;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }
        
        .btn-secondary:hover {
            background: #6366f1;
            color: white;
            transform: translateY(-3px);
        }
        
        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 40px;
            padding: 60px 0;
            border-bottom: 1px solid #e5e5e5;
        }
        
        .stat-item {
            text-align: center;
        }
        
        .stat-number {
            font-size: 48px;
            font-weight: 700;
            color: #6366f1;
            margin-bottom: 8px;
        }
        
        .stat-label {
            font-size: 16px;
            color: #4a4a4a;
        }
        
        /* Problem Section */
        .problem-section {
            padding: 120px 0;
            background: #fafafa;
        }
        
        .section-header {
            text-align: center;
            max-width: 700px;
            margin: 0 auto 80px;
        }
        
        .section-tag {
            display: inline-block;
            background: #ede9fe;
            color: #6366f1;
            padding: 6px 16px;
            border-radius: 20px;
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 16px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        
        .section-header h2 {
            font-size: 48px;
            font-weight: 700;
            letter-spacing: -1px;
            margin-bottom: 20px;
            color: #0a0a0a;
        }
        
        .section-header p {
            font-size: 18px;
            color: #4a4a4a;
            line-height: 1.7;
        }
        
        .problem-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 40px;
        }
        
        .problem-card {
            background: white;
            padding: 40px;
            border-radius: 12px;
            border: 1px solid #e5e5e5;
            transition: all 0.3s ease;
        }
        
        .problem-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 40px rgba(0, 0, 0, 0.08);
        }
        
        .problem-icon {
            font-size: 40px;
            margin-bottom: 24px;
        }
        
        .problem-card h3 {
            font-size: 24px;
            font-weight: 600;
            margin-bottom: 16px;
            color: #0a0a0a;
        }
        
        .problem-card p {
            font-size: 16px;
            color: #4a4a4a;
            line-height: 1.7;
            margin-bottom: 20px;
        }
        
        .solution-tag {
            display: inline-block;
            background: #dcfce7;
            color: #16a34a;
            padding: 4px 12px;
            border-radius: 4px;
            font-size: 13px;
            font-weight: 600;
        }
        
        /* Services Section */
        .services-section {
            padding: 120px 0;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 32px;
        }
        
        .service-card {
            background: #fafafa;
            padding: 48px 32px;
            border-radius: 12px;
            text-align: center;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }
        
        .service-card:hover {
            background: white;
            border-color: #6366f1;
            transform: translateY(-8px);
            box-shadow: 0 12px 40px rgba(99, 102, 241, 0.15);
        }
        
        .service-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 36px;
            margin: 0 auto 24px;
        }
        
        .service-card h3 {
            font-size: 24px;
            font-weight: 600;
            margin-bottom: 16px;
            color: #0a0a0a;
        }
        
        .service-card p {
            font-size: 15px;
            color: #4a4a4a;
            line-height: 1.7;
            margin-bottom: 20px;
        }
        
        .service-features {
            text-align: left;
            margin-top: 24px;
            padding-top: 24px;
            border-top: 1px solid #e5e5e5;
        }
        
        .service-features li {
            font-size: 14px;
            color: #4a4a4a;
            margin-bottom: 8px;
            padding-left: 24px;
            position: relative;
        }
        
        .service-features li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #6366f1;
            font-weight: 700;
        }
        
        /* Portfolio Section */
        .portfolio-section {
            padding: 120px 0;
            background: #fafafa;
        }
        
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 48px;
        }
        
        .portfolio-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid #e5e5e5;
            transition: all 0.3s ease;
        }
        
        .portfolio-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 16px 48px rgba(0, 0, 0, 0.1);
        }
        
        .portfolio-image {
            height: 300px;
            background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 48px;
            font-weight: 700;
            position: relative;
            overflow: hidden;
        }
        
        .portfolio-image::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: repeating-linear-gradient(
                45deg,
                rgba(255, 255, 255, 0.05),
                rgba(255, 255, 255, 0.05) 10px,
                transparent 10px,
                transparent 20px
            );
        }
        
        .portfolio-content {
            padding: 32px;
        }
        
        .portfolio-content h3 {
            font-size: 24px;
            font-weight: 600;
            margin-bottom: 12px;
            color: #0a0a0a;
        }
        
        .portfolio-content p {
            font-size: 15px;
            color: #4a4a4a;
            line-height: 1.7;
            margin-bottom: 24px;
        }
        
        .portfolio-stats {
            display: flex;
            gap: 32px;
            padding-top: 24px;
            border-top: 1px solid #e5e5e5;
        }
        
        .portfolio-stat {
            flex: 1;
        }
        
        .portfolio-stat-value {
            font-size: 32px;
            font-weight: 700;
            color: #6366f1;
            margin-bottom: 4px;
        }
        
        .portfolio-stat-label {
            font-size: 13px;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        
        /* Testimonials Section */
        .testimonials-section {
            padding: 120px 0;
        }
        
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 32px;
        }
        
        .testimonial-card {
            background: #fafafa;
            padding: 40px;
            border-radius: 12px;
            border: 1px solid #e5e5e5;
            transition: all 0.3s ease;
        }
        
        .testimonial-card:hover {
            background: white;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.08);
        }
        
        .stars {
            color: #f59e0b;
            font-size: 20px;
            margin-bottom: 20px;
        }
        
        .testimonial-text {
            font-size: 16px;
            color: #1a1a1a;
            line-height: 1.7;
            margin-bottom: 24px;
            font-style: italic;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 16px;
        }
        
        .author-avatar {
            width: 48px;
            height: 48px;
            background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 700;
            font-size: 18px;
        }
        
        .author-info h4 {
            font-size: 16px;
            font-weight: 600;
            color: #0a0a0a;
            margin-bottom: 2px;
        }
        
        .author-info p {
            font-size: 14px;
            color: #666;
        }
        
        /* CTA Section */
        .cta-section {
            padding: 120px 0;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            color: white;
            position: relative;
            overflow: hidden;
        }
        
        .cta-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -25%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(99, 102, 241, 0.2) 0%, transparent 70%);
            animation: float 15s infinite ease-in-out;
        }
        
        .cta-content {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
            position: relative;
            z-index: 1;
        }
        
        .cta-content h2 {
            font-size: 48px;
            font-weight: 700;
            letter-spacing: -1px;
            margin-bottom: 20px;
        }
        
        .cta-content p {
            font-size: 18px;
            color: #ccc;
            margin-bottom: 48px;
            line-height: 1.7;
        }
        
        .cta-form {
            background: white;
            padding: 48px;
            border-radius: 16px;
            max-width: 600px;
            margin: 0 auto;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }
        
        .form-group {
            margin-bottom: 24px;
            text-align: left;
        }
        
        .form-group label {
            display: block;
            font-size: 14px;
            font-weight: 600;
            color: #0a0a0a;
            margin-bottom: 8px;
        }
        
        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 14px 16px;
            border: 2px solid #e5e5e5;
            border-radius: 8px;
            font-size: 15px;
            font-family: inherit;
            transition: all 0.3s ease;
        }
        
        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #6366f1;
            box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.1);
        }
        
        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }
        
        .form-note {
            font-size: 13px;
            color: #666;
            text-align: center;
            margin-top: 16px;
        }
        
        .btn-submit {
            width: 100%;
            background: #6366f1;
            color: white;
            padding: 18px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .btn-submit:hover {
            background: #4f46e5;
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(99, 102, 241, 0.4);
        }
        
        /* Footer */
        footer {
            background: #0a0a0a;
            color: white;
            padding: 80px 0 40px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 60px;
            margin-bottom: 60px;
        }
        
        .footer-brand h3 {
            font-size: 28px;
            font-weight: 700;
            color: #6366f1;
            margin-bottom: 16px;
        }
        
        .footer-brand p {
            font-size: 15px;
            color: #999;
            line-height: 1.7;
            margin-bottom: 24px;
        }
        
        .social-links {
            display: flex;
            gap: 16px;
        }
        
        .social-link {
            width: 40px;
            height: 40px;
            background: #1a1a1a;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .social-link:hover {
            background: #6366f1;
            transform: translateY(-3px);
        }
        
        .footer-links h4 {
            font-size: 16px;
            font-weight: 600;
            margin-bottom: 20px;
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 12px;
        }
        
        .footer-links a {
            color: #999;
            text-decoration: none;
            font-size: 14px;
            transition: color 0.3s ease;
        }
        
        .footer-links a:hover {
            color: #6366f1;
        }
        
        .footer-bottom {
            padding-top: 40px;
            border-top: 1px solid #1a1a1a;
            text-align: center;
            color: #666;
            font-size: 14px;
        }
        
        /* Responsive */
        @media (max-width: 968px) {
            .container {
                padding: 0 24px;
            }
            
            .nav-container {
                padding: 16px 24px;
            }
            
            .nav-links {
                display: none;
            }
            
            .hero {
                padding: 140px 0 80px;
            }
            
            .hero h1 {
                font-size: 40px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .hero-cta {
                flex-direction: column;
            }
            
            .stats {
                grid-template-columns: 1fr;
                gap: 32px;
            }
            
            .problem-grid,
            .portfolio-grid {
                grid-template-columns: 1fr;
            }
            
            .services-grid,
            .testimonials-grid {
                grid-template-columns: 1fr;
            }
            
            .section-header h2 {
                font-size: 36px;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
                gap: 40px;
            }
            
            .cta-form {
                padding: 32px 24px;
            }
        }
        
        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }
        
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="nav-container">
            <div class="logo">Nexora</div>
            <div class="nav-links">
                <a href="#services">Services</a>
                <a href="#portfolio">Portfolio</a>
                <a href="#testimonials">Testimonials</a>
                <a href="#contact" class="nav-cta">Get Started</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Build a website that <span class="highlight">converts visitors into clients</span></h1>
                <p>Professional branding and web design that increases your business revenue. Clear messaging, fast performance, and design that builds trust.</p>
                <div class="hero-cta">
                    <a href="#contact" class="btn-primary">Book Free Audit</a>
                    <a href="#portfolio" class="btn-secondary">View Our Work</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats-section">
        <div class="container">
            <div class="stats fade-in">
                <div class="stat-item">
                    <div class="stat-number">150+</div>
                    <div class="stat-label">Projects Delivered</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">94%</div>
                    <div class="stat-label">Client Satisfaction</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">2.5x</div>
                    <div class="stat-label">Avg. Conversion Increase</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Problem Section -->
    <section class="problem-section" id="about">
        <div class="container">
            <div class="section-header fade-in">
                <span class="section-tag">The Challenge</span>
                <h2>Your website should drive growth, not frustration</h2>
                <p>Most business owners struggle with websites that fail to communicate value, convert visitors, or reflect their brand quality.</p>
            </div>
            
            <div class="problem-grid">
                <div class="problem-card fade-in">
                    <div class="problem-icon">⚠️</div>
                    <h3>Low conversion rates</h3>
                    <p>Visitors leave without taking action. Your website isn't clear about what you offer or why they should choose you.</p>
                    <span class="solution-tag">We fix this</span>
                </div>
                
                <div class="problem-card fade-in">
                    <div class="problem-icon">🎯</div>
                    <h3>Unclear brand identity</h3>
                    <p>Your brand looks unprofessional or inconsistent. Clients don't trust you enough to reach out.</p>
                    <span class="solution-tag">We fix this</span>
                </div>
                
                <div class="problem-card fade-in">
                    <div class="problem-icon">⏱️</div>
                    <h3>Slow, outdated design</h3>
                    <p>Your website is slow to load and doesn't work well on mobile. You're losing potential clients every day.</p>
                    <span class="solution-tag">We fix this</span>
                </div>
                
                <div class="problem-card fade-in">
                    <div class="problem-icon">💼</div>
                    <h3>No clear direction</h3>
                    <p>You've tried DIY solutions or worked with designers who don't understand business strategy.</p>
                    <span class="solution-tag">We fix this</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services-section" id="services">
        <div class="container">
            <div class="section-header fade-in">
                <span class="section-tag">What We Do</span>
                <h2>Services that increase your business performance</h2>
                <p>We focus on what actually drives results: clear messaging, professional design, and strategic conversion optimization.</p>
            </div>
            
            <div class="services-grid">
                <div class="service-card fade-in">
                    <div class="service-icon">🎨</div>
                    <h3>Brand Identity</h3>
                    <p>Professional logo design, color systems, and brand guidelines that make your business instantly recognizable.</p>
                    <ul class="service-features">
                        <li>Custom logo design</li>
                        <li>Color palette development</li>
                        <li>Typography system</li>
                        <li>Brand style guide</li>
                    </ul>
                </div>
                
                <div class="service-card fade-in">
                    <div class="service-icon">💻</div>
                    <h3>Landing Pages</h3>
                    <p>High-converting landing pages designed to turn visitors into customers. Fast, mobile-optimized, and results-focused.</p>
                    <ul class="service-features">
                        <li>Conversion-optimized design</li>
                        <li>Mobile-first approach</li>
                        <li>Fast loading speeds</li>
                        <li>A/B testing ready</li>
                    </ul>
                </div>
                
                <div class="service-card fade-in">
                    <div class="service-icon">🚀</div>
                    <h3>Website Design</h3>
                    <p>Full website design and development that showcases your expertise and drives lead generation.</p>
                    <ul class="service-features">
                        <li>Custom web design</li>
                        <li>SEO optimization</li>
                        <li>Content strategy</li>
                        <li>Analytics setup</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section class="portfolio-section" id="portfolio">
        <div class="container">
            <div class="section-header fade-in">
                <span class="section-tag">Our Work</span>
                <h2>Real results for real businesses</h2>
                <p>See how we've helped businesses like yours increase conversions and grow revenue.</p>
            </div>
            
            <div class="portfolio-grid">
                <div class="portfolio-card fade-in">
                    <div class="portfolio-image">TechFlow</div>
                    <div class="portfolio-content">
                        <h3>TechFlow SaaS Platform</h3>
                        <p>Complete rebrand and landing page redesign for a B2B software company. New design increased trial signups and improved brand perception.</p>
                        <div class="portfolio-stats">
                            <div class="portfolio-stat">
                                <div class="portfolio-stat-value">+165%</div>
                                <div class="portfolio-stat-label">Trial Signups</div>
                            </div>
                            <div class="portfolio-stat">
                                <div class="portfolio-stat-value">+89%</div>
                                <div class="portfolio-stat-label">Time on Site</div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="portfolio-card fade-in">
                    <div class="portfolio-image" style="background: linear-gradient(135deg, #f59e0b 0%, #ec4899 100%);">Luxe Co.</div>
                    <div class="portfolio-content">
                        <h3>Luxe Co. E-Commerce</h3>
                        <p>Premium brand identity and website for a luxury home goods retailer. Design focused on trust-building and streamlined checkout experience.</p>
                        <div class="portfolio-stats">
                            <div class="portfolio-stat">
                                <div class="portfolio-stat-value">+220%</div>
                                <div class="portfolio-stat-label">Online Sales</div>
                            </div>
                            <div class="portfolio-stat">
                                <div class="portfolio-stat-value">-42%</div>
                                <div class="portfolio-stat-label">Cart Abandonment</div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="portfolio-card fade-in">
                    <div class="portfolio-image" style="background: linear-gradient(135deg, #06b6d4 0%, #6366f1 100%);">PureHealth</div>
                    <div class="portfolio-content">
                        <h3>PureHealth Wellness Clinic</h3>
                        <p>Brand refresh and appointment-focused website for a growing wellness practice. Clear service descriptions and easy booking increased consultations.</p>
                        <div class="portfolio-stats">
                            <div class="portfolio-stat">
                                <div class="portfolio-stat-value">+143%</div>
                                <div class="portfolio-stat-label">Bookings</div>
                            </div>
                            <div class="portfolio-stat">
                                <div class="portfolio-stat-value">+78%</div>
                                <div class="portfolio-stat-label">Inquiries</div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="portfolio-card fade-in">
                    <div class="portfolio-image" style="background: linear-gradient(135deg, #0a0a0a 0%, #4a4a4a 100%);">Apex Law</div>
                    <div class="portfolio-content">
                        <h3>Apex Law Group</h3>
                        <p>Professional rebrand for a corporate law firm. Website redesign focused on establishing authority and making initial contact easy for potential clients.</p>
                        <div class="portfolio-stats">
                            <div class="portfolio-stat">
                                <div class="portfolio-stat-value">+190%</div>
                                <div class="portfolio-stat-label">Consultations</div>
                            </div>
                            <div class="portfolio-stat">
                                <div class="portfolio-stat-value">+95%</div>
                                <div class="portfolio-stat-label">Client Trust Score</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="testimonials-section" id="testimonials">
        <div class="container">
            <div class="section-header fade-in">
                <span class="section-tag">Client Success</span>
                <h2>What our clients say</h2>
                <p>We measure success by the results we deliver for your business.</p>
            </div>
            
            <div class="testimonials-grid">
                <div class="testimonial-card fade-in">
                    <div class="stars">★★★★★</div>
                    <p class="testimonial-text">"Nexora transformed our online presence. Within 3 months of launch, we saw a 165% increase in qualified leads. The design is clean, professional, and actually converts."</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">MJ</div>
                        <div class="author-info">
                            <h4>Michael Jenkins</h4>
                            <p>CEO, TechFlow</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card fade-in">
                    <div class="stars">★★★★★</div>
                    <p class="testimonial-text">"Best investment we made this year. Our old website was costing us clients. Nexora delivered a site that reflects our quality and makes booking appointments effortless."</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">SR</div>
                        <div class="author-info">
                            <h4>Sarah Rodriguez</h4>
                            <p>Founder, PureHealth Clinic</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card fade-in">
                    <div class="stars">★★★★★</div>
                    <p class="testimonial-text">"Finally, a design agency that understands business strategy. They didn't just make things look good—they built us a revenue-generating machine."</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">DK</div>
                        <div class="author-info">
                            <h4>David Kim</h4>
                            <p>Marketing Director, Luxe Co.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section" id="contact">
        <div class="container">
            <div class="cta-content">
                <h2>Ready to increase your conversion rate?</h2>
                <p>Book a free 30-minute audit. We'll review your current website and show you exactly what's holding you back from more clients.</p>
                
                <form class="cta-form" id="contactForm">
                    <div class="form-group">
                        <label for="name">Full Name *</label>
                        <input type="text" id="name" name="name" required placeholder="John Smith">
                    </div>
                    
                    <div class="form-group">
                        <label for="email">Email Address *</label>
                        <input type="email" id="email" name="email" required placeholder="john@company.com">
                    </div>
                    
                    <div class="form-group">
                        <label for="business">Business Type *</label>
                        <select id="business" name="business" required>
                            <option value="">Select your industry</option>
                            <option value="saas">SaaS / Technology</option>
                            <option value="ecommerce">E-Commerce</option>
                            <option value="professional">Professional Services</option>
                            <option value="healthcare">Healthcare / Wellness</option>
                            <option value="other">Other</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="message">What's your main challenge? *</label>
                        <textarea id="message" name="message" required placeholder="Tell us about your current website or branding challenge..."></textarea>
                    </div>
                    
                    <button type="submit" class="btn-submit">Book Free Audit</button>
                    
                    <p class="form-note">🔒 No spam. No sales calls. Just actionable insights for your business.</p>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-brand">
                    <h3>Nexora</h3>
                    <p>Digital branding and web design that drives business growth. Clear strategy, professional execution, measurable results.</p>
                    <div class="social-links">
                        <a href="#" class="social-link">𝕏</a>
                        <a href="#" class="social-link">in</a>
                        <a href="#" class="social-link">ig</a>
                        <a href="#" class="social-link">f</a>
                    </div>
                </div>
                
                <div class="footer-links">
                    <h4>Services</h4>
                    <ul>
                        <li><a href="#services">Brand Identity</a></li>
                        <li><a href="#services">Landing Pages</a></li>
                        <li><a href="#services">Website Design</a></li>
                        <li><a href="#contact">Free Audit</a></li>
                    </ul>
                </div>
                
                <div class="footer-links">
                    <h4>Company</h4>
                    <ul>
                        <li><a href="#about">About Us</a></li>
                        <li><a href="#portfolio">Portfolio</a></li>
                        <li><a href="#testimonials">Testimonials</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                
                <div class="footer-links">
                    <h4>Legal</h4>
                    <ul>
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Terms of Service</a></li>
                        <li><a href="#">Cookie Policy</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2025 Nexora. All rights reserved. Building brands that convert.</p>
            </div>
        </div>
    </footer>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Scroll animation
        const fadeElements = document.querySelectorAll('.fade-in');
        
        const appearOptions = {
            threshold: 0.15,
            rootMargin: "0px 0px -100px 0px"
        };

        const appearOnScroll = new IntersectionObserver(function(entries, appearOnScroll) {
            entries.forEach(entry => {
                if (!entry.isIntersecting) {
                    return;
                } else {
                    entry.target.classList.add('visible');
                    appearOnScroll.unobserve(entry.target);
                }
            });
        }, appearOptions);

        fadeElements.forEach(element => {
            appearOnScroll.observe(element);
        });

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Form submission
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form data
            const formData = new FormData(this);
            const data = Object.fromEntries(formData);
            
            // Simulate form submission
            alert('Thank you! We\'ll contact you within 24 hours to schedule your free audit.');
            this.reset();
            
            // In production, you would send this to your backend:
            // fetch('/api/contact', {
            //     method: 'POST',
            //     headers: { 'Content-Type': 'application/json' },
            //     body: JSON.stringify(data)
            // });
        });
    </script>
</body>
</html>
