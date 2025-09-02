<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Love Stories Events | Luxury Wedding Planning</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;500;700&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --gold: #C6A96C;
            --dark-gold: #A88B5C;
            --dark: #1A1A1A;
            --darker: #121212;
            --light: #FFFFFF;
            --cream: #F5F3F0;
            --taupe: #D8D1C7;
            --charcoal: #2E2E2E;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
            --transition: all 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            --radius-xl: 24px;
            --radius-lg: 20px;
            --radius-md: 16px;
            --radius-sm: 12px;
            --radius-xs: 8px;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            cursor: none;
        }
        
        body {
            font-family: 'Montserrat', sans-serif;
            color: var(--taupe);
            line-height: 1.6;
            background-color: var(--darker);
            overflow-x: hidden;
        }
        
        a, button, .btn, input, textarea, select, .portfolio-item, .filter-btn {
            cursor: none;
        }
        
        /* Enhanced Custom Cursor */
        .cursor {
            position: fixed;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: var(--gold);
            mix-blend-mode: difference;
            transition: transform 0.1s ease, opacity 0.3s ease;
            transform: translate(-50%, -50%) scale(1);
            pointer-events: none;
            z-index: 9999;
            will-change: transform;
        }
        
        .cursor-follower {
            position: fixed;
            width: 40px;
            height: 40px;
            border: 2px solid var(--gold);
            border-radius: 50%;
            transition: transform 0.15s ease, opacity 0.3s ease;
            transform: translate(-50%, -50%) scale(1);
            pointer-events: none;
            z-index: 9998;
            will-change: transform;
        }
        
        .cursor.hover, .cursor-follower.hover {
            transform: translate(-50%, -50%) scale(1.5);
            background: var(--cream);
        }
        
        .cursor.zoom {
            transform: translate(-50%, -50%) scale(2);
            background: rgba(198, 169, 108, 0.7);
        }
        
        .cursor-follower.zoom {
            transform: translate(-50%, -50%) scale(1.8);
            border-width: 1px;
            background: rgba(245, 243, 240, 0.1);
        }
        
        .cursor.click {
            transform: translate(-50%, -50%) scale(0.8);
            background: var(--dark-gold);
        }
        
        .cursor.hidden {
            opacity: 0;
        }
        
        .cursor-follower.hidden {
            opacity: 0;
        }
        
        h1, h2, h3, h4, h5 {
            font-family: 'Cormorant Garamond', serif;
            font-weight: 500;
            color: var(--cream);
            letter-spacing: 0.5px;
        }
        
        .container {
            width: 90%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .btn {
            display: inline-block;
            padding: 18px 42px;
            background: var(--gold);
            color: var(--darker);
            text-decoration: none;
            border-radius: var(--radius-md);
            border: none;
            transition: var(--transition);
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.9rem;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .btn:before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--cream);
            transition: var(--transition);
            z-index: -1;
            border-radius: var(--radius-md);
        }
        
        .btn:hover:before {
            left: 0;
        }
        
        .btn:hover {
            color: var(--darker);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid var(--gold);
            color: var(--cream);
            border-radius: var(--radius-md);
        }
        
        .btn-outline:before {
            background: var(--gold);
            border-radius: var(--radius-md);
        }
        
        .btn-outline:hover {
            color: var(--darker);
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 80px;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            color: var(--cream);
            position: relative;
            display: inline-block;
        }
        
        .section-title h2:after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 2px;
            background: var(--gold);
            border-radius: 2px;
        }
        
        .section-title p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto;
            color: var(--taupe);
        }
        
        /* Preloader */
        .preloader {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--darker);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.8s ease, visibility 0.8s ease;
        }
        
        .preloader.hidden {
            opacity: 0;
            visibility: hidden;
        }
        
        .preloader-text {
            font-family: 'Cormorant Garamond', serif;
            font-size: 2.5rem;
            color: var(--cream);
        }
        
        .preloader-text span {
            display: inline-block;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s ease, transform 0.5s ease;
        }
        
        /* Header Styles */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 30px 0;
            z-index: 1000;
            transition: var(--transition);
        }
        
        header.scrolled {
            padding: 15px 0;
            background: rgba(26, 26, 26, 0.95);
            box-shadow: var(--shadow);
            backdrop-filter: blur(10px);
            border-radius: 0 0 var(--radius-lg) var(--radius-lg);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-family: 'Cormorant Garamond', serif;
            font-size: 2.2rem;
            font-weight: 700;
            color: var(--cream);
            text-decoration: none;
            position: relative;
        }
        
        .logo span {
            color: var(--gold);
        }
        
        .logo:after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 1px;
            background: var(--gold);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.5s ease;
            border-radius: 2px;
        }
        
        .logo:hover:after {
            transform: scaleX(1);
            transform-origin: left;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 40px;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--cream);
            font-weight: 500;
            transition: var(--transition);
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            position: relative;
        }
        
        .nav-links a:after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 1px;
            background: var(--gold);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.5s ease;
            border-radius: 2px;
        }
        
        .nav-links a:hover:after {
            transform: scaleX(1);
            transform-origin: left;
        }
        
        .mobile-menu-btn {
            display: none;
            font-size: 1.5rem;
            color: var(--cream);
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1519225421980-715cb0215aed?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
        }
        
        .hero-content {
            max-width: 800px;
            margin-left: 10%;
            opacity: 0;
            transform: translateY(50px);
            transition: opacity 1s ease, transform 1s ease;
        }
        
        .hero-content.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        .hero h1 {
            font-size: 4.5rem;
            margin-bottom: 30px;
            line-height: 1.2;
            color: var(--cream);
        }
        
        .hero p {
            font-size: 1.3rem;
            margin-bottom: 40px;
            max-width: 600px;
            color: var(--taupe);
        }
        
        .hero-scroll {
            position: absolute;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            color: var(--taupe);
            opacity: 0;
            transition: opacity 1s ease;
        }
        
        .hero-scroll.visible {
            opacity: 1;
        }
        
        .hero-scroll span {
            margin-bottom: 10px;
            font-size: 0.9rem;
            letter-spacing: 2px;
            text-transform: uppercase;
        }
        
        .hero-scroll i {
            font-size: 1.5rem;
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0);
            }
            40% {
                transform: translateY(-10px);
            }
            60% {
                transform: translateY(-5px);
            }
        }
        
        /* About Section */
        .about {
            padding: 150px 0;
            background: var(--dark);
            position: relative;
        }
        
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
            align-items: center;
        }
        
        .about-content h2 {
            font-size: 3rem;
            margin-bottom: 30px;
            color: var(--cream);
            position: relative;
            padding-bottom: 20px;
        }
        
        .about-content h2:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 80px;
            height: 2px;
            background: var(--gold);
            border-radius: 2px;
        }
        
        .about-content p {
            margin-bottom: 25px;
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--taupe);
        }
        
        .about-image {
            position: relative;
            overflow: hidden;
            border-radius: var(--radius-xl);
        }
        
        .about-image img {
            width: 100%;
            height: auto;
            display: block;
            transition: var(--transition);
            border-radius: var(--radius-xl);
        }
        
        .about-image:hover img {
            transform: scale(1.05);
        }
        
        .about-image:before {
            content: '';
            position: absolute;
            top: -30px;
            left: -30px;
            width: 100px;
            height: 100px;
            border-top: 2px solid var(--gold);
            border-left: 2px solid var(--gold);
            opacity: 0;
            transition: var(--transition);
            border-radius: var(--radius-sm) 0 0 0;
        }
        
        .about-image:after {
            content: '';
            position: absolute;
            bottom: -30px;
            right: -30px;
            width: 100px;
            height: 100px;
            border-bottom: 2px solid var(--gold);
            border-right: 2px solid var(--gold);
            opacity: 0;
            transition: var(--transition);
            border-radius: 0 0 var(--radius-sm) 0;
        }
        
        .about-image:hover:before,
        .about-image:hover:after {
            opacity: 1;
            top: 20px;
            left: 20px;
            bottom: 20px;
            right: 20px;
        }
        
        /* Services Section */
        .services {
            padding: 150px 0;
            position: relative;
            background: var(--darker);
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
        }
        
        .service-card {
            padding: 60px 40px;
            background: var(--charcoal);
            box-shadow: var(--shadow);
            text-align: center;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            z-index: 1;
            border-radius: var(--radius-xl);
        }
        
        .service-card:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 0;
            background: var(--gold);
            transition: var(--transition);
            z-index: -1;
            border-radius: var(--radius-xl);
        }
        
        .service-card:hover:before {
            height: 100%;
        }
        
        .service-card:hover {
            transform: translateY(-10px);
        }
        
        .service-card:hover h3,
        .service-card:hover p {
            color: var(--darker);
        }
        
        .service-icon {
            font-size: 3.5rem;
            color: var(--gold);
            margin-bottom: 30px;
            transition: var(--transition);
        }
        
        .service-card:hover .service-icon {
            color: var(--darker);
        }
        
        .service-card h3 {
            margin-bottom: 20px;
            font-size: 1.8rem;
            transition: var(--transition);
        }
        
        .service-card p {
            margin-bottom: 25px;
            transition: var(--transition);
            color: var(--taupe);
        }
        
        /* Portfolio Section */
        .portfolio {
            padding: 150px 0;
            background: var(--dark);
            position: relative;
        }
        
        .portfolio-filter {
            display: flex;
            justify-content: center;
            margin-bottom: 50px;
        }
        
        .filter-btn {
            padding: 12px 28px;
            background: transparent;
            border: none;
            font-family: 'Montserrat', sans-serif;
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: var(--transition);
            position: relative;
            color: var(--taupe);
            border-radius: var(--radius-md);
            margin: 0 10px;
        }
        
        .filter-btn:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gold);
            transition: var(--transition);
            border-radius: 2px;
        }
        
        .filter-btn:hover:after,
        .filter-btn.active:after {
            width: 100%;
        }
        
        .filter-btn:hover,
        .filter-btn.active {
            color: var(--cream);
            background: rgba(198, 169, 108, 0.1);
        }
        
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }
        
        .portfolio-item {
            position: relative;
            height: 400px;
            overflow: hidden;
            border-radius: var(--radius-xl);
        }
        
        .portfolio-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
            border-radius: var(--radius-xl);
        }
        
        .portfolio-item:hover img {
            transform: scale(1.1);
        }
        
        .portfolio-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: var(--transition);
            padding: 30px;
            border-radius: var(--radius-xl);
        }
        
        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }
        
        .portfolio-overlay h3 {
            color: var(--cream);
            margin-bottom: 15px;
            font-size: 1.8rem;
            transform: translateY(-20px);
            transition: var(--transition);
            opacity: 0;
        }
        
        .portfolio-overlay p {
            color: var(--taupe);
            text-align: center;
            transform: translateY(20px);
            transition: var(--transition);
            opacity: 0;
        }
        
        .portfolio-item:hover .portfolio-overlay h3,
        .portfolio-item:hover .portfolio-overlay p {
            transform: translateY(0);
            opacity: 1;
        }
        
        /* Testimonials Section */
        .testimonials {
            padding: 150px 0;
            position: relative;
            background: var(--darker);
        }
        
        .testimonial-slider {
            max-width: 1000px;
            margin: 0 auto;
            position: relative;
            overflow: hidden;
        }
        
        .testimonial {
            padding: 60px;
            background: var(--charcoal);
            box-shadow: var(--shadow);
            text-align: center;
            display: none;
            border-radius: var(--radius-xl);
        }
        
        .testimonial.active {
            display: block;
            animation: fadeIn 1s ease;
        }
        
        .testimonial-text {
            font-style: italic;
            margin-bottom: 30px;
            font-size: 1.3rem;
            line-height: 1.8;
            position: relative;
            color: var(--taupe);
        }
        
        .testimonial-text:before,
        .testimonial-text:after {
            content: '"';
            font-size: 4rem;
            color: var(--gold);
            position: absolute;
            font-family: 'Cormorant Garamond', serif;
        }
        
        .testimonial-text:before {
            top: -20px;
            left: -30px;
        }
        
        .testimonial-text:after {
            bottom: -40px;
            right: -30px;
        }
        
        .testimonial-author {
            font-weight: 700;
            color: var(--cream);
            font-size: 1.1rem;
        }
        
        .testimonial-nav {
            display: flex;
            justify-content: center;
            margin-top: 40px;
        }
        
        .testimonial-dot {
            width: 14px;
            height: 14px;
            border-radius: 50%;
            background: var(--charcoal);
            margin: 0 8px;
            transition: var(--transition);
        }
        
        .testimonial-dot.active {
            background: var(--gold);
            transform: scale(1.3);
        }
        
        /* Contact Section */
        .contact {
            padding: 150px 0;
            background: var(--dark);
            position: relative;
        }
        
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
        }
        
        .contact-info h3 {
            font-size: 2.2rem;
            margin-bottom: 40px;
            position: relative;
            padding-bottom: 15px;
        }
        
        .contact-info h3:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 2px;
            background: var(--gold);
            border-radius: 2px;
        }
        
        .contact-detail {
            display: flex;
            align-items: center;
            margin-bottom: 30px;
        }
        
        .contact-icon {
            width: 60px;
            height: 60px;
            background: var(--gold);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-right: 20px;
            color: var(--darker);
            font-size: 1.5rem;
            transition: var(--transition);
        }
        
        .contact-detail:hover .contact-icon {
            transform: rotate(10deg);
        }
        
        .contact-text {
            font-size: 1.1rem;
            color: var(--taupe);
        }
        
        .contact-text strong {
            display: block;
            margin-bottom: 5px;
            color: var(--cream);
        }
        
        .social-icons {
            display: flex;
            margin-top: 40px;
        }
        
        .social-icons a {
            display: inline-flex;
            justify-content: center;
            align-items: center;
            width: 50px;
            height: 50px;
            background: var(--charcoal);
            color: var(--cream);
            border-radius: 50%;
            margin-right: 15px;
            text-decoration: none;
            transition: var(--transition);
            font-size: 1.3rem;
        }
        
        .social-icons a:hover {
            background: var(--gold);
            color: var(--darker);
            transform: translateY(-5px);
        }
        
        .contact-form {
            background: var(--charcoal);
            padding: 60px;
            box-shadow: var(--shadow);
            border-radius: var(--radius-xl);
        }
        
        .contact-form h3 {
            font-size: 2.2rem;
            margin-bottom: 40px;
            position: relative;
            padding-bottom: 15px;
        }
        
        .contact-form h3:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 2px;
            background: var(--gold);
            border-radius: 2px;
        }
        
        .form-group {
            margin-bottom: 30px;
            position: relative;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 10px;
            font-weight: 500;
            color: var(--cream);
        }
        
        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 15px 20px;
            border: 1px solid var(--taupe);
            font-family: 'Montserrat', sans-serif;
            font-size: 1rem;
            transition: var(--transition);
            background: transparent;
            color: var(--cream);
            border-radius: var(--radius-md);
        }
        
        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            border-color: var(--gold);
            outline: none;
        }
        
        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background: var(--darker);
            color: var(--taupe);
            padding: 100px 0 50px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 60px;
            margin-bottom: 60px;
        }
        
        .footer-section h3 {
            color: var(--cream);
            margin-bottom: 30px;
            font-size: 1.8rem;
            position: relative;
            padding-bottom: 15px;
        }
        
        .footer-section h3:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background: var(--gold);
            border-radius: 2px;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 15px;
        }
        
        .footer-links a {
            color: var(--taupe);
            text-decoration: none;
            transition: var(--transition);
            font-size: 1rem;
            position: relative;
        }
        
        .footer-links a:before {
            content: '→';
            position: absolute;
            left: -20px;
            opacity: 0;
            transition: var(--transition);
            color: var(--gold);
        }
        
        .footer-links a:hover:before {
            opacity: 1;
            left: -15px;
        }
        
        .footer-links a:hover {
            color: var(--gold);
            padding-left: 15px;
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
        }
        
        /* Responsive Styles */
        @media (max-width: 1200px) {
            .hero h1 {
                font-size: 3.5rem;
            }
            
            .section-title h2 {
                font-size: 2.8rem;
            }
        }
        
        @media (max-width: 992px) {
            .about-grid,
            .contact-grid {
                grid-template-columns: 1fr;
            }
            
            .nav-links {
                display: none;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .hero-content {
                margin-left: 5%;
            }
            
            .hero h1 {
                font-size: 3rem;
            }
            
            .section-title h2 {
                font-size: 2.5rem;
            }
        }
        
        @media (max-width: 768px) {
            .hero {
                height: 80vh;
            }
            
.hero h1 {
    font-size: 2.5rem;
}
            
            .section-title h2 {
                font-size: 2.2rem;
            }
            
            .services-grid,
            .portfolio-grid {
                grid-template-columns: 1fr;
            }
            
            .service-card,
            .portfolio-item {
                margin-bottom: 30px;
            }
            
            .contact-form {
                padding: 30px;
            }
            
            .filter-btn {
                padding: 10px 20px;
                margin: 5px;
            }
            
            * {
                cursor: auto;
            }
            
            .cursor, .cursor-follower {
                display: none;
            }
        }
        
        /* Animations */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        /* Luxury Elements */
        .luxury-divider {
            width: 100px;
            height: 2px;
            background: var(--gold);
            margin: 30px auto;
            border-radius: 2px;
        }
        
        .gold-text {
            color: var(--gold);
        }
        
        .decorative-element {
            position: absolute;
            width: 200px;
            height: 200px;
            border: 2px solid var(--gold);
            opacity: 0.1;
            z-index: -1;
            border-radius: var(--radius-lg);
        }
        
        /* Modal */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }
        
        .modal.open {
            opacity: 1;
            visibility: visible;
        }
        
        .modal-content {
            max-width: 90%;
            max-height: 90%;
            position: relative;
            border-radius: var(--radius-lg);
            overflow: hidden;
        }
        
        .modal-content img {
            max-width: 100%;
            max-height: 100%;
            display: block;
        }
        
        .modal-close {
            position: absolute;
            top: -40px;
            right: 0;
            color: var(--cream);
            font-size: 2rem;
        }
        
        /* Additional Luxury Elements */
        .luxury-border {
            position: relative;
        }
        
        .luxury-border:before {
            content: '';
            position: absolute;
            top: 20px;
            left: 20px;
            right: 20px;
            bottom: 20px;
            border: 1px solid var(--gold);
            opacity: 0.3;
            pointer-events: none;
            border-radius: var(--radius-lg);
        }
        
        .texture-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url('https://www.transparenttextures.com/patterns/black-paper.png');
            opacity: 0.05;
            pointer-events: none;
        }
        
        .sparkle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: var(--gold);
            border-radius: 50%;
            opacity: 0;
            animation: sparkle 3s infinite;
        }
        
        @keyframes sparkle {
            0% {
                opacity: 0;
                transform: translateY(0) rotate(0deg);
            }
            10% {
                opacity: 1;
            }
            100% {
                opacity: 0;
                transform: translateY(-50px) rotate(360deg);
            }
        }
        
        .floating-element {
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-20px);
            }
            100% {
                transform: translateY(0px);
            }
        }
        
        /* Statistics Section */
        .statistics {
            padding: 100px 0;
            background: var(--charcoal);
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }
        
        .stat-item {
            text-align: center;
            padding: 40px 20px;
            background: var(--dark);
            border-radius: var(--radius-xl);
            transition: var(--transition);
        }
        
