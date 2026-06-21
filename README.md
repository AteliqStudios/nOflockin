<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>n0flockin — Official Store</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Playfair+Display:wght@700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --black: #0a0a0a;
            --dark: #111111;
            --grey: #1a1a1a;
            --light-grey: #2a2a2a;
            --text: #e0e0e0;
            --muted: #888888;
            --accent-red: #e63946;
            --accent-yellow: #ffd60a;
            --accent-green: #2ecc71;
            --white: #ffffff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--black);
            color: var(--text);
            overflow-x: hidden;
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--black);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--light-grey);
            border-radius: 4px;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(10, 10, 10, 0.9);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--grey);
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 28px;
            font-weight: 900;
            color: var(--white);
            letter-spacing: -1px;
            text-decoration: none;
        }

        .logo span {
            color: var(--muted);
        }

        .nav-links {
            display: flex;
            gap: 40px;
            list-style: none;
        }

        .nav-links a {
            color: var(--muted);
            text-decoration: none;
            font-size: 14px;
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--white);
        }

        .nav-cta {
            background: var(--white);
            color: var(--black);
            padding: 12px 28px;
            border-radius: 30px;
            text-decoration: none;
            font-size: 13px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s;
        }

        .nav-cta:hover {
            background: var(--accent-yellow);
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
            padding-top: 80px;
        }

        .hero-bg {
            position: absolute;
            inset: 0;
            background: 
                radial-gradient(ellipse at 20% 50%, rgba(230, 57, 70, 0.08) 0%, transparent 50%),
                radial-gradient(ellipse at 80% 50%, rgba(255, 214, 10, 0.05) 0%, transparent 50%),
                radial-gradient(ellipse at 50% 100%, rgba(46, 204, 113, 0.05) 0%, transparent 50%);
        }

        .hero-content {
            text-align: center;
            z-index: 2;
            max-width: 900px;
            padding: 0 20px;
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: var(--grey);
            padding: 8px 20px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 30px;
            border: 1px solid var(--light-grey);
        }

        .sa-flag {
            width: 20px;
            height: 14px;
            background: linear-gradient(to bottom, #007749 33%, #ffffff 33%, #ffffff 66%, #001489 66%);
            position: relative;
            border-radius: 2px;
        }
        .sa-flag::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 40%;
            height: 100%;
            background: #001489;
            clip-path: polygon(0 0, 100% 50%, 0 100%);
        }
        .sa-flag::after {
            content: '';
            position: absolute;
            left: 8%;
            top: 25%;
            width: 12%;
            height: 50%;
            background: #ffd60a;
            clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: clamp(48px, 10vw, 120px);
            font-weight: 900;
            line-height: 0.9;
            margin-bottom: 20px;
            color: var(--white);
        }

        .hero h1 .accent {
            background: linear-gradient(135deg, var(--accent-red), var(--accent-yellow), var(--accent-green));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 18px;
            color: var(--muted);
            max-width: 500px;
            margin: 0 auto 40px;
            line-height: 1.6;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-primary {
            background: var(--white);
            color: var(--black);
            padding: 16px 40px;
            border-radius: 30px;
            text-decoration: none;
            font-size: 14px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }

        .btn-primary:hover {
            background: var(--accent-yellow);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(255, 214, 10, 0.3);
        }

        .btn-secondary {
            background: transparent;
            color: var(--white);
            padding: 16px 40px;
            border-radius: 30px;
            text-decoration: none;
            font-size: 14px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            border: 1px solid var(--light-grey);
            transition: all 0.3s;
            cursor: pointer;
        }

        .btn-secondary:hover {
            border-color: var(--white);
            background: rgba(255,255,255,0.05);
        }

        /* Product Section */
        .products {
            padding: 120px 5%;
            background: var(--dark);
        }

        .section-header {
            text-align: center;
            margin-bottom: 80px;
        }

        .section-header h2 {
            font-family: 'Playfair Display', serif;
            font-size: clamp(32px, 5vw, 56px);
            font-weight: 900;
            margin-bottom: 16px;
        }

        .section-header p {
            color: var(--muted);
            font-size: 16px;
            max-width: 500px;
            margin: 0 auto;
        }

        .colourway-tabs {
            display: flex;
            justify-content: center;
            gap: 16px;
            margin-bottom: 60px;
        }

        .tab-btn {
            padding: 12px 32px;
            background: var(--grey);
            border: 1px solid var(--light-grey);
            color: var(--muted);
            border-radius: 30px;
            cursor: pointer;
            font-size: 13px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s;
        }

        .tab-btn.active {
            background: var(--white);
            color: var(--black);
            border-color: var(--white);
        }

        .tab-btn:hover:not(.active) {
            border-color: var(--muted);
            color: var(--text);
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .product-card {
            background: var(--grey);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid var(--light-grey);
            transition: all 0.4s;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-8px);
            border-color: var(--light-grey);
            box-shadow: 0 20px 60px rgba(0,0,0,0.5);
        }

        .product-image {
            aspect-ratio: 1;
            background: var(--light-grey);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .product-image .placeholder-text {
            font-size: 14px;
            color: var(--muted);
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .product-image .stripe-accent {
            position: absolute;
            width: 100%;
            height: 4px;
            bottom: 0;
            background: linear-gradient(90deg, var(--accent-red), var(--accent-yellow), var(--accent-green));
        }

        .product-info {
            padding: 30px;
        }

        .product-tag {
            display: inline-block;
            padding: 4px 12px;
            background: rgba(255,255,255,0.05);
            border-radius: 4px;
            font-size: 11px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--muted);
            margin-bottom: 12px;
        }

        .product-info h3 {
            font-size: 22px;
            font-weight: 700;
            margin-bottom: 8px;
            color: var(--white);
        }

        .product-info .price {
            font-size: 24px;
            font-weight: 800;
            color: var(--white);
            margin-bottom: 16px;
        }

        .product-info .desc {
            font-size: 14px;
            color: var(--muted);
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .product-meta {
            display: flex;
            gap: 16px;
            font-size: 12px;
            color: var(--muted);
            margin-bottom: 20px;
        }

        .product-meta span {
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .add-to-cart {
            width: 100%;
            padding: 14px;
            background: var(--white);
            color: var(--black);
            border: none;
            border-radius: 10px;
            font-size: 13px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .add-to-cart:hover {
            background: var(--accent-yellow);
        }

        /* Size Guide */
        .size-guide {
            padding: 120px 5%;
            background: var(--black);
        }

        .size-tables {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .size-table-wrap {
            background: var(--grey);
            border-radius: 16px;
            padding: 40px;
            border: 1px solid var(--light-grey);
        }

        .size-table-wrap h3 {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 24px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 14px 16px;
            text-align: center;
            font-size: 14px;
        }

        th {
            background: var(--light-grey);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 12px;
            color: var(--muted);
        }

        td {
            border-bottom: 1px solid var(--light-grey);
            color: var(--text);
        }

        tr:hover td {
            background: rgba(255,255,255,0.02);
        }

        /* Email Marketing Section */
        .email-section {
            padding: 120px 5%;
            background: linear-gradient(180deg, var(--dark) 0%, var(--black) 100%);
            position: relative;
            overflow: hidden;
        }

        .email-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,214,10,0.03) 0%, transparent 70%);
            animation: pulse 8s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.1); opacity: 1; }
        }

        .email-container {
            max-width: 600px;
            margin: 0 auto;
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .email-container h2 {
            font-family: 'Playfair Display', serif;
            font-size: clamp(28px, 4vw, 48px);
            font-weight: 900;
            margin-bottom: 16px;
        }

        .email-container > p {
            color: var(--muted);
            margin-bottom: 40px;
            font-size: 16px;
            line-height: 1.6;
        }

        .email-form {
            display: flex;
            gap: 12px;
            margin-bottom: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .email-form input {
            flex: 1;
            min-width: 250px;
            padding: 16px 24px;
            background: var(--grey);
            border: 1px solid var(--light-grey);
            border-radius: 12px;
            color: var(--white);
            font-size: 15px;
            outline: none;
            transition: border-color 0.3s;
        }

        .email-form input:focus {
            border-color: var(--accent-yellow);
        }

        .email-form input::placeholder {
            color: var(--muted);
        }

        .email-form button {
            padding: 16px 32px;
            background: var(--white);
            color: var(--black);
            border: none;
            border-radius: 12px;
            font-size: 14px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .email-form button:hover {
            background: var(--accent-yellow);
        }

        .email-benefits {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 30px;
            flex-wrap: wrap;
        }

        .benefit {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 13px;
            color: var(--muted);
        }

        .benefit svg {
            width: 18px;
            height: 18px;
            color: var(--accent-green);
        }

        .success-message {
            display: none;
            padding: 20px;
            background: rgba(46, 204, 113, 0.1);
            border: 1px solid var(--accent-green);
            border-radius: 12px;
            color: var(--accent-green);
            font-weight: 600;
            margin-top: 20px;
        }

        /* Chat Widget */
        .chat-widget {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 9999;
        }

        .chat-toggle {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--white);
            border: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 20px rgba(0,0,0,0.4);
            transition: all 0.3s;
            position: relative;
        }

        .chat-toggle:hover {
            transform: scale(1.1);
            background: var(--accent-yellow);
        }

        .chat-toggle svg {
            width: 28px;
            height: 28px;
            color: var(--black);
        }

        .chat-badge {
            position: absolute;
            top: -2px;
            right: -2px;
            width: 18px;
            height: 18px;
            background: var(--accent-red);
            border-radius: 50%;
            border: 2px solid var(--black);
        }

        .chat-window {
            position: absolute;
            bottom: 80px;
            right: 0;
            width: 380px;
            max-height: 600px;
            background: var(--grey);
            border-radius: 20px;
            border: 1px solid var(--light-grey);
            overflow: hidden;
            display: none;
            flex-direction: column;
            box-shadow: 0 20px 60px rgba(0,0,0,0.5);
        }

        .chat-window.open {
            display: flex;
        }

        .chat-header {
            padding: 20px;
            background: var(--dark);
            border-bottom: 1px solid var(--light-grey);
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .chat-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent-red), var(--accent-yellow));
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            font-size: 16px;
            color: var(--black);
        }

        .chat-header-info h4 {
            font-size: 15px;
            font-weight: 700;
        }

        .chat-header-info p {
            font-size: 12px;
            color: var(--accent-green);
        }

        .chat-messages {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            max-height: 400px;
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .message {
            max-width: 80%;
            padding: 12px 16px;
            border-radius: 16px;
            font-size: 14px;
            line-height: 1.5;
            animation: messageSlide 0.3s ease;
        }

        @keyframes messageSlide {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .message.bot {
            background: var(--light-grey);
            color: var(--text);
            align-self: flex-start;
            border-bottom-left-radius: 4px;
        }

        .message.user {
            background: var(--white);
            color: var(--black);
            align-self: flex-end;
            border-bottom-right-radius: 4px;
        }

        .quick-replies {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            padding: 0 20px 12px;
        }

        .quick-reply {
            padding: 8px 16px;
            background: transparent;
            border: 1px solid var(--light-grey);
            border-radius: 20px;
            color: var(--muted);
            font-size: 12px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .quick-reply:hover {
            border-color: var(--white);
            color: var(--white);
        }

        .chat-input {
            padding: 16px 20px;
            border-top: 1px solid var(--light-grey);
            display: flex;
            gap: 10px;
        }

        .chat-input input {
            flex: 1;
            padding: 12px 16px;
            background: var(--dark);
            border: 1px solid var(--light-grey);
            border-radius: 24px;
            color: var(--white);
            font-size: 14px;
            outline: none;
        }

        .chat-input input::placeholder {
            color: var(--muted);
        }

        .chat-input button {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            background: var(--white);
            border: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .chat-input button:hover {
            background: var(--accent-yellow);
        }

        .chat-input button svg {
            width: 20px;
            height: 20px;
            color: var(--black);
        }

        /* Packaging Gallery */
        .packaging {
            padding: 120px 5%;
            background: var(--dark);
        }

        .packaging-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .pack-item {
            background: var(--grey);
            border-radius: 16px;
            padding: 30px;
            border: 1px solid var(--light-grey);
            text-align: center;
            transition: all 0.3s;
        }

        .pack-item:hover {
            transform: translateY(-5px);
            border-color: var(--light-grey);
        }

        .pack-icon {
            width: 80px;
            height: 80px;
            margin: 0 auto 20px;
            background: var(--light-grey);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
        }

        .pack-item h4 {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 8px;
        }

        .pack-item p {
            font-size: 14px;
            color: var(--muted);
            line-height: 1.6;
        }

        /* Footer */
        footer {
            padding: 60px 5% 30px;
            background: var(--black);
            border-top: 1px solid var(--grey);
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto 60px;
        }

        .footer-col h4 {
            font-size: 14px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 20px;
            color: var(--white);
        }

        .footer-col a {
            display: block;
            color: var(--muted);
            text-decoration: none;
            font-size: 14px;
            margin-bottom: 12px;
            transition: color 0.3s;
        }

        .footer-col a:hover {
            color: var(--white);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid var(--grey);
            color: var(--muted);
            font-size: 13px;
        }

        .social-links {
            display: flex;
            gap: 16px;
            margin-top: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--grey);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background: var(--white);
            color: var(--black);
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            .mobile-menu-btn {
                display: block;
            }
            .chat-window {
                width: calc(100vw - 40px);
                right: -10px;
            }
            .size-tables {
                grid-template-columns: 1fr;
            }
            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }
            .btn-primary, .btn-secondary {
                width: 100%;
                max-width: 300px;
                text-align: center;
            }
        }

        /* Animations */
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
<base target="_blank">
</head>
<body>

    <!-- Navigation -->
    <nav>
        <a href="#" class="logo">n0<span>flockin</span></a>
        <ul class="nav-links">
            <li><a href="#products">Collection</a></li>
            <li><a href="#sizes">Size Guide</a></li>
            <li><a href="#packaging">Packaging</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
        <a href="#products" class="nav-cta">Shop Now</a>
        <button class="mobile-menu-btn" onclick="alert('Mobile menu coming soon!')">
            <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M4 6h16M4 12h16M4 18h16"/>
            </svg>
        </button>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-bg"></div>
        <div class="hero-content">
            <div class="hero-badge">
                <div class="sa-flag"></div>
                Designed in South Africa
            </div>
            <h1>NO <span class="accent">FLOCKIN</span></h1>
            <p>SA Taxi Stripe tracksuits. Bold stripes. Zero compromises. Built for the culture.</p>
            <div class="hero-buttons">
                <a href="#products" class="btn-primary">Shop Collection</a>
                <a href="#sizes" class="btn-secondary">Size Guide</a>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products" id="products">
        <div class="section-header fade-in">
            <h2>The Collection</h2>
            <p>Premium 55% cotton / 45% polyester tracksuits with iconic SA taxi stripe detailing</p>
        </div>

        <div class="colourway-tabs fade-in">
            <button class="tab-btn active" onclick="switchColourway('black')">Colourway 01 — Black</button>
            <button class="tab-btn" onclick="switchColourway('grey')">Colourway 02 — Grey</button>
        </div>

        <div class="product-grid" id="product-grid">
            <!-- Black Colourway -->
            <div class="product-card fade-in" data-colourway="black">
                <div class="product-image">
                    <span class="placeholder-text">[Tracksuit Top — Black]</span>
                    <div class="stripe-accent"></div>
                </div>
                <div class="product-info">
                    <span class="product-tag">Hoodie Top</span>
                    <h3>n0flockin Tracksuit Top</h3>
                    <div class="price">R1,299</div>
                    <p class="desc">Full-zip hoodie with SA taxi stripe sleeves. Black body with red/yellow/green stripe detailing. Tone-on-tone black logo.</p>
                    <div class="product-meta">
                        <span>📏 XS–XL</span>
                        <span>🎨 Black 6C</span>
                        <span>🇿🇦 SA Made</span>
                    </div>
                    <button class="add-to-cart" onclick="addToCart('Tracksuit Top - Black')">Add to Cart</button>
                </div>
            </div>

            <div class="product-card fade-in" data-colourway="black">
                <div class="product-image">
                    <span class="placeholder-text">[Tracksuit Bottom — Black]</span>
                    <div class="stripe-accent"></div>
                </div>
                <div class="product-info">
                    <span class="product-tag">Sweatpants</span>
                    <h3>n0flockin Tracksuit Bottom</h3>
                    <div class="price">R999</div>
                    <p class="desc">Relaxed fit sweatpants with matching SA taxi stripe legs. Elastic waistband, side pockets, ribbed cuffs.</p>
                    <div class="product-meta">
                        <span>📏 XS–XL</span>
                        <span>🎨 Black 6C</span>
                        <span>🇿🇦 SA Made</span>
                    </div>
                    <button class="add-to-cart" onclick="addToCart('Tracksuit Bottom - Black')">Add to Cart</button>
                </div>
            </div>

            <div class="product-card fade-in" data-colourway="black">
                <div class="product-image">
                    <span class="placeholder-text">[Full Set — Black]</span>
                    <div class="stripe-accent"></div>
                </div>
                <div class="product-info">
                    <span class="product-tag">Bundle</span>
                    <h3>Full Tracksuit Set</h3>
                    <div class="price">R2,099</div>
                    <p class="desc">Complete top and bottom set. Save R200 when you buy together. Includes free laptop sticker and hangtag.</p>
                    <div class="product-meta">
                        <span>🎁 Free Sticker</span>
                        <span>🏷️ Free Hangtag</span>
                        <span>💰 Save R200</span>
                    </div>
                    <button class="add-to-cart" onclick="addToCart('Full Set - Black')">Add to Cart</button>
                </div>
            </div>

            <!-- Grey Colourway (hidden by default) -->
            <div class="product-card fade-in" data-colourway="grey" style="display:none;">
                <div class="product-image">
                    <span class="placeholder-text">[Tracksuit Top — Grey]</span>
                    <div class="stripe-accent"></div>
                </div>
                <div class="product-info">
                    <span class="product-tag">Hoodie Top</span>
                    <h3>n0flockin Tracksuit Top</h3>
                    <div class="price">R1,299</div>
                    <p class="desc">Full-zip hoodie with SA taxi stripe sleeves. Cool Grey 3C heather body with white tone-on-tone textured logo.</p>
                    <div class="product-meta">
                        <span>📏 XS–XL</span>
                        <span>🎨 Cool Grey 3C</span>
                        <span>🇿🇦 SA Made</span>
                    </div>
                    <button class="add-to-cart" onclick="addToCart('Tracksuit Top - Grey')">Add to Cart</button>
                </div>
            </div>

            <div class="product-card fade-in" data-colourway="grey" style="display:none;">
                <div class="product-image">
                    <span class="placeholder-text">[Tracksuit Bottom — Grey]</span>
                    <div class="stripe-accent"></div>
                </div>
                <div class="product-info">
                    <span class="product-tag">Sweatpants</span>
                    <h3>n0flockin Tracksuit Bottom</h3>
                    <div class="price">R999</div>
                    <p class="desc">Relaxed fit sweatpants with matching SA taxi stripe legs. Matching grey waistband and cuffs — no contrast.</p>
                    <div class="product-meta">
                        <span>📏 XS–XL</span>
                        <span>🎨 Cool Grey 3C</span>
                        <span>🇿🇦 SA Made</span>
                    </div>
                    <button class="add-to-cart" onclick="addToCart('Tracksuit Bottom - Grey')">Add to Cart</button>
                </div>
            </div>

            <div class="product-card fade-in" data-colourway="grey" style="display:none;">
                <div class="product-image">
                    <span class="placeholder-text">[Full Set — Grey]</span>
                    <div class="stripe-accent"></div>
                </div>
                <div class="product-info">
                    <span class="product-tag">Bundle</span>
                    <h3>Full Tracksuit Set</h3>
                    <div class="price">R2,099</div>
                    <p class="desc">Complete top and bottom set in heather grey. Save R200 when you buy together. Includes free laptop sticker and hangtag.</p>
                    <div class="product-meta">
                        <span>🎁 Free Sticker</span>
                        <span>🏷️ Free Hangtag</span>
                        <span>💰 Save R200</span>
                    </div>
                    <button class="add-to-cart" onclick="addToCart('Full Set - Grey')">Add to Cart</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Size Guide -->
    <section class="size-guide" id="sizes">
        <div class="section-header fade-in">
            <h2>Size Guide</h2>
            <p>All measurements in centimeters. Relaxed fit — size down for slimmer fit.</p>
        </div>

        <div class="size-tables">
            <div class="size-table-wrap fade-in">
                <h3>📐 Tracksuit Top (CM)</h3>
                <table>
                    <thead>
                        <tr>
                            <th>Measurement</th>
                            <th>XS</th>
                            <th>S</th>
                            <th>M</th>
                            <th>L</th>
                            <th>XL</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Chest Width (flat)</td>
                            <td>51</td><td>53</td><td>55</td><td>57</td><td>59</td>
                        </tr>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Body Length</td>
                            <td>64</td><td>66</td><td>68</td><td>70</td><td>72</td>
                        </tr>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Shoulder Width</td>
                            <td>43</td><td>45</td><td>47</td><td>49</td><td>51</td>
                        </tr>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Sleeve Length</td>
                            <td>61</td><td>62</td><td>63</td><td>64</td><td>65</td>
                        </tr>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Bottom Rib</td>
                            <td>41</td><td>43</td><td>45</td><td>47</td><td>49</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <div class="size-table-wrap fade-in">
                <h3>📐 Tracksuit Bottom (CM)</h3>
                <table>
                    <thead>
                        <tr>
                            <th>Measurement</th>
                            <th>XS</th>
                            <th>S</th>
                            <th>M</th>
                            <th>L</th>
                            <th>XL</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Waist (relaxed)</td>
                            <td>33</td><td>35</td><td>37</td><td>39</td><td>41</td>
                        </tr>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Waist (stretched)</td>
                            <td>45</td><td>47</td><td>49</td><td>51</td><td>53</td>
                        </tr>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Hip Width</td>
                            <td>49</td><td>51</td><td>53</td><td>55</td><td>57</td>
                        </tr>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Thigh Width</td>
                            <td>28</td><td>29</td><td>30</td><td>31</td><td>32</td>
                        </tr>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Leg Opening</td>
                            <td>11</td><td>11.5</td><td>12.5</td><td>13.5</td><td>14.5</td>
                        </tr>
                        <tr>
                            <td style="text-align:left; font-weight:600;">Inseam</td>
                            <td>69</td><td>71</td><td>73</td><td>75</td><td>77</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </section>

    <!-- Packaging -->
    <section class="packaging" id="packaging">
        <div class="section-header fade-in">
            <h2>The Experience</h2>
            <p>Every detail matters — from the polybag to the sticker</p>
        </div>

        <div class="packaging-grid">
            <div class="pack-item fade-in">
                <div class="pack-icon">📦</div>
                <h4>Frosted Polybag</h4>
                <p>30×40cm frosted PE bag with zip-lock closure. Semi-transparent grey with gloss logo and SA flag detail.</p>
            </div>
            <div class="pack-item fade-in">
                <div class="pack-icon">🏷️</div>
                <h4>Premium Hangtag</h4>
                <p>350 GSM cardstock, 10×5cm, matte finish. Front: logo. Back: brand info. Attached with black string.</p>
            </div>
            <div class="pack-item fade-in">
                <div class="pack-icon">💻</div>
                <h4>Laptop Sticker</h4>
                <p>8-10cm vinyl sticker, matte finish, die-cut to logo shape. Available in black or white.</p>
            </div>
            <div class="pack-item fade-in">
                <div class="pack-icon">👕</div>
                <h4>Woven Neck Label</h4>
                <p>6×8cm label with gothic "nf" logo. Fabric: 55% cotton / 45% polyester. Care instructions included.</p>
            </div>
        </div>
    </section>

    <!-- Email Marketing -->
    <section class="email-section" id="contact">
        <div class="email-container">
            <h2 class="fade-in">Join the <span style="color: var(--accent-yellow);">Flock</span></h2>
            <p class="fade-in">Get early access to drops, exclusive discounts, and behind-the-scenes content. No spam — just heat.</p>

            <form class="email-form fade-in" onsubmit="handleSubscribe(event)">
                <input type="email" id="email-input" placeholder="Enter your email address" required>
                <button type="submit">Subscribe</button>
            </form>

            <div class="success-message" id="success-msg">
                ✅ You're in! Check your inbox for a welcome gift.
            </div>

            <div class="email-benefits fade-in">
                <div class="benefit">
                    <svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg>
                    Early Access to Drops
                </div>
                <div class="benefit">
                    <svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg>
                    10% Off First Order
                </div>
                <div class="benefit">
                    <svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg>
                    Free Shipping Updates
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-grid">
            <div class="footer-col">
                <h4>Brand</h4>
                <a href="#">About n0flockin</a>
                <a href="#">Lookbook</a>
                <a href="#">Stockists</a>
                <a href="#">Press</a>
            </div>
            <div class="footer-col">
                <h4>Support</h4>
                <a href="#">Shipping Info</a>
                <a href="#">Returns</a>
                <a href="#">Size Guide</a>
                <a href="#">FAQ</a>
            </div>
            <div class="footer-col">
                <h4>Legal</h4>
                <a href="#">Privacy Policy</a>
                <a href="#">Terms of Service</a>
                <a href="#">Cookie Policy</a>
            </div>
            <div class="footer-col">
                <h4>Connect</h4>
                <p style="color: var(--muted); font-size: 14px; margin-bottom: 12px;">Designed in South Africa<br>Made with pride 🇿🇦</p>
                <div class="social-links">
                    <a href="https://instagram.com/0flockin" target="_blank" title="Instagram">
                        <svg width="18" height="18" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
                    </a>
                    <a href="#" title="Twitter/X">
                        <svg width="18" height="18" fill="currentColor" viewBox="0 0 24 24"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
                    </a>
                    <a href="#" title="TikTok">
                        <svg width="18" height="18" fill="currentColor" viewBox="0 0 24 24"><path d="M12.525.02c1.31-.02 2.61-.01 3.91-.02.08 1.53.63 3.09 1.75 4.17 1.12 1.11 2.7 1.62 4.24 1.79v4.03c-1.44-.05-2.89-.35-4.2-.97-.57-.26-1.1-.59-1.62-.93-.01 2.92.01 5.84-.02 8.75-.08 1.4-.54 2.79-1.35 3.94-1.31 1.92-3.58 3.17-5.91 3.21-1.43.08-2.86-.31-4.08-1.03-2.02-1.19-3.44-3.37-3.65-5.71-.02-.5-.03-1-.01-1.49.18-1.9 1.12-3.72 2.58-4.96 1.66-1.44 3.98-2.13 6.15-1.72.02 1.48-.04 2.96-.04 4.44-.99-.32-2.15-.23-3.02.37-.63.41-1.11 1.04-1.36 1.75-.21.51-.15 1.07-.14 1.61.24 1.64 1.82 3.02 3.5 2.87 1.12-.01 2.19-.66 2.77-1.61.19-.33.4-.67.41-1.06.1-1.79.06-3.57.07-5.36.01-4.03-.01-8.05.02-12.07z"/></svg>
                    </a>
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <p>© 2026 n0flockin. All rights reserved. Designed in South Africa.</p>
        </div>
    </footer>

    <!-- Chat Widget -->
    <div class="chat-widget">
        <div class="chat-window" id="chat-window">
            <div class="chat-header">
                <div class="chat-avatar">nf</div>
                <div class="chat-header-info">
                    <h4>n0flockin Support</h4>
                    <p>● Online now</p>
                </div>
            </div>
            <div class="chat-messages" id="chat-messages">
                <div class="message bot">Hey! Welcome to n0flockin 👋 I'm your automated assistant. How can I help you today?</div>
            </div>
            <div class="quick-replies" id="quick-replies">
                <button class="quick-reply" onclick="sendQuickReply('What sizes do you have?')">Sizes?</button>
                <button class="quick-reply" onclick="sendQuickReply('How much is shipping?')">Shipping?</button>
                <button class="quick-reply" onclick="sendQuickReply('When is the next drop?')">Next drop?</button>
                <button class="quick-reply" onclick="sendQuickReply('Can I track my order?')">Track order?</button>
            </div>
            <div class="chat-input">
                <input type="text" id="chat-input-field" placeholder="Type a message..." onkeypress="if(event.key==='Enter') sendMessage()">
                <button onclick="sendMessage()">
                    <svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8"/></svg>
                </button>
            </div>
        </div>
        <button class="chat-toggle" onclick="toggleChat()">
            <svg fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"/></svg>
            <div class="chat-badge"></div>
        </button>
    </div>

    <script>
        // Colourway Switcher
        function switchColourway(colour) {
            const tabs = document.querySelectorAll('.tab-btn');
            tabs.forEach(t => t.classList.remove('active'));
            event.target.classList.add('active');

            const cards = document.querySelectorAll('.product-card');
            cards.forEach(card => {
                if (card.dataset.colourway === colour) {
                    card.style.display = 'block';
                    setTimeout(() => card.style.opacity = '1', 10);
                } else {
                    card.style.display = 'none';
                }
            });
        }

        // Add to Cart
        function addToCart(product) {
            alert(`✅ "${product}" added to cart!

This is a demo. In production, this would connect to your payment gateway (PayFast/Yoco/PayPal).`);
        }

        // Email Subscribe
        function handleSubscribe(e) {
            e.preventDefault();
            const email = document.getElementById('email-input').value;
            const successMsg = document.getElementById('success-msg');

            // Simulate API call
            successMsg.style.display = 'block';
            document.getElementById('email-input').value = '';

            // Simulate welcome email sequence
            setTimeout(() => {
                console.log(`📧 Welcome email sent to: ${email}`);
                console.log(`📧 Follow-up drip campaign scheduled: Day 3 (lookbook), Day 7 (discount reminder)`);
            }, 1000);
        }

        // Chat Widget
        let chatOpen = false;
        function toggleChat() {
            chatOpen = !chatOpen;
            document.getElementById('chat-window').classList.toggle('open', chatOpen);
        }

        const botResponses = {
            'size': 'We stock XS through XL. Check our detailed size guide above — tracksuit top chest measurements range from 51cm (XS) to 59cm (XL). The fit is relaxed, so size down if you prefer slimmer.',
            'shipping': '🇿🇦 South Africa: R99 flat rate, 3-5 business days.
🌍 International: Calculated at checkout via DHL.
📦 Free shipping on orders over R2,500!',
            'drop': 'Next drop is scheduled for July 2026! Subscribers get 24-hour early access. Want me to add you to the notify list?',
            'track': 'You can track your order using the link in your confirmation email, or reply with your order number and I'll look it up.',
            'price': 'Tracksuit Top: R1,299 | Bottom: R999 | Full Set: R2,099 (save R200). All prices in ZAR.',
            'material': '55% cotton / 45% polyester blend. Machine wash cold, wash inside out, do not tumble dry, iron on low heat.',
            'colour': 'Two colourways available:
⚫ Black 6C with red/yellow/green stripes
⚪ Cool Grey 3C (heather) with matching grey waistband',
            'return': 'We accept returns within 14 days of delivery. Items must be unworn with original tags. Exchanges available for size issues.',
            'contact': 'Email: hello@n0flockin.co.za
Instagram: @0flockin
WhatsApp: +27 XX XXX XXXX',
            'default': 'I can help with sizing, shipping, pricing, materials, or tracking. What would you like to know about n0flockin?'
        };

        function sendMessage() {
            const input = document.getElementById('chat-input-field');
            const text = input.value.trim();
            if (!text) return;

            addMessage(text, 'user');
            input.value = '';

            // Simulate typing delay
            setTimeout(() => {
                const response = getBotResponse(text);
                addMessage(response, 'bot');
            }, 800);
        }

        function sendQuickReply(text) {
            addMessage(text, 'user');
            setTimeout(() => {
                const response = getBotResponse(text);
                addMessage(response, 'bot');
            }, 600);
        }

        function addMessage(text, sender) {
            const container = document.getElementById('chat-messages');
            const msg = document.createElement('div');
            msg.className = `message ${sender}`;
            msg.textContent = text;
            container.appendChild(msg);
            container.scrollTop = container.scrollHeight;
        }

        function getBotResponse(input) {
            const lower = input.toLowerCase();
            if (lower.includes('size') || lower.includes('fit') || lower.includes('measurement')) return botResponses.size;
            if (lower.includes('ship') || lower.includes('delivery') || lower.includes('cost')) return botResponses.shipping;
            if (lower.includes('drop') || lower.includes('release') || lower.includes('new')) return botResponses.drop;
            if (lower.includes('track') || lower.includes('order') || lower.includes('where')) return botResponses.track;
            if (lower.includes('price') || lower.includes('cost') || lower.includes('how much') || lower.includes('r')) return botResponses.price;
            if (lower.includes('material') || lower.includes('fabric') || lower.includes('cotton') || lower.includes('wash')) return botResponses.material;
            if (lower.includes('colour') || lower.includes('color') || lower.includes('black') || lower.includes('grey')) return botResponses.colour;
            if (lower.includes('return') || lower.includes('exchange') || lower.includes('refund')) return botResponses.return;
            if (lower.includes('contact') || lower.includes('email') || lower.includes('instagram') || lower.includes('whatsapp')) return botResponses.contact;
            if (lower.includes('hello') || lower.includes('hi') || lower.includes('hey')) return 'Hey there! 👋 Ready to cop some heat? Ask me about sizes, shipping, or our next drop!';
            if (lower.includes('thank')) return 'You're welcome! Stay flockin' 🔥 Anything else?';
            return botResponses.default;
        }

        // Scroll Animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) target.scrollIntoView({ behavior: 'smooth', block: 'start' });
            });
        });
    </script>
</body>
</html>
