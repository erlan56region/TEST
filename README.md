<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ИП Рахметов А.К. - Насосные станции АКВАЛОС</title>
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
        
        /* Темная тема */
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
        
        body {
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
            background-color: var(--white);
            transition: background-color 0.5s ease, color 0.5s ease;
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
        
        /* Переключатель темы */
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
        
        /* Шапка */
        header {
            background-color: var(--white);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: var(--transition);
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
        }
        
        /* Мобильная навигация */
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
        
        /* Герой секция */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://via.placeholder.com/1920x1080/0056b3/ffffff?text=Насосные+станции+АКВАЛОС') no-repeat center center/cover;
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
        
        /* Услуги */
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
        
        .service-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .service-card:hover .service-img img {
            transform: scale(1.1);
        }
        
        .service-content {
            padding: 25px;
        }
        
        .service-content h3 {
            margin-bottom: 15px;
            font-size: 22px;
        }
        
        /* Каталог */
        .catalog-section {
            padding: 80px 0;
            background-color: var(--white);
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
        
        .product-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .product-card:hover .product-img img {
            transform: scale(1.1);
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
        
        /* Модальное окно товара */
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
        
        .product-modal-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 12px 0 0 12px;
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
        
        /* О компании */
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
        
        .about-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
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
        
        /* Контакты */
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
        
        /* Подвал */
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
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 14px;
            color: rgba(255, 255, 255, 0.7);
        }
        
        /* Модальное окно */
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
        
        /* Анимация загрузки */
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
        
        /* Адаптивность */
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
            
            .product-modal-body {
                flex-direction: column;
            }
            
            .product-modal-img {
                height: 250px;
            }
            
            .product-modal-img img {
                border-radius: 12px 12px 0 0;
            }
            
            .stats {
                flex-direction: column;
                gap: 20px;
            }
        }
        
        @media (max-width: 576px) {
            section {
                padding: 60px 0;
            }
            
            h2 {
                font-size: 28px;
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
                        <li><a href="#catalog">Каталог АКВАЛОС</a></li>
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
                    <li><a href="#catalog">Каталог АКВАЛОС</a></li>
                    <li><a href="#about">О компании</a></li>
                    <li><a href="#contacts">Контакты</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Герой секция -->
    <section class="hero" id="hero">
        <div class="container">
            <h1>Насосные станции АКВАЛОС</h1>
            <p>Профессиональные автоматические насосные станции для систем водоснабжения домов, дач и предприятий в Оренбурге и Оренбургской области</p>
            <a href="#catalog" class="btn" id="catalogBtn">Смотреть каталог</a>
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
                        <i class="fas fa-cogs"></i>
                    </div>
                    <div class="service-content">
                        <h3>Обслуживание насосных станций</h3>
                        <p>Профессиональное обслуживание, ремонт и настройка насосных станций АКВАЛОС и другого оборудования.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-tools"></i>
                    </div>
                    <div class="service-content">
                        <h3>Ремонт и диагностика</h3>
                        <p>Быстрая диагностика и качественный ремонт насосного оборудования любой сложности для Оренбурга и Оренбургской области.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Каталог АКВАЛОС -->
    <section id="catalog" class="catalog-section">
        <div class="container">
            <h2>Каталог насосных станций АКВАЛОС</h2>
            <div class="catalog-grid" id="catalogGrid">
                <!-- Товары будут загружены через JavaScript -->
            </div>
        </div>
    </section>

    <!-- Модальное окно товара -->
    <div class="product-modal" id="productModal">
        <div class="product-modal-content">
            <button class="product-modal-close" id="productModalClose" aria-label="Закрыть">&times;</button>
            <div class="product-modal-body">
                <div class="product-modal-img">
                    <i class="fas fa-water-pump" id="modalProductIcon"></i>
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
                    <p><strong>ИП Рахметов А.К.</strong> (ИНН 561902398552) специализируется на услугах в области водоснабжения и установке насосных станций с 2010 года. Мы являемся официальными дилерами насосных станций АКВАЛОС в Оренбурге и Оренбургской области.</p>
                    <p>Наша команда состоит из опытных специалистов, которые используют современное оборудование и материалы для обеспечения высокого качества работ.</p>
                    <div class="stats">
                        <div class="stat-item">
                            <span class="stat-number" id="yearsCounter">0</span>
                            <span class="stat-text">Лет опыта</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number" id="projectsCounter">0</span>
                            <span class="stat-text">Установленных станций</span>
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
                        <a href="https://vk.com" target="_blank" aria-label="ВКонтакте"><i class="fab fa-vk"></i></a>
                        <a href="https://t.me" target="_blank" aria-label="Telegram"><i class="fab fa-telegram"></i></a>
                        <a href="https://wa.me/735321234567" target="_blank" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                        <a href="https://instagram.com" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
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
                            <textarea id="message" class="form-control" rows="4" placeholder="Интересует насосная станция АКВАЛОС..."></textarea>
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
                        <li><a href="#catalog">Каталог АКВАЛОС</a></li>
                        <li><a href="#contacts">Контакты</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Услуги</h3>
                    <ul>
                        <li><a href="#services">Водоснабжение</a></li>
                        <li><a href="#services">Обслуживание станций</a></li>
                        <li><a href="#services">Ремонт оборудования</a></li>
                        <li><a href="#services">Консультации</a></li>
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
        // Данные товаров АКВАЛОС с исправленными характеристиками
        const products = [
            {
                id: 1,
                name: "АКВАЛОС 1",
                description: "Бытовая насосная станция для водоснабжения",
                price: "24 500 ₽",
                icon: "fas fa-water-pump",
                features: ["Производительность 2.0 м³/ч", "Напор 35 м", "Мощность 600 Вт"],
                badge: "Бюджетная",
                fullDescription: "АКВАЛОС 1 - надежная бытовая насосная станция для водоснабжения дач и небольших домов. Идеальное решение для стабильного водоснабжения при ограниченном бюджете.",
                specifications: [
                    { name: "Производительность", value: "2.0 м³/ч" },
                    { name: "Напор", value: "35 м" },
                    { name: "Мощность", value: "600 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "20 л" },
                    { name: "Материал корпуса", value: "Нержавеющая сталь" },
                    { name: "Защита от сухого хода", value: "Да" },
                    { name: "Уровень шума", value: "55 дБ" }
                ]
            },
            {
                id: 2,
                name: "АКВАЛОС 2",
                description: "Автоматическая насосная станция для дома",
                price: "31 800 ₽",
                icon: "fas fa-water-pump",
                features: ["Производительность 3.0 м³/ч", "Напор 42 м", "Мощность 750 Вт"],
                badge: "Хит продаж",
                fullDescription: "АКВАЛОС 2 - популярная модель для автоматического водоснабжения частных домов. Оптимальное сочетание цены и производительности.",
                specifications: [
                    { name: "Производительность", value: "3.0 м³/ч" },
                    { name: "Напор", value: "42 м" },
                    { name: "Мощность", value: "750 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "24 л" },
                    { name: "Материал корпуса", value: "Нержавеющая сталь" },
                    { name: "Защита от сухого хода", value: "Да" },
                    { name: "Уровень шума", value: "53 дБ" }
                ]
            },
            {
                id: 3,
                name: "АКВАЛОС 3",
                description: "Насосная станция с увеличенным гидробаком",
                price: "38 200 ₽",
                icon: "fas fa-water-pump",
                features: ["Производительность 3.2 м³/ч", "Напор 45 м", "Гидробак 50 л"],
                badge: "Комфорт",
                fullDescription: "АКВАЛОС 3 с гидробаком 50 литров обеспечивает стабильное давление и уменьшает количество включений насоса. Идеально для семей из 3-4 человек.",
                specifications: [
                    { name: "Производительность", value: "3.2 м³/ч" },
                    { name: "Напор", value: "45 м" },
                    { name: "Мощность", value: "800 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "50 л" },
                    { name: "Материал корпуса", value: "Нержавеющая сталь" },
                    { name: "Защита от сухого хода", value: "Да" },
                    { name: "Уровень шума", value: "52 дБ" }
                ]
            },
            {
                id: 4,
                name: "АКВАЛОС 4",
                description: "Мощная насосная станция для коттеджей",
                price: "45 900 ₽",
                icon: "fas fa-water-pump",
                features: ["Производительность 3.8 м³/ч", "Напор 50 м", "Мощность 1100 Вт"],
                badge: "Для коттеджа",
                fullDescription: "АКВАЛОС 4 предназначена для водоснабжения коттеджей и домов с большим водопотреблением. Обеспечивает одновременную работу нескольких точек водозабора.",
                specifications: [
                    { name: "Производительность", value: "3.8 м³/ч" },
                    { name: "Напор", value: "50 м" },
                    { name: "Мощность", value: "1100 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "24 л" },
                    { name: "Материал корпуса", value: "Чугун" },
                    { name: "Защита от сухого хода", value: "Да" },
                    { name: "Уровень шума", value: "58 дБ" }
                ]
            },
            {
                id: 5,
                name: "АКВАЛОС 5",
                description: "Насосная станция с системой плавного пуска",
                price: "52 700 ₽",
                icon: "fas fa-water-pump",
                features: ["Плавный пуск", "Производительность 4.2 м³/ч", "Напор 55 м"],
                badge: "Энергоэффективная",
                fullDescription: "АКВАЛОС 5 оснащена системой плавного пуска, что снижает пусковые токи и продлевает срок службы оборудования. Рекомендуется для сетей с нестабильным напряжением.",
                specifications: [
                    { name: "Производительность", value: "4.2 м³/ч" },
                    { name: "Напор", value: "55 м" },
                    { name: "Мощность", value: "1200 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "24 л" },
                    { name: "Материал корпуса", value: "Нержавеющая сталь" },
                    { name: "Плавный пуск", value: "Да" },
                    { name: "Уровень шума", value: "56 дБ" }
                ]
            },
            {
                id: 6,
                name: "АКВАЛОС 6",
                description: "Профессиональная насосная станция",
                price: "61 500 ₽",
                icon: "fas fa-water-pump",
                features: ["Производительность 4.8 м³/ч", "Напор 60 м", "Гидробак 100 л"],
                badge: "Профессиональная",
                fullDescription: "АКВАЛОС 6 - профессиональное решение для объектов с высоким водопотреблением. Большой гидробак обеспечивает стабильное давление при пиковых нагрузках.",
                specifications: [
                    { name: "Производительность", value: "4.8 м³/ч" },
                    { name: "Напор", value: "60 м" },
                    { name: "Мощность", value: "1400 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "100 л" },
                    { name: "Материал корпуса", value: "Чугун" },
                    { name: "Защита от сухого хода", value: "Да" },
                    { name: "Уровень шума", value: "60 дБ" }
                ]
            },
            {
                id: 7,
                name: "АКВАЛОС 7",
                description: "Насосная станция с электронным управлением",
                price: "73 800 ₽",
                icon: "fas fa-water-pump",
                features: ["Электронное управление", "Производительность 5.5 м³/ч", "Напор 65 м"],
                badge: "Умная",
                fullDescription: "АКВАЛОС 7 с электронной системой управления обеспечивает точный контроль давления и защиту оборудования. Встроенный дисплей отображает рабочие параметры.",
                specifications: [
                    { name: "Производительность", value: "5.5 м³/ч" },
                    { name: "Напор", value: "65 м" },
                    { name: "Мощность", value: "1600 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "24 л" },
                    { name: "Материал корпуса", value: "Нержавеющая сталь" },
                    { name: "Электронное управление", value: "Да" },
                    { name: "Дисплей", value: "ЖК-дисплей" }
                ]
            },
            {
                id: 8,
                name: "АКВАЛОС 8",
                description: "Промышленная насосная станция",
                price: "89 200 ₽",
                icon: "fas fa-water-pump",
                features: ["Производительность 6.5 м³/ч", "Напор 70 м", "Мощность 2000 Вт"],
                badge: "Промышленная",
                fullDescription: "АКВАЛОС 8 - промышленная насосная станция для коммерческих объектов и небольших производств. Обеспечивает высокую производительность и надежность.",
                specifications: [
                    { name: "Производительность", value: "6.5 м³/ч" },
                    { name: "Напор", value: "70 м" },
                    { name: "Мощность", value: "2000 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "100 л" },
                    { name: "Материал корпуса", value: "Чугун" },
                    { name: "Защита от сухого хода", value: "Да" },
                    { name: "Уровень шума", value: "65 дБ" }
                ]
            },
            {
                id: 9,
                name: "АКВАЛОС 9",
                description: "Насосная станция с частотным регулированием",
                price: "112 500 ₽",
                icon: "fas fa-water-pump",
                features: ["Частотное регулирование", "Производительность 7.5 м³/ч", "Напор 75 м"],
                badge: "Премиум",
                fullDescription: "АКВАЛОС 9 с системой частотного регулирования поддерживает точное давление независимо от расхода воды. Экономит электроэнергию и продлевает срок службы.",
                specifications: [
                    { name: "Производительность", value: "7.5 м³/ч" },
                    { name: "Напор", value: "75 м" },
                    { name: "Мощность", value: "2200 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "24 л" },
                    { name: "Материал корпуса", value: "Нержавеющая сталь" },
                    { name: "Частотное регулирование", value: "Да" },
                    { name: "КПД", value: "92%" }
                ]
            },
            {
                id: 10,
                name: "АКВАЛОС 10",
                description: "Высокопроизводительная промышленная станция",
                price: "148 000 ₽",
                icon: "fas fa-water-pump",
                features: ["Производительность 9.0 м³/ч", "Напор 80 м", "Мощность 2800 Вт"],
                badge: "Экстра",
                fullDescription: "АКВАЛОС 10 - флагманская модель для объектов с экстремально высоким водопотреблением. Обеспечивает бесперебойную работу в самых demanding условиях.",
                specifications: [
                    { name: "Производительность", value: "9.0 м³/ч" },
                    { name: "Напор", value: "80 м" },
                    { name: "Мощность", value: "2800 Вт" },
                    { name: "Глубина всасывания", value: "8 м" },
                    { name: "Объем гидробака", value: "100 л" },
                    { name: "Материал корпуса", value: "Чугун" },
                    { name: "Защита от сухого хода", value: "Да" },
                    { name: "Класс защиты", value: "IP54" }
                ]
            }
        ];

        // Инициализация GSAP анимаций
        function initAnimations() {
            // Инициализация ScrollTrigger
            gsap.registerPlugin(ScrollTrigger);
            
            // Анимация появления секций при скролле
            gsap.utils.toArray('section').forEach(section => {
                gsap.fromTo(section, {
                    opacity: 0,
                    y: 50
                }, {
                    opacity: 1,
                    y: 0,
                    duration: 1,
                    ease: "power2.out",
                    scrollTrigger: {
                        trigger: section,
                        start: "top 80%",
                        end: "bottom 20%",
                        toggleActions: "play none none reverse"
                    }
                });
            });
            
            // Анимация карточек услуг
            gsap.utils.toArray('.service-card').forEach((card, i) => {
                gsap.fromTo(card, {
                    opacity: 0,
                    y: 50
                }, {
                    opacity: 1,
                    y: 0,
                    duration: 0.8,
                    delay: i * 0.1,
                    ease: "power2.out",
                    scrollTrigger: {
                        trigger: card,
                        start: "top 85%",
                        toggleActions: "play none none reverse"
                    }
                });
            });
            
            // Анимация карточек товаров
            gsap.utils.toArray('.product-card').forEach((card, i) => {
                gsap.fromTo(card, {
                    opacity: 0,
                    y: 50
                }, {
                    opacity: 1,
                    y: 0,
                    duration: 0.8,
                    delay: i * 0.1,
                    ease: "power2.out",
                    scrollTrigger: {
                        trigger: card,
                        start: "top 85%",
                        toggleActions: "play none none reverse"
                    }
                });
            });
            
            // Анимация элементов "О компании"
            gsap.fromTo('.about-img', {
                opacity: 0,
                x: -50
            }, {
                opacity: 1,
                x: 0,
                duration: 1,
                ease: "power2.out",
                scrollTrigger: {
                    trigger: '.about',
                    start: "top 80%",
                    toggleActions: "play none none reverse"
                }
            });
            
            gsap.fromTo('.about-content', {
                opacity: 0,
                x: 50
            }, {
                opacity: 1,
                x: 0,
                duration: 1,
                ease: "power2.out",
                scrollTrigger: {
                    trigger: '.about',
                    start: "top 80%",
                    toggleActions: "play none none reverse"
                }
            });
            
            // Анимация статистики
            gsap.utils.toArray('.stat-item').forEach((item, i) => {
                gsap.fromTo(item, {
                    opacity: 0,
                    y: 30
                }, {
                    opacity: 1,
                    y: 0,
                    duration: 0.8,
                    delay: i * 0.2,
                    ease: "power2.out",
                    scrollTrigger: {
                        trigger: '.stats',
                        start: "top 80%",
                        toggleActions: "play none none reverse"
                    }
                });
            });
            
            // Анимация контактных блоков
            gsap.utils.toArray('.contact-info').forEach((info, i) => {
                gsap.fromTo(info, {
                    opacity: 0,
                    y: 50
                }, {
                    opacity: 1,
                    y: 0,
                    duration: 0.8,
                    delay: i * 0.2,
                    ease: "power2.out",
                    scrollTrigger: {
                        trigger: '.contacts-grid',
                        start: "top 80%",
                        toggleActions: "play none none reverse"
                    }
                });
            });
        }

        // Улучшенная функция для анимации счетчика с GSAP
        function animateCounter(element, start, end, duration) {
            const obj = { value: start };
            gsap.to(obj, {
                value: end,
                duration: duration / 1000,
                ease: "power2.out",
                onUpdate: function() {
                    if (element.id === 'clientsCounter') {
                        element.textContent = Math.floor(obj.value) + '%';
                    } else {
                        element.textContent = Math.floor(obj.value).toLocaleString();
                    }
                },
                scrollTrigger: {
                    trigger: element,
                    start: "top 80%",
                    toggleActions: "play none none reverse"
                }
            });
        }

        // Функция для запуска счетчиков
        function initCounters() {
            const yearsCounter = document.getElementById('yearsCounter');
            const projectsCounter = document.getElementById('projectsCounter');
            const clientsCounter = document.getElementById('clientsCounter');
            
            if (yearsCounter && projectsCounter && clientsCounter) {
                animateCounter(yearsCounter, 0, 15, 2000);
                animateCounter(projectsCounter, 0, 1200, 2500);
                animateCounter(clientsCounter, 0, 98, 1800);
            }
        }

        // Инициализация каталога
        function initCatalog() {
            const catalogGrid = document.getElementById('catalogGrid');
            
            if (!catalogGrid) return;
            
            // Очистка контейнера
            catalogGrid.innerHTML = '';
            
            // Создание карточек товаров
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
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
            
            // Инициализация обработчиков событий для кнопок товаров
            initProductButtons();
            
            // Инициализация модального окна товара
            initProductModal();
        }
        
        // Инициализация обработчиков событий для кнопок товаров
        function initProductButtons() {
            const productCards = document.querySelectorAll('.product-card');
            productCards.forEach(card => {
                const buttons = card.querySelectorAll('.btn');
                buttons.forEach(button => {
                    button.addEventListener('click', (e) => {
                        e.stopPropagation();
                        const productId = button.getAttribute('data-product-id');
                        if (button.classList.contains('btn-outline')) {
                            // Заказ товара
                            orderProduct(productId);
                        } else {
                            // Просмотр подробной информации
                            viewProductDetails(productId);
                        }
                    });
                });
                
                // Клик по карточке товара
                card.addEventListener('click', () => {
                    const productId = card.querySelector('.btn').getAttribute('data-product-id');
                    viewProductDetails(productId);
                });
            });
        }
        
        // Просмотр детальной информации о товаре
        function viewProductDetails(productId) {
            const product = products.find(p => p.id == productId);
            if (product) {
                const modal = document.getElementById('productModal');
                const modalIcon = document.getElementById('modalProductIcon');
                const modalName = document.getElementById('modalProductName');
                const modalPrice = document.getElementById('modalProductPrice');
                const modalDescription = document.getElementById('modalProductDescription');
                const modalSpecs = document.getElementById('modalProductSpecs');
                
                if (!modal || !modalIcon || !modalName || !modalPrice || !modalDescription || !modalSpecs) return;
                
                // Заполнение модального окна данными товара
                modalIcon.className = product.icon;
                modalName.textContent = product.name;
                modalPrice.textContent = product.price;
                modalDescription.textContent = product.fullDescription;
                
                // Очистка и заполнение спецификаций
                modalSpecs.innerHTML = '';
                product.specifications.forEach(spec => {
                    const li = document.createElement('li');
                    li.innerHTML = `
                        <span class="spec-name">${spec.name}</span>
                        <span class="spec-value">${spec.value}</span>
                    `;
                    modalSpecs.appendChild(li);
                });
                
                // Анимация открытия модального окна
                modal.classList.add('active');
                document.body.style.overflow = 'hidden';
                
                // Анимация появления контента в модальном окне
                gsap.fromTo('.product-modal-content', {
                    scale: 0.8,
                    opacity: 0
                }, {
                    scale: 1,
                    opacity: 1,
                    duration: 0.3,
                    ease: "back.out(1.7)"
                });
            }
        }
        
        // Заказ товара
        function orderProduct(productId) {
            const product = products.find(p => p.id == productId);
            if (product) {
                // Открытие модального окна заказа
                openModal();
                // В реальном приложении здесь можно добавить логику для предзаполнения формы
            }
        }
        
        // Инициализация модального окна товара
        function initProductModal() {
            const modal = document.getElementById('productModal');
            const closeButton = document.getElementById('productModalClose');
            const orderButton = document.getElementById('modalProductOrder');
            const consultButton = document.getElementById('modalProductConsult');
            
            if (!modal || !closeButton || !orderButton || !consultButton) return;
            
            // Закрытие модального окна
            closeButton.addEventListener('click', () => {
                closeProductModal();
            });
            
            // Заказ товара из модального окна
            orderButton.addEventListener('click', () => {
                closeProductModal();
                openModal();
            });
            
            // Консультация по товару
            consultButton.addEventListener('click', () => {
                closeProductModal();
                openModal();
            });
            
            // Закрытие по клику вне модального окна
            modal.addEventListener('click', (e) => {
                if (e.target === modal) {
                    closeProductModal();
                }
            });
            
            // Закрытие по клавише Escape
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape' && modal.classList.contains('active')) {
                    closeProductModal();
                }
            });
        }
        
        // Закрытие модального окна товара
        function closeProductModal() {
            const modal = document.getElementById('productModal');
            if (modal) {
                // Анимация закрытия модального окна
                gsap.to('.product-modal-content', {
                    scale: 0.8,
                    opacity: 0,
                    duration: 0.2,
                    ease: "power2.in",
                    onComplete: () => {
                        modal.classList.remove('active');
                        document.body.style.overflow = 'auto';
                    }
                });
            }
        }
        
        // Базовая функциональность
        function initBaseFunctionality() {
            // Скрытие анимации загрузки
            const loadingAnimation = document.getElementById('loadingAnimation');
            if (loadingAnimation) {
                setTimeout(() => {
                    loadingAnimation.classList.add('hidden');
                }, 1000);
            }
            
            // Мобильное меню
            const mobileMenuBtn = document.getElementById('mobileMenuBtn');
            const mobileNav = document.getElementById('mobileNav');
            
            if (mobileMenuBtn && mobileNav) {
                mobileMenuBtn.addEventListener('click', () => {
                    mobileNav.classList.toggle('active');
                    
                    // Анимация иконки меню
                    const icon = mobileMenuBtn.querySelector('i');
                    if (mobileNav.classList.contains('active')) {
                        icon.className = 'fas fa-times';
                        gsap.fromTo(mobileNav, {
                            opacity: 0,
                            y: -20
                        }, {
                            opacity: 1,
                            y: 0,
                            duration: 0.3,
                            ease: "power2.out"
                        });
                    } else {
                        icon.className = 'fas fa-bars';
                    }
                });
            }
            
            // Плавная прокрутка
            document.querySelectorAll('nav a').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    const targetElement = document.querySelector(targetId);
                    
                    if (targetElement) {
                        // Нативная плавная прокрутка
                        const targetPosition = targetElement.getBoundingClientRect().top + window.pageYOffset - 70;
                        window.scrollTo({
                            top: targetPosition,
                            behavior: 'smooth'
                        });
                        
                        // Закрытие мобильного меню после клика
                        if (mobileNav) {
                            mobileNav.classList.remove('active');
                            mobileMenuBtn.querySelector('i').className = 'fas fa-bars';
                        }
                    }
                });
            });
            
            // Переключение темы
            const themeToggle = document.getElementById('themeToggle');
            const themeIcon = document.getElementById('themeIcon');
            let isDarkTheme = localStorage.getItem('darkTheme') === 'true';
            
            function applyTheme() {
                if (isDarkTheme) {
                    document.body.classList.add('dark-theme');
                    themeIcon.className = 'fas fa-sun';
                } else {
                    document.body.classList.remove('dark-theme');
                    themeIcon.className = 'fas fa-moon';
                }
            }
            
            function toggleTheme() {
                isDarkTheme = !isDarkTheme;
                localStorage.setItem('darkTheme', isDarkTheme);
                applyTheme();
                
                // Анимация переключателя темы
                gsap.fromTo(themeToggle, {
                    scale: 1
                }, {
                    scale: 1.2,
                    duration: 0.2,
                    yoyo: true,
                    repeat: 1
                });
            }
            
            if (themeToggle && themeIcon) {
                themeToggle.addEventListener('click', toggleTheme);
                applyTheme();
            }
            
            // Модальное окно
            const modal = document.getElementById('modal');
            const catalogBtn = document.getElementById('catalogBtn');
            const closeModal = document.getElementById('closeModal');
            
            function openModal() {
                if (modal) {
                    modal.classList.add('active');
                    document.body.style.overflow = 'hidden';
                    
                    // Анимация открытия модального окна
                    gsap.fromTo('.modal-content', {
                        scale: 0.8,
                        opacity: 0
                    }, {
                        scale: 1,
                        opacity: 1,
                        duration: 0.3,
                        ease: "back.out(1.7)"
                    });
                }
            }
            
            function closeModalFunc() {
                if (modal) {
                    // Анимация закрытия модального окна
                    gsap.to('.modal-content', {
                        scale: 0.8,
                        opacity: 0,
                        duration: 0.2,
                        ease: "power2.in",
                        onComplete: () => {
                            modal.classList.remove('active');
                            document.body.style.overflow = 'auto';
                        }
                    });
                }
            }
            
            if (catalogBtn) {
                catalogBtn.addEventListener('click', (e) => {
                    e.preventDefault();
                    openModal();
                });
            }
            
            if (closeModal) {
                closeModal.addEventListener('click', closeModalFunc);
            }
            
            // Закрытие по клику вне модального окна
            window.addEventListener('click', (e) => {
                if (e.target === modal) {
                    closeModalFunc();
                }
            });
            
            // Формы
            const contactForm = document.getElementById('contact-form');
            const quickForm = document.getElementById('quick-form');
            const notification = document.getElementById('notification');
            
            function showNotification(message = "Сообщение отправлено успешно!") {
                if (notification) {
                    notification.textContent = message;
                    notification.classList.add('show');
                    
                    // Анимация появления уведомления
                    gsap.fromTo(notification, {
                        x: 150
                    }, {
                        x: 0,
                        duration: 0.5,
                        ease: "back.out(1.7)"
                    });
                    
                    setTimeout(() => {
                        // Анимация скрытия уведомления
                        gsap.to(notification, {
                            x: 150,
                            duration: 0.3,
                            ease: "power2.in",
                            onComplete: () => {
                                notification.classList.remove('show');
                            }
                        });
                    }, 3000);
                }
            }
            
            // Обработка формы обратной связи
            if (contactForm) {
                contactForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    
                    // Получаем данные формы
                    const formData = new FormData(contactForm);
                    const data = {
                        name: formData.get('name') || document.getElementById('name').value,
                        phone: formData.get('phone') || document.getElementById('phone').value,
                        location: formData.get('location') || document.getElementById('location').value,
                        message: formData.get('message') || document.getElementById('message').value
                    };
                    
                    // В реальном приложении здесь будет отправка на сервер
                    console.log('Данные формы обратной связи:', data);
                    
                    // Имитация отправки
                    setTimeout(() => {
                        contactForm.reset();
                        showNotification("Заявка отправлена! Мы свяжемся с вами в ближайшее время.");
                    }, 500);
                });
            }
            
            // Обработка формы быстрой консультации
            if (quickForm) {
                quickForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    
                    // Получаем данные формы
                    const formData = new FormData(quickForm);
                    const data = {
                        name: formData.get('name') || document.getElementById('quick-name').value,
                        phone: formData.get('phone') || document.getElementById('quick-phone').value,
                        location: formData.get('location') || document.getElementById('quick-location').value
                    };
                    
                    // В реальном приложении здесь будет отправка на сервер
                    console.log('Данные формы быстрой консультации:', data);
                    
                    // Имитация отправки
                    setTimeout(() => {
                        quickForm.reset();
                        closeModalFunc();
                        showNotification("Заявка на консультацию отправлена! Мы перезвоним вам в течение 15 минут.");
                    }, 500);
                });
            }
            
            // Социальные сети - открытие в новом окне
            document.querySelectorAll('.social-links a').forEach(link => {
                link.setAttribute('target', '_blank');
                link.setAttribute('rel', 'noopener noreferrer');
            });
            
            // Телефонный номер
            document.querySelectorAll('.phone').forEach(phoneElement => {
                phoneElement.addEventListener('click', (e) => {
                    e.preventDefault();
                    window.open('tel:+735321234567');
                });
            });
            
            // Закрытие мобильного меню при ресайзе
            window.addEventListener('resize', () => {
                if (window.innerWidth > 768 && mobileNav) {
                    mobileNav.classList.remove('active');
                    if (mobileMenuBtn) {
                        mobileMenuBtn.querySelector('i').className = 'fas fa-bars';
                    }
                }
            });

            // Обработка скролла для шапки
            const header = document.getElementById('header');
            
            window.addEventListener('scroll', () => {
                if (window.scrollY > 50) {
                    header.classList.add('scrolled');
                } else {
                    header.classList.remove('scrolled');
                }
            });
        }
        
        // Инициализация при загрузке страницы
        document.addEventListener('DOMContentLoaded', () => {
            try {
                initBaseFunctionality();
                initCatalog();
                
                // Инициализация анимаций после небольшой задержки
                setTimeout(() => {
                    initAnimations();
                    initCounters();
                }, 100);
            } catch (error) {
                console.error('Ошибка инициализации:', error);
            }
        });
    </script>
</body>
</html>
