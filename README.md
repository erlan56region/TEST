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
        /* Все CSS стили остаются без изменений */
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
        
        /* ... остальные стили без изменений ... */
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
                    <li><a href="#about">О компании</a></li>
                    <li><a href="#contacts">Контакты</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Герой секция -->
    <section class="hero" id="hero">
        <div class="container">
            <h1>Автономная канализация Аквалос</h1>
            <p>Профессиональные системы биологической очистки сточных вод для загородного дома и дачи в Оренбурге и Оренбургской области</p>
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
                        <i class="fas fa-recycle"></i>
                    </div>
                    <div class="service-content">
                        <h3>Монтаж автономной канализации</h3>
                        <p>Профессиональная установка септиков Аквалос для частных домов, дач и коммерческих объектов в Оренбурге и области.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-tools"></i>
                    </div>
                    <div class="service-content">
                        <h3>Обслуживание септиков</h3>
                        <p>Регулярное обслуживание, чистка и ремонт автономных канализационных систем Аквалос.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-truck"></i>
                    </div>
                    <div class="service-content">
                        <h3>Доставка и установка</h3>
                        <p>Быстрая доставка и профессиональный монтаж септиков Аквалос в Оренбурге и Оренбургской области.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Каталог -->
    <section id="catalog" class="catalog-section">
        <div class="container">
            <h2>Каталог автономных канализаций Аквалос</h2>
            <div class="catalog-filters">
                <button class="catalog-filter-btn active" data-filter="all">Все модели</button>
                <button class="catalog-filter-btn" data-filter="vertical">Вертикальные станции</button>
                <button class="catalog-filter-btn" data-filter="horizontal">Горизонтальные станции</button>
            </div>
            <div class="catalog-grid" id="catalogGrid">
                <!-- Товары будут загружены через JavaScript -->
            </div>
        </div>
    </section>

    <!-- Преимущества -->
    <section class="advantages-section">
        <div class="container">
            <h2>17 преимуществ септика Аквалос</h2>
            <div class="advantages-grid">
                <div class="advantage-item">
                    <i class="fas fa-ruble-sign"></i>
                    <h3>Оптимальное соотношение цена - качество</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-warehouse"></i>
                    <h3>Постоянное наличие на складе</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-calendar-check"></i>
                    <h3>Три рабочих дня до пользования станцией</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-bolt"></i>
                    <h3>Малое электропотребление</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-cogs"></i>
                    <h3>Отсутствие часто ломающихся устройств</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-power-off"></i>
                    <h3>Работает при отсутствии электроэнергии (до 7 суток)</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-wind"></i>
                    <h3>Полное отсутствие запаха</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-snowflake"></i>
                    <h3>Работа при любых экстремальных погодных условиях</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-shield-alt"></i>
                    <h3>Гарантия на корпус 50 лет</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-tint"></i>
                    <h3>Нечувствительность к пиковым потокам</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-filter"></i>
                    <h3>Степень очистки 96-98%</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-flask"></i>
                    <h3>Не используются химические вещества</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-user-cog"></i>
                    <h3>Самостоятельное обслуживание</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-volume-mute"></i>
                    <h3>Низкий уровень шума</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-hand-holding-usd"></i>
                    <h3>Возможность оплаты после сдачи объекта</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-truck-loading"></i>
                    <h3>Не нужна ассенизаторская машина</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-exchange-alt"></i>
                    <h3>Простота переоборудования</h3>
                </div>
            </div>
        </div>
    </section>

    <!-- Модальное окно товара -->
    <div class="product-modal" id="productModal">
        <div class="product-modal-content">
            <button class="product-modal-close" id="productModalClose" aria-label="Закрыть">&times;</button>
            <div class="product-modal-body">
                <div class="product-modal-img">
                    <i class="fas fa-recycle" id="modalProductIcon"></i>
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
                    <p><strong>ИП Рахметов А.К.</strong> (ИНН 561902398552) специализируется на установке автономных канализационных систем с 2010 года. Мы являемся официальными дилерами систем Аквалос в Оренбурге и Оренбургской области.</p>
                    <p>Наша команда состоит из опытных специалистов, которые используют современное оборудование и материалы для обеспечения высокого качества работ.</p>
                    <div class="stats">
                        <div class="stat-item">
                            <span class="stat-number" id="yearsCounter">0</span>
                            <span class="stat-text">Лет опыта</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number" id="projectsCounter">0</span>
                            <span class="stat-text">Установленных систем</span>
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
                            <textarea id="message" class="form-control" rows="4" placeholder="Интересует автономная канализация Аквалос..."></textarea>
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
                        <li><a href="#contacts">Контакты</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Услуги</h3>
                    <ul>
                        <li><a href="#services">Автономная канализация</a></li>
                        <li><a href="#services">Монтаж септиков</a></li>
                        <li><a href="#services">Обслуживание</a></li>
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
        // Глобальные переменные для управления модальными окнами
        let currentModal = null;

        // Данные товаров - автономные канализации Аквалос
        const products = [
            {
                id: 1,
                name: "АКВАЛОС 2 Un*",
                description: "Автономная канализация для дома и дачи",
                price: "101 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 400л/сут", "Залповый сброс: 120л", "Глубина подводящей трубы: до 30 см"],
                category: "vertical",
                badge: "Универсальная",
                fullDescription: "Автономная канализация АКВАЛОС 2 Un* предназначена для использования в частных домах и на дачах. Способ отведения воды: универсальная.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная" },
                    { name: "Производительность", value: "400л/сут" },
                    { name: "Залповый сброс", value: "120л" },
                    { name: "Глубина подводящей трубы", value: "До 30 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "860*860*1500" }
                ]
            },
            {
                id: 2,
                name: "АКВАЛОС 3 Un*",
                description: "Автономная канализация для частного дома",
                price: "113 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 600л/сут", "Залповый сброс: 200л", "Глубина подводящей трубы: до 50 см"],
                category: "vertical",
                badge: "Универсальная",
                fullDescription: "Автономная канализация АКВАЛОС 3 Un* предназначена для использования в частных домах. Способ отведения воды: универсальная.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная" },
                    { name: "Производительность", value: "600л/сут" },
                    { name: "Залповый сброс", value: "200л" },
                    { name: "Глубина подводящей трубы", value: "До 50 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "860*860*1850" }
                ]
            },
            {
                id: 3,
                name: "АКВАЛОС 4 Un*",
                description: "Автономная канализация для загородного дома",
                price: "129 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 800л/сут", "Залповый сброс: 230л", "Глубина подводящей трубы: до 60 см"],
                category: "vertical",
                badge: "Универсальная",
                fullDescription: "Автономная канализация АКВАЛОС 4 Un* предназначена для использования в загородных домах. Способ отведения воды: универсальная.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная" },
                    { name: "Производительность", value: "800л/сут" },
                    { name: "Залповый сброс", value: "230л" },
                    { name: "Глубина подводящей трубы", value: "До 60 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "860*860*2280" }
                ]
            },
            {
                id: 4,
                name: "АКВАЛОС 5 Un*",
                description: "Автономная канализация для большого дома",
                price: "141 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 900л/сут", "Залповый сброс: 320л", "Глубина подводящей трубы: до 60 см"],
                category: "vertical",
                badge: "Универсальная",
                fullDescription: "Автономная канализация АКВАЛОС 5 Un* предназначена для использования в больших домах. Способ отведения воды: универсальная.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная (2,28)" },
                    { name: "Производительность", value: "900л/сут" },
                    { name: "Залповый сброс", value: "320л" },
                    { name: "Глубина подводящей трубы", value: "До 60 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "1000*1000*2280" }
                ]
            },
            {
                id: 5,
                name: "АКВАЛОС 7 Un*",
                description: "Автономная канализация повышенной производительности",
                price: "171 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 1200л/сут", "Залповый сброс: 500л", "Глубина подводящей трубы: до 60 см"],
                category: "vertical",
                badge: "Универсальная",
                fullDescription: "Автономная канализация АКВАЛОС 7 Un* обладает повышенной производительностью. Способ отведения воды: универсальная.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная (2,28)" },
                    { name: "Производительность", value: "1200л/сут" },
                    { name: "Залповый сброс", value: "500л" },
                    { name: "Глубина подводящей трубы", value: "До 60 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "1100*1100*2280" }
                ]
            },
            {
                id: 6,
                name: "АКВАЛОС 8 Un*",
                description: "Профессиональная автономная канализация",
                price: "181 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 1600л/сут", "Залповый сброс: 630л", "Глубина подводящей трубы: до 60 см"],
                category: "vertical",
                badge: "Универсальная",
                fullDescription: "Профессиональная автономная канализация АКВАЛОС 8 Un* предназначена для объектов с повышенными требованиями.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная (2,28)" },
                    { name: "Производительность", value: "1600л/сут" },
                    { name: "Залповый сброс", value: "630л" },
                    { name: "Глубина подводящей трубы", value: "До 60 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "1200*1200*2280" }
                ]
            },
            {
                id: 7,
                name: "АКВАЛОС 10 Un*",
                description: "Промышленная автономная канализация",
                price: "237 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 2000л/сут", "Залповый сброс: 800л", "Глубина подводящей трубы: до 60 см"],
                category: "vertical",
                badge: "Универсальная",
                fullDescription: "Промышленная автономная канализация АКВАЛОС 10 Un* предназначена для коммерческих объектов и больших домовладений.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная (2,28)" },
                    { name: "Производительность", value: "2000л/сут" },
                    { name: "Залповый сброс", value: "800л" },
                    { name: "Глубина подводящей трубы", value: "До 60 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "1500*1500*2280" }
                ]
            },
            {
                id: 8,
                name: "Горизонтальная станция АКВАЛОС 4",
                description: "Горизонтальная автономная канализация",
                price: "148 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 800 л/сут", "Залповый сброс: 200 л", "Глубина подводящей трубы: до 30 см"],
                category: "horizontal",
                badge: "Горизонтальная",
                fullDescription: "Горизонтальная станция АКВАЛОС 4 предназначена для использования в частных домах и на дачах. Глубина подводящей трубы: до 30 см.",
                specifications: [
                    { name: "Глубина подводящей трубы", value: "До 30 см" },
                    { name: "Производительность", value: "800 л/сут" },
                    { name: "Залповый сброс", value: "200 л" },
                    { name: "Габаритные размеры", value: "1620*1000*1300" }
                ]
            },
            {
                id: 9,
                name: "Горизонтальная станция АКВАЛОС 5",
                description: "Горизонтальная автономная канализация",
                price: "158 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 900 л/сут", "Залповый сброс: 300 л", "Глубина подводящей трубы: до 30 см"],
                category: "horizontal",
                badge: "Горизонтальная",
                fullDescription: "Горизонтальная станция АКВАЛОС 5 предназначена для использования в частных домах. Глубина подводящей трубы: до 30 см.",
                specifications: [
                    { name: "Глубина подводящей трубы", value: "До 30 см" },
                    { name: "Производительность", value: "900 л/сут" },
                    { name: "Залповый сброс", value: "300 л" },
                    { name: "Габаритные размеры", value: "1820*1000*1300" }
                ]
            },
            {
                id: 10,
                name: "Горизонтальная станция АКВАЛОС 7",
                description: "Горизонтальная автономная канализация",
                price: "194 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 1200 л/сут", "Залповый сброс: 550 л", "Глубина подводящей трубы: до 30 см"],
                category: "horizontal",
                badge: "Горизонтальная",
                fullDescription: "Горизонтальная станция АКВАЛОС 7 предназначена для использования в загородных домах. Глубина подводящей трубы: до 30 см.",
                specifications: [
                    { name: "Глубина подводящей трубы", value: "До 30 см" },
                    { name: "Производительность", value: "1200 л/сут" },
                    { name: "Залповый сброс", value: "550 л" },
                    { name: "Габаритные размеры", value: "2120*1000*1300" }
                ]
            },
            {
                id: 11,
                name: "Горизонтальная станция АКВАЛОС 10",
                description: "Горизонтальная автономная канализация",
                price: "246 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 2000 л/сут", "Залповый сброс: 800 л", "Глубина подводящей трубы: до 30 см"],
                category: "horizontal",
                badge: "Горизонтальная",
                fullDescription: "Горизонтальная станция АКВАЛОС 10 предназначена для использования в больших домах и коммерческих объектах. Глубина подводящей трубы: до 30 см.",
                specifications: [
                    { name: "Глубина подводящей трубы", value: "До 30 см" },
                    { name: "Производительность", value: "2000 л/сут" },
                    { name: "Залповый сброс", value: "800 л" },
                    { name: "Габаритные размеры", value: "2120*1260*1570" }
                ]
            }
        ];

        // Добавляем стили для секции преимуществ
        const style = document.createElement('style');
        style.textContent = `
            .advantages-section {
                padding: 80px 0;
                background-color: var(--light);
            }
            
            .advantages-grid {
                display: grid;
                grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
                gap: 25px;
                margin-top: 40px;
            }
            
            .advantage-item {
                background: var(--white);
                padding: 25px;
                border-radius: 12px;
                text-align: center;
                box-shadow: var(--shadow);
                transition: var(--transition);
            }
            
            .advantage-item:hover {
                transform: translateY(-5px);
            }
            
            .advantage-item i {
                font-size: 48px;
                color: var(--primary);
                margin-bottom: 15px;
            }
            
            .advantage-item h3 {
                font-size: 16px;
                font-weight: 600;
                color: var(--dark);
            }
        `;
        document.head.appendChild(style);

        // Остальной JavaScript код остается без изменений
        // ... (остальной JavaScript код из предыдущего ответа)
    </script>
</body>
</html>