.stat-item:hover {
    transform: translateY(-5px);
    box-shadow: var(--shadow);
}
        
        .stat-number {
            font-size: 3.5rem;
            font-weight: 700;
            color: var(--gold);
            margin-bottom: 15px;
            font-family: 'Cormorant Garamond', serif;
        }
        
        .stat-text {
            font-size: 1.1rem;
            color: var(--taupe);
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        /* Process Section */
        .process {
            padding: 150px 0;
            background: var(--dark);
        }
        
        .process-steps {
            display: flex;
            justify-content: space-between;
            position: relative;
            margin: 80px 0;
        }
        
        .process-steps:before {
            content: '';
            position: absolute;
            top: 40px;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--taupe);
            opacity: 0.3;
            z-index: -1;
            border-radius: 2px;
        }
        
        .process-step {
            text-align: center;
            position: relative;
            width: 25%;
        }
        
        .step-number {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: var(--gold);
            color: var(--darker);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.8rem;
            margin: 0 auto 30px;
            position: relative;
            font-weight: 700;
        }
        
        .step-content h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }
        
        .step-content p {
            color: var(--taupe);
        }
        
        /* Team Section */
        .team {
            padding: 150px 0;
            background: var(--darker);
        }
        
        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }
        
        .team-member {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .team-image {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            overflow: hidden;
            margin: 0 auto 30px;
            position: relative;
        }
        
        .team-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .team-member:hover .team-image img {
            transform: scale(1.1);
        }
        
        .team-image:before {
            content: '';
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            border: 2px solid var(--gold);
            border-radius: 50%;
            opacity: 0;
            transition: var(--transition);
        }
        
        .team-member:hover .team-image:before {
            opacity: 1;
            top: 5px;
            left: 5px;
            right: 5px;
            bottom: 5px;
        }
        
        .team-info h3 {
            font-size: 1.8rem;
            margin-bottom: 10px;
        }
        
        .team-info p {
            color: var(--taupe);
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <!-- Enhanced Custom Cursor -->
    <div class="cursor"></div>
    <div class="cursor-follower"></div>

    <!-- Preloader -->
    <div class="preloader">
        <div class="preloader-text">
            <span>L</span>
            <span>O</span>
            <span>V</span>
            <span>E</span>
            <span>&nbsp;</span>
            <span>S</span>
            <span>T</span>
            <span>O</span>
            <span>R</span>
            <span>I</span>
            <span>E</span>
            <span>S</span>
        </div>
    </div>

    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <a href="#" class="logo">Love <span>Stories</span></a>
                <ul class="nav-links">
                    <li><a href="#home" class="nav-link active">Home</a></li>
                    <li><a href="#about" class="nav-link">About</a></li>
                    <li><a href="#services" class="nav-link">Services</a></li>
                    <li><a href="#portfolio" class="nav-link">Portfolio</a></li>
                    <li><a href="#testimonials" class="nav-link">Testimonials</a></li>
                    <li><a href="#contact" class="nav-link">Contact</a></li>
                </ul>
                <div class="mobile-menu-btn">
                    <i class="fas fa-bars"></i>
                </div>
            </nav>
        </div>
    </header>

    <!-- Home Page -->
    <div id="home" class="page active">
        <!-- Hero Section -->
        <section class="hero">
            <div class="texture-overlay"></div>
            <div class="container">
                <div class="hero-content">
                    <h1>Creating Unforgettable Wedding Experiences</h1>
                    <p>Let us transform your dream wedding into a beautiful reality with our expert planning services in Rhodes, Greece.</p>
                    <a href="#contact" class="btn">Start Planning</a>
                </div>
            </div>
            <div class="hero-scroll">
                <span>Scroll Down</span>
                <i class="fas fa-chevron-down"></i>
            </div>
        </section>

        <!-- Statistics Section -->
        <section class="statistics">
            <div class="container">
                <div class="stats-grid">
                    <div class="stat-item">
                        <div class="stat-number" data-count="150">0</div>
                        <div class="stat-text">Weddings Planned</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number" data-count="12">0</div>
                        <div class="stat-text">Years of Experience</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number" data-count="35">0</div>
                        <div class="stat-text">Destination Weddings</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number" data-count="100">0</div>
                        <div class="stat-text">Happy Couples</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section class="about" id="about">
            <div class="texture-overlay"></div>
            <div class="container">
                <div class="about-grid">
                    <div class="about-content">
                        <h2>Your Love Story Deserves a Beautiful Celebration</h2>
                        <p>At Love Stories Events Rhodes, we specialize in creating luxurious, personalized weddings that reflect your unique love story. With our expertise and attention to detail, we ensure that your special day is everything you've dreamed of and more.</p>
                        <p>Based in the beautiful island of Rhodes, Greece, we have extensive knowledge of the best venues, vendors, and locations to make your wedding truly magical.</p>
                        <a href="#contact" class="btn btn-outline">Discover More</a>
                    </div>
                    <div class="about-image luxury-border">
                        <img src="https://images.unsplash.com/photo-1583939003579-730cec57d2e9?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Wedding Planning">
                    </div>
                </div>
            </div>
        </section>

        <!-- Process Section -->
        <section class="process">
            <div class="texture-overlay"></div>
            <div class="container">
                <div class="section-title">
                    <h2>Our Process</h2>
                    <p>How we create your perfect wedding experience</p>
                </div>
                <div class="process-steps">
                    <div class="process-step">
                        <div class="step-number">01</div>
                        <div class="极狐step-content">
                            <h3>Consultation</h3>
                            <p>We begin with an in-depth consultation to understand your vision and preferences.</p>
                        </div>
                    </div>
                    <div class="process-step">
                        <div class="step-number">02</div>
                        <div class="step-content">
                            <h3>Planning</h3>
                            <p>Our team creates a detailed plan tailored to your specific needs and desires.</p>
                        </div>
                    </div>
                    <div class="process-step">
                        <div class="step-number">03</div>
                        <div class="step-content">
                            <h3>Execution</h3>
                            <p>We handle all the details to ensure your wedding day is flawless and memorable.</p>
                        </div>
                    </div>
                    <div class="process-step">
                        <div class="step-number">04</div>
                        <div class="step-content">
                            <h3>Enjoyment</h3>
                            <p>You relax and enjoy your special day while we manage everything behind the scenes.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Services Section -->
        <section class="services" id="services">
            <div class="texture-overlay"></div>
            <div class="container">
                <div class="section-title">
                    <h2>Our Services</h2>
                    <p>Comprehensive wedding planning services tailored to your needs</p>
                </div>
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">💒</div>
                        <h3>Full Wedding Planning</h3>
                        <p>From concept to execution, we handle every detail to ensure your wedding day is perfect.</p>
                        <a href="#" class="btn btn-outline">Learn More</a>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">🎨</div>
                        <h3>Design & Decor</h3>
                        <p>Custom design concepts that reflect your unique style and vision for your special day.</p>
                        <a href="#" class="btn btn-outline">Learn More</a>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">✈️</div>
                        <h3>Destination Weddings</h3>
                        <p>Expert planning for beautiful weddings in the stunning locations of Rhodes, Greece.</p>
                        <a href="#" class="btn btn-outline">Learn More</a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Portfolio Section -->
        <section class="portfolio" id="portfolio">
            <div class="texture-overlay"></div>
            <div class="container">
                <div class="section-title">
                    <h2>Our Portfolio</h2>
                    <p>Some of our recent beautiful weddings and events</p>
                </div>
                <div class="portfolio-filter">
                    <button class="filter-btn active" data-filter="all">All</button>
                    <button class="filter-btn" data-filter="wedding">Weddings</button>
                    <button class="filter-btn" data-filter="engagement">Engagements</button>
                    <button class="filter-btn" data-filter="birthday">Birthdays</button>
                </div>
                <div class="portfolio-grid">
                    <div class="portfolio-item" data-category="wedding">
                        <img src="https://images.unsplash.com/photo-1519657337289-0776531f15c9?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Garden Wedding">
                        <div class="portfolio-overlay">
                            <h3>O&B Wedding</h3>
                            <p>A beautiful garden celebration in Rhodes</p>
                        </div>
                    </div>
                    <div class="portfolio-item" data-category="wedding">
                        <img src="https://images.unsplash.com/photo-1465495976277-4387d4b0b4c6?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Beach Wedding">
                        <div class="portfolio-overlay">
                            <h3>M&J Beach Wedding</h3>
                            <p>Sunset ceremony on a private beach</p>
                        </div>
                    </div>
                    <div class="portfolio-item" data-category="birthday">
                        <img src="https://images.unsplash.com/photo-1532710093739-9480c53d04b5?ixlib=rb-1.2.1&auto=format&fit=crop&极狐w=1350&q=80" alt="Birthday Celebration">
                        <div class="portfolio-overlay">
                            <h极狐3>Birthdays</h3>
                            <p>Elegant birthday celebrations</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Testimonials Section -->
        <section class="testimonials" id="testimonials">
            <div class="texture-overlay"></div>
            <div class="container">
                <div class="section-title">
                    <h2>Testimonials</h2>
                    <p>What our couples say about us</p>
                </div>
                <div class="testimonial-slider">
                    <div class="testimonial active">
                        <p class="testimonial-text">Love Stories Events made our dream wedding a reality. Their attention to detail and professional approach took all the stress out of planning. Our Rhodes destination wedding was absolutely perfect!</p>
                        <p class="testimonial-author">- Mathilde & Fontana</p>
                    </div>
                    <div class="testimonial">
                        <p class="testimonial-text">From the initial consultation to the final send-off, the team was incredible. They understood our vision and executed it flawlessly. Our beach wedding was pure magic!</p>
                        <p class="testimonial-author">- VICTORIE & JOSH A</p>
                    </div>
                    <div class="testimonial">
                        <p class="testimonial-text">We were planning our wedding from abroad, but Love Stories made it feel like they were right there with us. Their vendor recommendations were spot-on and our day was perfect.</p>
                        <p class="testimonial-author">- Sophia & David</p>
                    </div>
                </div>
                <div class="testimonial-nav">
                    <div class="testimonial-dot active" data-index="0"></div>
                    <div class="testimonial-dot" data-index="1"></div>
                    <div class="testimonial-dot" data-index="2"></div>
                </div>
            </div>
        </section>

        <!-- Team Section -->
        <section class="team">
            <div class="texture-overlay"></div>
            <div class="container">
                <div class="section-title">
                    <h2>Our Team</h2>
                    <p>The talented professionals behind Love Stories Events</p>
                </div>
                <div class="team-grid">
                    <div class="team-member">
                        <div class="team-image">
                            <img src="https://images.unsplash.com/photo-1560250097-0b93528c311a?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Team Member">
                        </div>
                        <div class="team-info">
                            <h3>Elena Rodriguez</h3>
                            <p>Creative Director & Founder</p>
                            <div class="social-icons">
                                <a href="#"><i class="fab fa-instagram"></i></a>
                                <a href="#"><i class="fab fa-linkedin"></i></a>
                            </div>
                        </div>
                    </div>
                    <div class="team-member">
                        <div class="team-image">
                            <img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Team Member">
                        </div>
                        <div class="team-info">
                            <h3>Sophia Williams</h3>
                            <p>Senior Wedding Planner</p>
                            <div class="social-icons">
                                <a href="#"><i class="fab fa-instagram"></i></a>
                                <a href="#"><i class="fab fa-linkedin"></i></a>
                            </div>
                        </div>
                    </div>
                    <div class="team-member">
                        <div class="team-image">
                            <img src="https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Team Member">
                        </div>
                        <div class="team-info">
                            <h3>Michael Johnson</h3>
                            <p>Event Designer</p>
                            <div class="social-icons">
                                <a href="#"><i class="fab fa-instagram"></i></a>
                                <a href="#"><i class="fab fa-linkedin"></i></a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="contact" id="contact">
            <div class="texture-overlay"></div>
            <div class="container">
                <div class="section-title">
                    <h2>Contact Us</h2>
                    <p>Get in touch to start planning your special day</p>
                </div>
                <div class="contact-grid">
                    <div class="contact-info">
                        <h3>Get In Touch</h3>
                        <div class="contact-detail">
                            <div class="contact-icon">
                                <i class="fas fa-map-marker-alt"></i>
                            </div>
                            <div class="contact-text">
                                <strong>Address</strong>
                                Rhodes, Greece
                            </div>
                        </div>
                        <div class="contact-detail">
                            <div class="contact-icon">
                                <i class="fas fa-phone"></i>
                            </div>
                            <div class="contact-text">
                                <strong>Phone</strong>
                                +30 693 290 8743
                            </div>
                        </div>
                        <div class="contact-detail">
                            <div class="contact-icon">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <div class="contact-text">
                                <strong>Email</strong>
                                info@lovestoriesevents.com
                            </div>
                        </div>
                        <div class="social-icons">
                            <a href="#"><i class="fab fa-facebook-f"></i></a>
                            <a href="#"><i class="fab fa-instagram"></i></a>
                            <a href="#"><i class="fab fa-pinterest-p"></i></a>
                            <a href="#"><i class="fab fa-twitter"></i></a>
                        </div>
                    </div>
                    <div class="contact-form">
                        <h3>Send Us a Message</h3>
                        <form>
                            <div class="form-group">
                                <label for="name">Your Name</label>
                                <input type="text" id="name" required>
                            </div>
                            <div class="form-group">
                                <label for="email">Your Email</label>
                                <input type="email" id="email" required>
                            </div>
                            <div class="form-group">
                                <label for="event-type">Event Type</label>
                                <select id="event-type">
                                    <option value="">Select Event Type</option>
                                    <option value="wedding">Wedding</option>
                                    <option value="engagement">Engagement Party</option>
                                    <option value="birthday">Birthday</option>
                                    <option value="anniversary">Anniversary</option>
                                    <option value="other">Other</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label for="message">Your Message</label>
                                <textarea id="message" required></textarea>
                            </div>
                            <button type="submit" class="btn">Send Message</button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer>
        <div class="texture-overlay"></div>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>Love Stories Events</h3>
                    <p>Creating unforgettable wedding experiences with personalized planning and exquisite attention to detail in Rhodes, Greece.</p>
                </div>
                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#home">Home</a></li>
                        <li><a href="#about">About</a></li>
                        <li><a href="#services">Services</a></li>
                        <li><a href="#portfolio">Portfolio</a></li>
                        <li><a href="#testimonials">Testimonials</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Services</h3>
                    <ul class="footer-links">
                        <li><a href="#">Wedding Planning</a></li>
                        <li><a href="#">Destination Weddings</a></li>
                        <li><a href="#">Event Design</a></li>
                        <li><a href="#">Vendor Coordination</a></li>
                        <li><a href="#">Day-of Coordination</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2023 Love Stories Events Rhodes. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Modal for portfolio items -->
    <div class="modal">
        <div class="modal-content">
            <img src="" alt="">
            <div class="modal-close">
                <i class="fas fa-times"></i>
            </div>
        </div>
    </div>

    <script>
        // Enhanced custom cursor with instant movement
        const cursor = document.querySelector('.cursor');
        const cursorFollower = document.querySelector('.cursor-follower');
        
        // Track mouse movement
        document.addEventListener('mousemove', function(e) {
            // Move cursor instantly
            cursor.style.left = `${e.clientX}px`;
            cursor.style.top = `${e.clientY}px`;
            
            // Move follower with minimal delay for smooth effect
            setTimeout(() => {
                cursorFollower.style.left = `${e.clientX}px`;
                cursorFollower.style.top = `${e.clientY}px`;
            }, 50);
            
            cursor.style.opacity = '1';
            cursorFollower.style.opacity = '1';
        });
        
        // Hover effect for cursor with zoom
        const hoverElements = document.querySelectorAll('a, button, .btn, .portfolio-item, .filter-btn, .nav-links a, .service-card, .team-member, .contact-detail, .social-icons a');
        
        hoverElements.forEach(el => {
            el.addEventListener('mouseenter', () => {
                cursor.classList.add('zoom');
                cursorFollower.classList.add('zoom');
            });
            
            el.addEventListener('mouseleave', () => {
                cursor.classList.remove('zoom');
                cursorFollower.classList.remove('zoom');
            });
        });
        
        // Click effect for cursor
        document.addEventListener('mousedown', () => {
            cursor.classList.add('click');
        });
        
        document.addEventListener('mouseup', () => {
            cursor.classList.remove('click');
        });
        
        // Hide cursor when leaving window
        document.addEventListener('mouseout', () => {
            cursor.style.opacity = '0';
            cursorFollower.style.opacity = '0';
        });
        
        document.addEventListener('mouseover', () => {
            cursor.style.opacity = '1';
            cursorFollower.style.opacity = '1';
        });
        
        // Preloader animation
        document.addEventListener('DOMContentLoaded', function() {
            const preloader = document.querySelector('.preloader');
            const preloaderText = document.querySelector('.preloader-text');
            const spans = preloaderText.querySelectorAll('span');
            
            // Animate each letter with a delay
            spans.forEach((span, index) => {
                setTimeout(() => {
                    span.style.opacity = 1;
                    span.style.transform = 'translateY(0)';
                }, index * 100);
            });
            
            // Hide preloader after animation completes
            setTimeout(() => {
                preloader.classList.add('hidden');
                
                // Show hero content after preloader is hidden
                setTimeout(() => {
                    const heroContent = document.querySelector('.hero-content');
                    const heroScroll = document.querySelector('.hero-scroll');
                    
                    heroContent.classList.add('visible');
                    
                    setTimeout(() => {
                        heroScroll.classList.add('visible');
                    }, 500);
                }, 300);
            }, 2000);
            
            // Initialize animations
            initAnimations();
            
            // Initialize counters
            initCounters();
            
            // Create sparkle effects
            createSparkles();
        });
        
        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });
        
        // Testimonial slider
        const testimonials = document.querySelectorAll('.testimonial');
        const dots = document.querySelectorAll('.testimonial-dot');
        let currentTestimonial = 0;
        
        function showTestimonial(index) {
            // Check if elements exist before manipulating them
            if (testimonials.length === 0 || dots.length === 0) return;
            
            testimonials.forEach(testimonial => {
                if (testimonial) testimonial.classList.remove('active');
            });
            dots.forEach(dot => {
                if (dot) dot.classList.remove('active');
            });
            
            if (testimonials[index]) testimonials[index].classList.add('active');
            if (dots[index]) dots[index].classList.add('active');
            currentTestimonial = index;
        }
        
        // Only set up testimonial slider if we have testimonials
        if (testimonials.length > 0 && dots.length > 0) {
            dots.forEach(dot => {
                dot.addEventListener('click', function() {
                    const index = parseInt(this.getAttribute('data-index'));
                    showTestimonial(index);
                });
            });
            
            // Auto-rotate testimonials
            setInterval(() => {
                currentTestimonial = (currentTestimonial + 1) % testimonials.length;
                showTestimonial(currentTestimonial);
            }, 5000);
        }
        
        // Portfolio filter
        const filterButtons = document.querySelectorAll('.filter-btn');
        const portfolioItems = document.querySelectorAll('.portfolio-item');
        
        filterButtons.forEach(button => {
            button.addEventListener('click', function() {
                // Remove active class from all buttons
                filterButtons.forEach(btn => btn.classList.remove('active'));
                
                // Add active class to clicked button
                this.classList.add('active');
                
                // Get filter value
                const filterValue = this.getAttribute('data-filter');
                
                // Show/hide portfolio items based on filter
                portfolioItems.forEach(item => {
                    if (filterValue === 'all' || item.getAttribute('data-category') === filterValue) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            });
        });
        
        // Modal functionality
        const modal = document.querySelector('.modal');
        const modalImg = document.querySelector('.modal-content img');
        const modalClose = document.querySelector('.modal-close');
        const portfolioItemsModal = document.querySelectorAll('.portfolio-item');
        
        portfolioItemsModal.forEach(item => {
            item.addEventListener('click', function() {
                const imgSrc = this.querySelector('img').getAttribute('src');
                modalImg.setAttribute('src', imgSrc);
                modal.classList.add('open');
            });
        });
        
        if (modalClose) {
            modalClose.addEventListener('click', function() {
                modal.classList.remove('open');
            });
        }
        
        // Initialize animations on page load
        function initAnimations() {
            // Initialize scroll animations
            const animatedElements = document.querySelectorAll('.about-content, .about-image, .service-card, .portfolio-item, .contact-info, .contact-form, .stat-item, .process-step, .team-member');
            
            function checkScroll() {
                animatedElements.forEach(element => {
                    const elementPosition = element.getBoundingClientRect().top;
                    const screenPosition = window.innerHeight / 1.3;
                    
                    if (elementPosition < screenPosition) {
                        element.style.opacity = 1;
                        element.style.transform = 'translateY(0)';
                    }
                });
            }
            
            // Set initial styles for animated elements
            animatedElements.forEach(element => {
                element.style.opacity = 0;
                element.style.transform = 'translateY(50px)';
                element.style.transition = 'opacity 0.8s ease, transform 0.8s ease';
            });
            
            // Check scroll on load and scroll
            window.addEventListener('scroll', checkScroll);
            checkScroll();
        }
        
        // Initialize counters
        function initCounters() {
            const counters = document.querySelectorAll('.stat-number');
            const speed = 200;
            
            counters.forEach(counter => {
                const target = parseInt(counter.getAttribute('data-count'));
                const count = parseInt(counter.innerText);
                const increment = Math.ceil(target / speed);
                
                if (count < target) {
                    counter.innerText = count + increment;
                    setTimeout(() => initCounters(), 1);
                } else {
                    counter.innerText = target;
                }
            });
        }
        
        // Create sparkle effects
        function createSparkles() {
            const heroSection = document.querySelector('.hero');
            const numberOfSparkles = 20;
            
            for (let i = 0; i < numberOfSparkles; i++) {
                const sparkle = document.createElement('div');
                sparkle.classList.add('sparkle');
                
                // Random position
                const left = Math.random() * 100;
                const top = Math.random() * 100;
                
                sparkle.style.left = `${left}%`;
                sparkle.style.top = `${top}%`;
                
                // Random delay
                const delay = Math.random() * 5;
                sparkle.style.animationDelay = `${delay}s`;
                
                if (heroSection) heroSection.appendChild(sparkle);
            }
        }
    </script>
</body>
</html>