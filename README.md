<!DOCTYPE html>
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
        /* Все стили остаются такими же как в предыдущем коде */
        /* Для экономии места не дублирую их, они уже корректны */
        
        /* Добавляем только этот небольшой фикс */
        html {
            scroll-behavior: smooth;
            scroll-padding-top: 80px;
        }
        
        @media (max-width: 768px) {
            html {
                scroll-padding-top: 120px;
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
                        <li><a href="#services" class="nav-link">Услуги</a></li>
                        <li><a href="#catalog" class="nav-link">Каталог</a></li>
                        <li><a href="#about" class="nav-link">О компании</a></li>
                        <li><a href="#contacts" class="nav-link">Контакты</a></li>
                    </ul>
                </nav>
                <div class="phone">
                    <i class="fas fa-phone"></i>
                    <a href="tel:+735321234567">+7 (3532) 123-45-67</a>
                </div>
            </div>
            <nav class="mobile-nav" id="mobileNav">
                <ul>
                    <li><a href="#services" class="nav-link">Услуги</a></li>
                    <li><a href="#catalog" class="nav-link">Каталог</a></li>
                    <li><a href="#about" class="nav-link">О компании</a></li>
                    <li><a href="#contacts" class="nav-link">Контакты</a></li>
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
                        <div><a href="tel:+735321234567">+7 (3532) 123-45-67</a></div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <div><a href="mailto:info@rahmetov-orenburg.ru">info@rahmetov-orenburg.ru</a></div>
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

    <!-- Остальной код (футер, модальные окна и т.д.) остается без изменений -->

    <script>
        // Исправленная функция для навигации
        function initNavigation() {
            const mobileMenuBtn = document.getElementById('mobileMenuBtn');
            const mobileNav = document.getElementById('mobileNav');
            
            // Мобильное меню
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
            
            // Улучшенная плавная прокрутка для всех навигационных ссылок
            document.querySelectorAll('.nav-link, .footer-column a[href^="#"], .logo a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    if (!targetId || !targetId.startsWith('#')) return;
                    
                    const targetElement = document.querySelector(targetId);
                    
                    if (targetElement) {
                        // Рассчитываем позицию с учетом фиксированного хедера
                        const headerHeight = document.getElementById('header').offsetHeight;
                        const targetPosition = targetElement.getBoundingClientRect().top + window.pageYOffset - headerHeight - 20;
                        
                        // Плавная прокрутка
                        window.scrollTo({
                            top: targetPosition,
                            behavior: 'smooth'
                        });
                        
                        // Закрытие мобильного меню после клика
                        if (mobileNav) {
                            mobileNav.classList.remove('active');
                            if (mobileMenuBtn) {
                                mobileMenuBtn.querySelector('i').className = 'fas fa-bars';
                            }
                        }
                        
                        // Обновляем URL без перезагрузки страницы
                        history.pushState(null, null, targetId);
                    }
                });
            });
            
            // Обработка скролла для шапки
            let lastScrollY = window.scrollY;
            const header = document.getElementById('header');
            
            window.addEventListener('scroll', () => {
                if (window.scrollY > 50) {
                    header.classList.add('scrolled');
                } else {
                    header.classList.remove('scrolled');
                }
                
                // Скрытие/показ шапки при скролле
                if (window.scrollY > lastScrollY && window.scrollY > 100) {
                    header.classList.add('hidden');
                } else {
                    header.classList.remove('hidden');
                }
                
                lastScrollY = window.scrollY;
            });
        }

        // Остальные функции (initCatalog, initAnimations и т.д.) остаются без изменений
        // ... (все остальные функции из предыдущего кода)

        // Упрощенная инициализация
        document.addEventListener('DOMContentLoaded', function() {
            // Скрытие анимации загрузки
            const loadingAnimation = document.getElementById('loadingAnimation');
            if (loadingAnimation) {
                setTimeout(() => {
                    loadingAnimation.classList.add('hidden');
                }, 1000);
            }
            
            // Инициализация основных функций
            initNavigation();
            initCatalog();
            initHeroAnimation();
            
            // Инициализация анимаций после загрузки
            setTimeout(() => {
                initAnimations();
                initCounters();
            }, 100);
            
            // Инициализация модальных окон и форм
            initModals();
        });

        // Базовая инициализация модальных окон
        function initModals() {
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
            
            // Закрытие по клику вне модального окна
            window.addEventListener('click', (e) => {
                if (e.target === modal) {
                    closeModalFunc();
                }
            });
            
            // Формы
            const contactForm = document.getElementById('contact-form');
            const quickForm = document.getElementById('quick-form');
            
            if (contactForm) {
                contactForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    // Здесь должна быть логика отправки формы
                    contactForm.reset();
                    closeModalFunc();
                });
            }
            
            if (quickForm) {
                quickForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    // Здесь должна быть логика отправки формы
                    quickForm.reset();
                    closeModalFunc();
                });
            }
        }

        // Упрощенные версии остальных функций для демонстрации
        function initCatalog() {
            const catalogGrid = document.getElementById('catalogGrid');
            if (!catalogGrid) return;
            
            // Простая заглушка для демонстрации
            catalogGrid.innerHTML = `
                <div class="product-card">
                    <div class="product-img">
                        <i class="fas fa-tint"></i>
                        <div class="product-badge">Хит</div>
                    </div>
                    <div class="product-content">
                        <h3>Насосная станция Grundfos</h3>
                        <p>Автоматическая насосная станция для водоснабжения дома</p>
                        <div class="product-features">
                            <span class="product-feature">Автоматика</span>
                            <span class="product-feature">Мощность 750 Вт</span>
                        </div>
                        <div class="product-price">12 500 ₽</div>
                        <div class="product-actions">
                            <button class="btn">Подробнее</button>
                            <button class="btn btn-outline">Заказать</button>
                        </div>
                    </div>
                </div>
            `;
        }

        function initHeroAnimation() {
            const hero = document.getElementById('hero');
            if (hero) {
                setTimeout(() => {
                    hero.classList.add('animate');
                }, 100);
            }
        }

        function initAnimations() {
            // Простая анимация появления элементов
            document.querySelectorAll('.service-card, .product-card').forEach((card, index) => {
                setTimeout(() => {
                    card.style.opacity = '1';
                    card.style.transform = 'translateY(0)';
                }, 100 * index);
            });
        }

        function initCounters() {
            // Простые счетчики
            const yearsCounter = document.getElementById('yearsCounter');
            const projectsCounter = document.getElementById('projectsCounter');
            const clientsCounter = document.getElementById('clientsCounter');
            
            if (yearsCounter) {
                let count = 0;
                const interval = setInterval(() => {
                    count++;
                    yearsCounter.textContent = count;
                    if (count >= 15) clearInterval(interval);
                }, 100);
            }
            
            if (projectsCounter) {
                let count = 0;
                const interval = setInterval(() => {
                    count += 50;
                    projectsCounter.textContent = count;
                    if (count >= 1200) clearInterval(interval);
                }, 50);
            }
            
            if (clientsCounter) {
                let count = 0;
                const interval = setInterval(() => {
                    count += 2;
                    clientsCounter.textContent = count + '%';
                    if (count >= 98) clearInterval(interval);
                }, 30);
            }
        }
    </script>
</body>
</html>
