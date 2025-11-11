<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ИП Рахметов А.К. - Водоснабжение и отопление</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    <style>
        :root {
            --primary: #0056b3;
            --primary-dark: #003d82;
            --secondary: #00b894;
            --dark: #343a40;
            --light: #f8f9fa;
            --gray: #6c757d;
            --white: #ffffff;
            --black: #0a0a0a;
            --shadow: 0 5px 15px rgba(0,0,0,0.08);
            --transition: all 0.3s ease;
        }
        
        .dark-theme {
            --primary: #4dabf7;
            --primary-dark: #339af0;
            --secondary: #00d9a5;
            --dark: #1a1a1a;
            --light: #2d2d2d;
            --gray: #a0a0a0;
            --white: #e0e0e0;
            --shadow: 0 5px 15px rgba(0,0,0,0.3);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
            background-color: var(--white);
            transition: background-color 0.5s ease, color 0.5s ease;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--primary);
            color: var(--white);
            padding: 12px 25px;
            border-radius: 8px;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            font-size: 16px;
            position: relative;
            overflow: hidden;
        }
        
        .btn:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 7px 14px rgba(0, 86, 179, 0.2);
        }
        
        section {
            padding: 80px 0;
        }
        
        h2 {
            font-size: 36px;
            margin-bottom: 40px;
            text-align: center;
            position: relative;
        }
        
        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background: var(--primary);
            border-radius: 2px;
        }
        
        .theme-toggle {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--primary);
            color: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 1000;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .theme-toggle:hover {
            transform: scale(1.1);
        }
        
        header {
            background-color: var(--white);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: var(--transition);
            transform: translateY(0);
        }
        
        header.hidden {
            transform: translateY(-100%);
        }
        
        header.scrolled {
            padding: 5px 0;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }
        
        .header-inner {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
            transition: var(--transition);
        }
        
        .logo {
            font-size: 22px;
            font-weight: 700;
            color: var(--primary);
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
            font-size: 28px;
        }
        
        .logo-subtitle {
            font-size: 12px;
            color: var(--gray);
            margin-top: 2px;
        }
        
        .desktop-nav ul {
            display: flex;
            list-style: none;
        }
        
        .desktop-nav ul li {
            margin-left: 25px;
            position: relative;
        }
        
        .desktop-nav ul li a {
            font-weight: 500;
            transition: var(--transition);
            padding: 5px 0;
        }
        
        .desktop-nav ul li a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: var(--transition);
        }
        
        .desktop-nav ul li a:hover::after {
            width: 100%;
        }
        
        .desktop-nav ul li a:hover {
            color: var(--primary);
        }
        
        .phone {
            font-weight: 700;
            font-size: 18px;
            display: flex;
            align-items: center;
        }
        
        .phone i {
            margin-right: 8px;
            color: var(--primary);
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--primary);
            padding: 5px;
        }
        
        .mobile-nav {
            display: none;
            width: 100%;
            text-align: center;
            padding: 20px 0;
            background: var(--white);
            box-shadow: 0 5px 10px rgba(0,0,0,0.1);
        }
        
        .mobile-nav.active {
            display: block;
        }
        
        .mobile-nav ul {
            flex-direction: column;
            list-style: none;
        }
        
        .mobile-nav ul li {
            margin: 10px 0;
        }
        
        .mobile-nav ul li a {
            font-weight: 500;
            padding: 10px 0;
            display: block;
            transition: var(--transition);
        }
        
        .mobile-nav ul li a:hover {
            color: var(--primary);
        }
        
        .hero {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: var(--white);
            text-align: center;
            padding: 200px 0 120px;
            margin-top: 70px;
        }
        
        .hero h1 {
            font-size: 52px;
            margin-bottom: 20px;
            font-weight: 700;
        }
        
        .hero p {
            font-size: 20px;
            margin-bottom: 40px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .hero .btn {
            background-color: var(--white);
            color: var(--primary);
        }
        
        .hero .btn:hover {
            background-color: rgba(255, 255, 255, 0.9);
        }
        
        .services {
            background-color: var(--light);
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background-color: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .service-card:hover {
            transform: translateY(-10px);
        }
        
        .service-img {
            height: 200px;
            overflow: hidden;
            background-color: #f8f9fa;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 48px;
        }
        
        .service-content {
            padding: 25px;
        }
        
        .service-content h3 {
            margin-bottom: 15px;
            font-size: 22px;
        }
        
        .catalog-section {
            padding: 80px 0;
            background-color: var(--white);
        }
        
        .catalog-filters {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 40px;
        }
        
        .catalog-filter-btn {
            padding: 8px 20px;
            background: var(--white);
            border: 1px solid #ddd;
            border-radius: 30px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
        }
        
        .catalog-filter-btn:hover, .catalog-filter-btn.active {
            background: var(--primary);
            color: var(--white);
            border-color: var(--primary);
        }
        
        .catalog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
        }
        
        .product-card {
            background: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }
        
        .product-img {
            height: 200px;
            overflow: hidden;
            position: relative;
            background-color: #f8f9fa;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 48px;
        }
        
        .product-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--primary);
            color: var(--white);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
        }
        
        .product-content {
            padding: 20px;
        }
        
        .product-content h3 {
            margin-bottom: 10px;
            font-size: 18px;
            color: var(--dark);
        }
        
        .product-content p {
            color: var(--gray);
            font-size: 14px;
            margin-bottom: 15px;
            min-height: 60px;
        }
        
        .product-features {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 15px;
        }
        
        .product-feature {
            background: var(--light);
            padding: 4px 10px;
            border-radius: 15px;
            font-size: 12px;
            color: var(--dark);
        }
        
        .product-price {
            font-size: 20px;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 15px;
        }
        
        .product-actions {
            display: flex;
            gap: 10px;
        }
        
        .product-actions .btn {
            flex: 1;
            padding: 10px;
            font-size: 14px;
        }
        
        .product-actions .btn-outline {
            background: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
        }
        
        .product-actions .btn-outline:hover {
            background: var(--primary);
            color: var(--white);
        }
        
        .septics-section {
            padding: 80px 0;
            background-color: var(--light);
        }
        
        .septics-header {
            text-align: center;
            margin-bottom: 40px;
        }
        
        .septics-header h2 {
            margin-bottom: 20px;
        }
        
        .septics-description {
            font-size: 18px;
            color: var(--gray);
            max-width: 800px;
            margin: 0 auto 30px;
        }
        
        .septics-consultation {
            background: var(--primary);
            color: var(--white);
            padding: 20px;
            border-radius: 12px;
            text-align: center;
            margin-bottom: 40px;
        }
        
        .septics-types {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }
        
        .septic-type {
            background: var(--white);
            padding: 30px;
            border-radius: 12px;
            box-shadow: var(--shadow);
            text-align: center;
            transition: var(--transition);
        }
        
        .septic-type:hover {
            transform: translateY(-5px);
        }
        
        .septic-type-icon {
            font-size: 48px;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .septic-type h3 {
            margin-bottom: 15px;
            font-size: 22px;
        }
        
        .septics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
        }
        
        .septic-card {
            background: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .septic-card:hover {
            transform: translateY(-5px);
        }
        
        .septic-card-header {
            background: var(--primary);
            color: var(--white);
            padding: 20px;
            text-align: center;
        }
        
        .septic-card-body {
            padding: 20px;
        }
        
        .septic-features {
            list-style: none;
            margin-bottom: 20px;
        }
        
        .septic-features li {
            padding: 8px 0;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
        }
        
        .septic-feature-name {
            font-weight: 500;
        }
        
        .septic-feature-value {
            color: var(--gray);
        }
        
        .septic-price {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary);
            text-align: center;
            margin-bottom: 20px;
        }
        
        .product-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            padding: 20px;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .product-modal.active {
            display: flex;
            opacity: 1;
        }
        
        .product-modal-content {
            background: var(--white);
            border-radius: 12px;
            max-width: 900px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            transform: scale(0.9);
            transition: transform 0.3s ease;
        }
        
        .product-modal.active .product-modal-content {
            transform: scale(1);
        }
        
        .product-modal-close {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--gray);
            z-index: 10;
            padding: 5px;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .product-modal-body {
            display: flex;
            flex-wrap: wrap;
        }
        
        .product-modal-img {
            flex: 1;
            min-width: 300px;
            height: 400px;
            background-color: #f8f9fa;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 64px;
        }
        
        .product-modal-info {
            flex: 1;
            min-width: 300px;
            padding: 30px;
        }
        
        .product-modal-info h3 {
            font-size: 24px;
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        .product-modal-price {
            font-size: 28px;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .product-modal-description {
            margin-bottom: 20px;
            color: var(--gray);
        }
        
        .product-modal-specs {
            margin-bottom: 25px;
        }
        
        .product-modal-specs h4 {
            margin-bottom: 10px;
            font-size: 18px;
            color: var(--dark);
        }
        
        .specs-list {
            list-style: none;
        }
        
        .specs-list li {
            padding: 8px 0;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
        }
        
        .spec-name {
            font-weight: 500;
        }
        
        .spec-value {
            color: var(--gray);
        }
        
        .product-modal-actions {
            display: flex;
            gap: 15px;
        }
        
        .product-modal-actions .btn {
            flex: 1;
        }
        
        .about-section {
            padding: 80px 0;
        }
        
        .about {
            display: flex;
            align-items: center;
            gap: 50px;
        }
        
        .about-img {
            flex: 1;
            height: 450px;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            background-color: #f8f9fa;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 64px;
        }
        
        .about-content {
            flex: 1;
        }
        
        .about-content h2 {
            text-align: left;
        }
        
        .about-content h2::after {
            left: 0;
            transform: none;
        }
        
        .stats {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
        }
        
        .stat-item {
            text-align: center;
        }
        
        .stat-number {
            font-size: 36px;
            font-weight: 700;
            color: var(--primary);
            display: block;
        }
        
        .contacts {
            background-color: var(--light);
        }
        
        .contacts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .contact-info {
            background-color: var(--white);
            padding: 30px;
            border-radius: 12px;
            box-shadow: var(--shadow);
        }
        
        .contact-info h3 {
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .contact-item {
            margin-bottom: 15px;
            display: flex;
            align-items: flex-start;
        }
        
        .contact-item i {
            margin-right: 10px;
            color: var(--primary);
            width: 20px;
            text-align: center;
            font-size: 18px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: var(--transition);
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(0, 86, 179, 0.1);
        }
        
        footer {
            background-color: var(--dark);
            color: var(--white);
            padding: 60px 0 20px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .footer-column {
            flex: 1;
            min-width: 200px;
        }
        
        .footer-column h3 {
            margin-bottom: 20px;
            font-size: 18px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 30px;
            height: 2px;
            background: var(--primary);
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: var(--transition);
        }
        
        .social-links a:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 14px;
            color: rgba(255, 255, 255, 0.7);
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            padding: 20px;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .modal.active {
            display: flex;
            opacity: 1;
        }
        
        .modal-content {
            background: var(--white);
            border-radius: 12px;
            padding: 30px;
            max-width: 500px;
            width: 90%;
            position: relative;
            transform: scale(0.9);
            transition: transform 0.3s ease;
        }
        
        .modal.active .modal-content {
            transform: scale(1);
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--gray);
            padding: 5px;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            padding: 15px 25px;
            background: var(--primary);
            color: var(--white);
            border-radius: 8px;
            box-shadow: var(--shadow);
            transform: translateX(150%);
            transition: transform 0.3s;
            z-index: 1000;
        }
        
        .notification.show {
            transform: translateX(0);
        }
        
        .loading-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--white);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.5s ease, visibility 0.5s ease;
        }
        
        .loading-animation.hidden {
            opacity: 0;
            visibility: hidden;
        }
        
        .loader {
            width: 50px;
            height: 50px;
            border: 5px solid rgba(0, 86, 179, 0.2);
            border-radius: 50%;
            border-top-color: var(--primary);
            animation: spin 1s ease-in-out infinite;
        }
        
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
        
        @media (max-width: 992px) {
            .about {
                flex-direction: column;
            }
            
            .about-content h2 {
                text-align: center;
            }
            
            .about-content h2::after {
                left: 50%;
                transform: translateX(-50%);
            }
            
            .stats {
                justify-content: space-around;
            }
            
            .product-modal-body {
                flex-direction: column;
            }
            
            .product-modal-img {
                height: 250px;
                min-width: 100%;
            }
        }
        
        @media (max-width: 768px) {
            .desktop-nav {
                display: none;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .header-inner {
                flex-wrap: wrap;
            }
            
            .phone {
                margin-top: 10px;
                width: 100%;
                justify-content: center;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .stats {
                flex-direction: column;
                gap: 20px;
            }
            
            h2 {
                font-size: 28px;
            }
            
            .product-modal-info {
                min-width: 100%;
            }
        }
        
        @media (max-width: 576px) {
            section {
                padding: 60px 0;
            }
            
            .hero {
                padding: 150px 0 80px;
            }
            
            .catalog-grid {
                grid-template-columns: 1fr;
            }
            
            .services-grid {
                grid-template-columns: 1fr;
            }
            
            .septics-types {
                grid-template-columns: 1fr;
            }
            
            .septics-grid {
                grid-template-columns: 1fr;
            }
            
            .product-modal-actions {
                flex-direction: column;
            }
            
            .product-actions {
                flex-direction: column;
            }
            
            .footer-content {
                flex-direction: column;
            }
        }
        
        @media (max-width: 400px) {
            .hero h1 {
                font-size: 28px;
            }
            
            .hero p {
                font-size: 16px;
            }
            
            .catalog-filters {
                gap: 5px;
            }
            
            .catalog-filter-btn {
                padding: 6px 12px;
                font-size: 14px;
            }
        }
    </style>
</head>
<body>
    <!-- Анимация загрузки -->
    <div class="loading-animation" id="loadingAnimation">
        <div class="loader"></div>
    </div>

    <!-- Шапка -->
    <header id="header">
        <div class="container">
            <div class="header-inner">
                <div class="logo">
                    <i class="fas fa-tint"></i>
                    <div>
                        ИП Рахметов А.К.
                        <div class="logo-subtitle">ИНН 561902398552</div>
                    </div>
                </div>
                <button class="mobile-menu-btn" id="mobileMenuBtn" aria-label="Открыть меню">
                    <i class="fas fa-bars"></i>
                </button>
                <nav class="desktop-nav">
                    <ul>
                        <li><a href="#services">Услуги</a></li>
                        <li><a href="#catalog">Каталог</a></li>
                        <li><a href="#septics">Септики Аквалос</a></li>
                        <li><a href="#about">О компании</a></li>
                        <li><a href="#contacts">Контакты</a></li>
                    </ul>
                </nav>
                <div class="phone">
                    <i class="fas fa-phone"></i>
                    +7 (3532) 123-45-67
                </div>
            </div>
            <nav class="mobile-nav" id="mobileNav">
                <ul>
                    <li><a href="#services">Услуги</a></li>
                    <li><a href="#catalog">Каталог</a></li>
                    <li><a href="#septics">Септики Аквалос</a></li>
                    <li><a href="#about">О компании</a></li>
                    <li><a href="#contacts">Контакты</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Герой секция -->
    <section class="hero" id="hero">
        <div class="container">
            <h1>Водоснабжение и отопление</h1>
            <p>Профессиональные услуги по монтажу и обслуживанию систем водоснабжения и отопления для домов и предприятий в Оренбурге и Оренбургской области</p>
            <a href="#contacts" class="btn" id="contactBtn">Связаться с нами</a>
        </div>
    </section>

    <!-- Услуги -->
    <section id="services" class="services">
        <div class="container">
            <h2>Наши услуги</h2>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-water"></i>
                    </div>
                    <div class="service-content">
                        <h3>Монтаж систем водоснабжения</h3>
                        <p>Проектирование и установка систем водоснабжения для частных домов, квартир и коммерческих объектов в Оренбурге и области.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-fire"></i>
                    </div>
                    <div class="service-content">
                        <h3>Отопление</h3>
                        <p>Монтаж и обслуживание систем отопления любого типа: радиаторное, теплые полы, воздушное отопление для Оренбурга и области.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-recycle"></i>
                    </div>
                    <div class="service-content">
                        <h3>Канализация</h3>
                        <p>Установка и ремонт канализационных систем, включая локальные очистные сооружения для Оренбурга и Оренбургской области.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Каталог -->
    <section id="catalog" class="catalog-section">
        <div class="container">
            <h2>Каталог товаров</h2>
            <div class="catalog-filters">
                <button class="catalog-filter-btn active" data-filter="all">Все товары</button>
                <button class="catalog-filter-btn" data-filter="pumps">Насосы</button>
                <button class="catalog-filter-btn" data-filter="boilers">Котлы</button>
                <button class="catalog-filter-btn" data-filter="radiators">Радиаторы</button>
                <button class="catalog-filter-btn" data-filter="pipes">Трубы и фитинги</button>
                <button class="catalog-filter-btn" data-filter="water-heaters">Водонагреватели</button>
                <button class="catalog-filter-btn" data-filter="cryology">Криология</button>
            </div>
            <div class="catalog-grid" id="catalogGrid">
                <!-- Товары будут загружены через JavaScript -->
            </div>
        </div>
    </section>

    <!-- Септики Аквалос -->
    <section id="septics" class="septics-section">
        <div class="container">
            <div class="septics-header">
                <h2>Купить септик, автономную канализацию Аквалос</h2>
                <p class="septics-description">Не знаете какую станцию выбрать? Оставьте заявку или позвоните нам!</p>
                <div class="septics-consultation">
                    <h3>Бесплатная консультация по подбору септика</h3>
                    <p>Наши специалисты помогут выбрать оптимальное решение для вашего дома</p>
                    <a href="#contacts" class="btn" style="background: var(--white); color: var(--primary); margin-top: 15px;">Получить консультацию</a>
                </div>
            </div>
            
            <div class="septics-types">
                <div class="septic-type">
                    <div class="septic-type-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <h3>До 10 человек</h3>
                    <p>Компактные решения для частных домов и дач</p>
                </div>
                <div class="septic-type">
                    <div class="septic-type-icon">
                        <i class="fas fa-arrows-alt-h"></i>
                    </div>
                    <h3>Горизонтальные станции</h3>
                    <p>Для участков с высоким уровнем грунтовых вод</p>
                </div>
                <div class="septic-type">
                    <div class="septic-type-icon">
                        <i class="fas fa-industry"></i>
                    </div>
                    <h3>Более 10 человек</h3>
                    <p>Мощные системы для коттеджей и небольших предприятий</p>
                </div>
                <div class="septic-type">
                    <div class="septic-type-icon">
                        <i class="fas fa-hard-hat"></i>
                    </div>
                    <h3>Промышленные</h3>
                    <p>Для предприятий, гостиниц, ресторанов и других коммерческих объектов</p>
                </div>
            </div>
            
            <h2 style="margin-bottom: 30px;">Популярные модели септиков Аквалос</h2>
            <div class="septics-grid" id="septicsGrid">
                <!-- Септики будут загружены через JavaScript -->
            </div>
        </div>
    </section>

    <!-- Модальное окно товара -->
    <div class="product-modal" id="productModal">
        <div class="product-modal-content">
            <button class="product-modal-close" id="productModalClose" aria-label="Закрыть">&times;</button>
            <div class="product-modal-body">
                <div class="product-modal-img">
                    <i class="fas fa-cog" id="modalProductIcon"></i>
                </div>
                <div class="product-modal-info">
                    <h3 id="modalProductName"></h3>
                    <div class="product-modal-price" id="modalProductPrice"></div>
                    <div class="product-modal-description" id="modalProductDescription"></div>
                    <div class="product-modal-specs">
                        <h4>Характеристики</h4>
                        <ul class="specs-list" id="modalProductSpecs">
                            <!-- Спецификации будут добавлены через JavaScript -->
                        </ul>
                    </div>
                    <div class="product-modal-actions">
                        <button class="btn" id="modalProductOrder">Заказать</button>
                        <button class="btn btn-outline" id="modalProductConsult">Консультация</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- О компании -->
    <section id="about" class="about-section">
        <div class="container">
            <div class="about">
                <div class="about-img">
                    <i class="fas fa-building"></i>
                </div>
                <div class="about-content">
                    <h2>О компании</h2>
                    <p><strong>ИП Рахметов А.К.</strong> (ИНН 561902398552) специализируется на услугах в области водоснабжения и отопления с 2010 года. Мы предлагаем полный комплекс услуг от проектирования до монтажа и обслуживания систем в Оренбурге и Оренбургской области.</p>
                    <p>Наша команда состоит из опытных специалистов, которые используют современное оборудование и материалы для обеспечения высокого качества работ.</p>
                    <div class="stats">
                        <div class="stat-item">
                            <span class="stat-number" id="yearsCounter">0</span>
                            <span class="stat-text">Лет опыта</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number" id="projectsCounter">0</span>
                            <span class="stat-text">Выполненных проектов</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number" id="clientsCounter">0</span>
                            <span class="stat-text">Довольных клиентов</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Контакты -->
    <section id="contacts" class="contacts">
        <div class="container">
            <h2>Контакты</h2>
            <div class="contacts-grid">
                <div class="contact-info">
                    <h3>Контактная информация</h3>
                    <div class="contact-item">
                        <i class="fas fa-user-tie"></i>
                        <div><strong>ИП Рахметов А.К.</strong></div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-id-card"></i>
                        <div>ИНН: 561902398552</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <div>г. Оренбург, ул. Примерная, д. 123</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-phone"></i>
                        <div>+7 (3532) 123-45-67</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <div>info@rahmetov-orenburg.ru</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-clock"></i>
                        <div>Пн-Пт: 9:00-18:00</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marked-alt"></i>
                        <div>Работаем по всему Оренбургу и области</div>
                    </div>
                    <div class="social-links">
                        <a href="#" aria-label="ВКонтакте"><i class="fab fa-vk"></i></a>
                        <a href="#" aria-label="Telegram"><i class="fab fa-telegram"></i></a>
                        <a href="#" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                        <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                <div class="contact-info">
                    <h3>Форма обратной связи</h3>
                    <form id="contact-form">
                        <div class="form-group">
                            <label for="name">Ваше имя</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="phone">Ваш телефон</label>
                            <input type="tel" id="phone" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="location">Ваш населенный пункт</label>
                            <input type="text" id="location" class="form-control" placeholder="Оренбург или область">
                        </div>
                        <div class="form-group">
                            <label for="message">Сообщение</label>
                            <textarea id="message" class="form-control" rows="4"></textarea>
                        </div>
                        <button type="submit" class="btn">Отправить</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Подвал -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Компания</h3>
                    <ul>
                        <li><a href="#about">О нас</a></li>
                        <li><a href="#services">Услуги</a></li>
                        <li><a href="#catalog">Каталог</a></li>
                        <li><a href="#septics">Септики Аквалос</a></li>
                        <li><a href="#contacts">Контакты</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Услуги</h3>
                    <ul>
                        <li><a href="#">Водоснабжение</a></li>
                        <li><a href="#">Отопление</a></li>
                        <li><a href="#">Канализация</a></li>
                        <li><a href="#">Септики Аквалос</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Контакты</h3>
                    <ul>
                        <li><strong>ИП Рахметов А.К.</strong></li>
                        <li>ИНН: 561902398552</li>
                        <li>+7 (3532) 123-45-67</li>
                        <li>info@rahmetov-orenburg.ru</li>
                        <li>г. Оренбург, ул. Примерная, д. 123</li>
                        <li>Работаем по Оренбургу и области</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                &copy; 2025 ИП Рахметов А.К. (ИНН 561902398552). Все права защищены. Обслуживаем Оренбург и Оренбургскую область.
            </div>
        </div>
    </footer>

    <!-- Переключатель темы -->
    <div class="theme-toggle" id="themeToggle" aria-label="Переключить тему">
        <i class="fas fa-moon" id="themeIcon"></i>
    </div>

    <!-- Модальное окно -->
    <div class="modal" id="modal">
        <div class="modal-content">
            <button class="close-modal" id="closeModal" aria-label="Закрыть">&times;</button>
            <h3>Быстрая консультация</h3>
            <form id="quick-form">
                <div class="form-group">
                    <label for="quick-name">Ваше имя</label>
                    <input type="text" id="quick-name" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="quick-phone">Ваш телефон</label>
                    <input type="tel" id="quick-phone" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="quick-location">Ваш населенный пункт</label>
                    <input type="text" id="quick-location" class="form-control" placeholder="Оренбург или область">
                </div>
                <button type="submit" class="btn">Позвоните мне</button>
            </form>
        </div>
    </div>

    <!-- Уведомление -->
    <div class="notification" id="notification">
        Сообщение отправлено успешно!
    </div>

    <script>
        // Данные товаров
        const products = [
            {
                id: 1,
                name: "Насосная станция Grundfos JPBasic 3",
                description: "Автоматическая насосная станция для водоснабжения дома",
                price: "12 500 ₽",
                icon: "fas fa-tint",
                features: ["Автоматика", "Мощность 750 Вт", "Производительность 3 м³/ч"],
                category: "pumps",
                badge: "Хит",
                fullDescription: "Насосная станция Grundfos JPBasic 3 предназначена для автоматического водоснабжения загородных домов, дач и других объектов. Оснащена защитой от сухого хода и перегрева.",
                specifications: [
                    { name: "Производительность", value: "3 м³/ч" },
                    { name: "Напор", value: "40 м" },
                    { name: "Мощность", value: "750 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "24 л" },
                    { name: "Материал корпуса", value: "Нержавеющая сталь" }
                ]
            },
            {
                id: 2,
                name: "Газовый котел Baxi Eco Four 24F",
                description: "Настенный двухконтурный газовый котел для отопления и ГВС",
                price: "45 800 ₽",
                icon: "fas fa-fire",
                features: ["Двухконтурный", "КПД 93%", "Мощность 24 кВт"],
                category: "boilers",
                badge: "Акция",
                fullDescription: "Газовый котел Baxi Eco Four 24F - надежное решение для отопления и горячего водоснабжения квартиры или частного дома. Оснащен современной системой управления и защитой.",
                specifications: [
                    { name: "Мощность отопления", value: "24 кВт" },
                    { name: "Мощность ГВС", value: "24 кВт" },
                    { name: "КПД", value: "93%" },
                    { name: "Расход газа", value: "2,78 м³/ч" },
                    { name: "Температура ГВС", value: "35-60°C" },
                    { name: "Габариты", value: "730x400x299 мм" }
                ]
            },
            {
                id: 3,
                name: "Биметаллический радиатор Global Style Plus 500",
                description: "Секционный биметаллический радиатор для систем отопления",
                price: "8 200 ₽",
                icon: "fas fa-temperature-high",
                features: ["Биметалл", "Высота 500 мм", "Теплоотдача 185 Вт"],
                category: "radiators",
                badge: "Популярный",
                fullDescription: "Биметаллический радиатор Global Style Plus 500 сочетает в себе высокую теплоотдачу и долговечность. Подходит для систем центрального и автономного отопления.",
                specifications: [
                    { name: "Теплоотдача секции", value: "185 Вт" },
                    { name: "Межосевое расстояние", value: "500 мм" },
                    { name: "Рабочее давление", value: "35 бар" },
                    { name: "Испытательное давление", value: "52,5 бар" },
                    { name: "Объем секции", value: "0,19 л" },
                    { name: "Вес секции", value: "2,15 кг" }
                ]
            }
        ];

        // Данные септиков Аквалос
        const septics = [
            {
                id: 101,
                name: "Аквалос 5",
                description: "Автономная канализация для семьи до 5 человек",
                price: "89 000 ₽",
                icon: "fas fa-home",
                features: ["До 5 человек", "Компактный", "Энергонезависимый"],
                category: "до 10 человек",
                badge: "Популярный",
                fullDescription: "Автономная канализация Аквалос 5 предназначена для загородного дома с постоянным проживанием до 5 человек. Обеспечивает эффективную очистку сточных вод.",
                specifications: [
                    { name: "Производительность", value: "1 м³/сут" },
                    { name: "Объем", value: "2500 л" },
                    { name: "Количество пользователей", value: "5 человек" },
                    { name: "Габариты", value: "2300x1200x1700 мм" },
                    { name: "Вес", value: "120 кг" },
                    { name: "Степень очистки", value: "98%" }
                ]
            },
            {
                id: 102,
                name: "Аквалос 8",
                description: "Автономная канализация для семьи до 8 человек",
                price: "112 000 ₽",
                icon: "fas fa-users",
                features: ["До 8 человек", "Высокая степень очистки", "Надежность"],
                category: "до 10 человек",
                badge: "Хит",
                fullDescription: "Автономная канализация Аквалос 8 предназначена для загородного дома с постоянным проживанием до 8 человек. Идеальное решение для средней семьи.",
                specifications: [
                    { name: "Производительность", value: "1,6 м³/сут" },
                    { name: "Объем", value: "3000 л" },
                    { name: "Количество пользователей", value: "8 человек" },
                    { name: "Габариты", value: "2500x1200x1700 мм" },
                    { name: "Вес", value: "150 кг" },
                    { name: "Степень очистки", value: "98%" }
                ]
            }
        ];

        document.addEventListener('DOMContentLoaded', function() {
            const loadingAnimation = document.getElementById('loadingAnimation');
            if (loadingAnimation) {
                setTimeout(() => {
                    loadingAnimation.classList.add('hidden');
                }, 1000);
            }
            
            initBaseFunctionality();
            initCatalog();
            initSeptics();
            initCounters();
        });

        function initBaseFunctionality() {
            const mobileMenuBtn = document.getElementById('mobileMenuBtn');
            const mobileNav = document.getElementById('mobileNav');
            
            if (mobileMenuBtn && mobileNav) {
                mobileMenuBtn.addEventListener('click', () => {
                    mobileNav.classList.toggle('active');
                    
                    const icon = mobileMenuBtn.querySelector('i');
                    if (mobileNav.classList.contains('active')) {
                        icon.className = 'fas fa-times';
                    } else {
                        icon.className = 'fas fa-bars';
                    }
                });
            }
            
            document.querySelectorAll('nav a').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    const targetElement = document.querySelector(targetId);
                    
                    if (targetElement) {
                        targetElement.scrollIntoView({ behavior: 'smooth' });
                        
                        if (mobileNav) {
                            mobileNav.classList.remove('active');
                            if (mobileMenuBtn) {
                                mobileMenuBtn.querySelector('i').className = 'fas fa-bars';
                            }
                        }
                    }
                });
            });
            
            const themeToggle = document.getElementById('themeToggle');
            const themeIcon = document.getElementById('themeIcon');
            let isDarkTheme = localStorage.getItem('darkTheme') === 'true';
            
            function applyTheme() {
                if (isDarkTheme) {
                    document.body.classList.add('dark-theme');
                    if (themeIcon) themeIcon.className = 'fas fa-sun';
                } else {
                    document.body.classList.remove('dark-theme');
                    if (themeIcon) themeIcon.className = 'fas fa-moon';
                }
            }
            
            function toggleTheme() {
                isDarkTheme = !isDarkTheme;
                localStorage.setItem('darkTheme', isDarkTheme);
                applyTheme();
            }
            
            if (themeToggle && themeIcon) {
                themeToggle.addEventListener('click', toggleTheme);
                applyTheme();
            }
            
            const modal = document.getElementById('modal');
            const contactBtn = document.getElementById('contactBtn');
            const closeModal = document.getElementById('closeModal');
            
            function openModal() {
                if (modal) {
                    modal.classList.add('active');
                    document.body.style.overflow = 'hidden';
                }
            }
            
            function closeModalFunc() {
                if (modal) {
                    modal.classList.remove('active');
                    document.body.style.overflow = 'auto';
                }
            }
            
            if (contactBtn) {
                contactBtn.addEventListener('click', (e) => {
                    e.preventDefault();
                    openModal();
                });
            }
            
            if (closeModal) {
                closeModal.addEventListener('click', closeModalFunc);
            }
            
            window.addEventListener('click', (e) => {
                if (e.target === modal) {
                    closeModalFunc();
                }
            });
            
            const contactForm = document.getElementById('contact-form');
            const quickForm = document.getElementById('quick-form');
            const notification = document.getElementById('notification');
            
            function showNotification() {
                if (notification) {
                    notification.classList.add('show');
                    
                    setTimeout(() => {
                        notification.classList.remove('show');
                    }, 3000);
                }
            }
            
            if (contactForm) {
                contactForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    setTimeout(() => {
                        contactForm.reset();
                        showNotification();
                    }, 500);
                });
            }
            
            if (quickForm) {
                quickForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    setTimeout(() => {
                        quickForm.reset();
                        closeModalFunc();
                        showNotification();
                    }, 500);
                });
            }
            
            window.addEventListener('resize', () => {
                if (window.innerWidth > 768 && mobileNav) {
                    mobileNav.classList.remove('active');
                    if (mobileMenuBtn) {
                        mobileMenuBtn.querySelector('i').className = 'fas fa-bars';
                    }
                }
            });

            let lastScrollY = window.scrollY;
            const header = document.getElementById('header');
            
            if (header) {
                window.addEventListener('scroll', () => {
                    if (window.scrollY > 50) {
                        header.classList.add('scrolled');
                    } else {
                        header.classList.remove('scrolled');
                    }
                    
                    if (window.scrollY > lastScrollY && window.scrollY > 100) {
                        header.classList.add('hidden');
                    } else {
                        header.classList.remove('hidden');
                    }
                    
                    lastScrollY = window.scrollY;
                });
            }
        }
        
        function initCatalog() {
            const catalogGrid = document.getElementById('catalogGrid');
            
            if (!catalogGrid) return;
            
            catalogGrid.innerHTML = '';
            
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.setAttribute('data-category', product.category);
                productCard.innerHTML = `
                    <div class="product-img">
                        <i class="${product.icon}"></i>
                        ${product.badge ? `<div class="product-badge">${product.badge}</div>` : ''}
                    </div>
                    <div class="product-content">
                        <h3>${product.name}</h3>
                        <p>${product.description}</p>
                        <div class="product-features">
                            ${product.features.map(feature => `<span class="product-feature">${feature}</span>`).join('')}
                        </div>
                        <div class="product-price">${product.price}</div>
                        <div class="product-actions">
                            <button class="btn" data-product-id="${product.id}">Подробнее</button>
                            <button class="btn btn-outline" data-product-id="${product.id}">Заказать</button>
                        </div>
                    </div>
                `;
                catalogGrid.appendChild(productCard);
            });
            
            initCatalogFilters();
            initProductButtons();
            initProductModal();
        }
        
        function initSeptics() {
            const septicsGrid = document.getElementById('septicsGrid');
            
            if (!septicsGrid) return;
            
            septicsGrid.innerHTML = '';
            
            septics.forEach(septic => {
                const septicCard = document.createElement('div');
                septicCard.className = 'septic-card';
                septicCard.innerHTML = `
                    <div class="septic-card-header">
                        <h3>${septic.name}</h3>
                        <p>${septic.description}</p>
                    </div>
                    <div class="septic-card-body">
                        <div class="septic-price">${septic.price}</div>
                        <ul class="septic-features">
                            ${septic.specifications.map(spec => `
                                <li>
                                    <span class="septic-feature-name">${spec.name}</span>
                                    <span class="septic-feature-value">${spec.value}</span>
                                </li>
                            `).join('')}
                        </ul>
                        <div class="product-actions">
                            <button class="btn" data-product-id="${septic.id}" data-septic="true">Подробнее</button>
                            <button class="btn btn-outline" data-product-id="${septic.id}" data-septic="true">Заказать</button>
                        </div>
                    </div>
                `;
                septicsGrid.appendChild(septicCard);
            });
            
            document.querySelectorAll('.septic-card .btn').forEach(button => {
                button.addEventListener('click', (e) => {
                    e.stopPropagation();
                    const productId = button.getAttribute('data-product-id');
                    const isSeptic = button.getAttribute('data-septic') === 'true';
                    
                    if (button.classList.contains('btn-outline')) {
                        orderProduct(productId, isSeptic);
                    } else {
                        viewProductDetails(productId, isSeptic);
                    }
                });
            });
        }
        
        function initCatalogFilters() {
            const filterButtons = document.querySelectorAll('.catalog-filter-btn');
            if (filterButtons.length === 0) return;
            
            filterButtons.forEach(button => {
                button.addEventListener('click', () => {
                    filterButtons.forEach(btn => btn.classList.remove('active'));
                    button.classList.add('active');
                    
                    const filter = button.getAttribute('data-filter');
                    filterCatalog(filter);
                });
            });
        }
        
        function filterCatalog(filter) {
            const productCards = document.querySelectorAll('.product-card');
            if (productCards.length === 0) return;
            
            productCards.forEach(card => {
                const shouldShow = filter === 'all' || card.getAttribute('data-category') === filter;
                card.style.display = shouldShow ? 'block' : 'none';
            });
        }
        
        function initProductButtons() {
            const productCards = document.querySelectorAll('.product-card');
            if (productCards.length === 0) return;
            
            productCards.forEach(card => {
                const buttons = card.querySelectorAll('.btn');
                buttons.forEach(button => {
                    button.addEventListener('click', (e) => {
                        e.stopPropagation();
                        const productId = button.getAttribute('data-product-id');
                        if (button.classList.contains('btn-outline')) {
                            orderProduct(productId, false);
                        } else {
                            viewProductDetails(productId, false);
                        }
                    });
                });
                
                card.addEventListener('click', () => {
                    const productId = card.querySelector('.btn').getAttribute('data-product-id');
                    viewProductDetails(productId, false);
                });
            });
        }
        
        function viewProductDetails(productId, isSeptic = false) {
            const product = isSeptic ? 
                septics.find(p => p.id == productId) : 
                products.find(p => p.id == productId);
                
            if (product) {
                const modal = document.getElementById('productModal');
                const modalIcon = document.getElementById('modalProductIcon');
                const modalName = document.getElementById('modalProductName');
                const modalPrice = document.getElementById('modalProductPrice');
                const modalDescription = document.getElementById('modalProductDescription');
                const modalSpecs = document.getElementById('modalProductSpecs');
                
                if (!modal || !modalIcon || !modalName || !modalPrice || !modalDescription || !modalSpecs) return;
                
                modalIcon.className = product.icon;
                modalName.textContent = product.name;
                modalPrice.textContent = product.price;
                modalDescription.textContent = product.fullDescription;
                
                modalSpecs.innerHTML = '';
                product.specifications.forEach(spec => {
                    const li = document.createElement('li');
                    li.innerHTML = `
                        <span class="spec-name">${spec.name}</span>
                        <span class="spec-value">${spec.value}</span>
                    `;
                    modalSpecs.appendChild(li);
                });
                
                modal.classList.add('active');
                document.body.style.overflow = 'hidden';
            }
        }
        
        function orderProduct(productId, isSeptic = false) {
            const product = isSeptic ? 
                septics.find(p => p.id == productId) : 
                products.find(p => p.id == productId);
                
            if (product) {
                openModal();
            }
        }
        
        function initProductModal() {
            const modal = document.getElementById('productModal');
            const closeButton = document.getElementById('productModalClose');
            const orderButton = document.getElementById('modalProductOrder');
            const consultButton = document.getElementById('modalProductConsult');
            
            if (!modal || !closeButton || !orderButton || !consultButton) return;
            
            closeButton.addEventListener('click', () => {
                closeProductModal();
            });
            
            orderButton.addEventListener('click', () => {
                closeProductModal();
                openModal();
            });
            
            consultButton.addEventListener('click', () => {
                closeProductModal();
                openModal();
            });
            
            modal.addEventListener('click', (e) => {
                if (e.target === modal) {
                    closeProductModal();
                }
            });
            
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape' && modal.classList.contains('active')) {
                    closeProductModal();
                }
            });
        }
        
        function closeProductModal() {
            const modal = document.getElementById('productModal');
            if (modal) {
                modal.classList.remove('active');
                document.body.style.overflow = 'auto';
            }
        }
        
        function initCounters() {
            const yearsCounter = document.getElementById('yearsCounter');
            const projectsCounter = document.getElementById('projectsCounter');
            const clientsCounter = document.getElementById('clientsCounter');
            
            if (yearsCounter && projectsCounter && clientsCounter) {
                let years = 0;
                let projects = 0;
                let clients = 0;
                
                const yearsInterval = setInterval(() => {
                    years++;
                    yearsCounter.textContent = years;
                    if (years >= 15) clearInterval(yearsInterval);
                }, 100);
                
                const projectsInterval = setInterval(() => {
                    projects += 50;
                    projectsCounter.textContent = projects;
                    if (projects >= 1200) clearInterval(projectsInterval);
                }, 10);
                
                const clientsInterval = setInterval(() => {
                    clients += 2;
                    clientsCounter.textContent = clients + '%';
                    if (clients >= 98) clearInterval(clientsInterval);
                }, 20);
            }
        }

        function openModal() {
            const modal = document.getElementById('modal');
            if (modal) {
                modal.classList.add('active');
                document.body.style.overflow = 'hidden';
            }
        }
    </script>
</body>
</html>
