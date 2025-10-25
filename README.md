# TEST


























// Создаем элемент стилей и добавляем CSS
const style = document.createElement('style');
style.textContent = `
:root {
    --primary-color: #ffffff;
    --secondary-color: #000000;
    --accent-color: #007AFF;
    --text-color: #1D1D1F;
    --gray-color: #86868B;
    --transition-time: 0.6s;
    --card-bg: #F5F5F7;
}

.dark-theme {
    --primary-color: #000000;
    --secondary-color: #ffffff;
    --accent-color: #0A84FF;
    --text-color: #F5F5F7;
    --gray-color: #86868B;
    --card-bg: #1D1D1F;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    transition: background-color var(--transition-time) ease, 
                color var(--transition-time) ease,
                border-color var(--transition-time) ease,
                transform var(--transition-time) ease;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    background-color: var(--primary-color);
    color: var(--text-color);
    min-height: 100vh;
    line-height: 1.6;
}

.container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 2rem;
}

/* Header Styles */
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 3rem;
    padding: 1.5rem 0;
    border-bottom: 1px solid var(--gray-color);
}

.logo {
    display: flex;
    align-items: center;
    gap: 12px;
    font-size: 1.8rem;
    font-weight: 700;
    color: var(--text-color);
}

.logo i {
    color: var(--accent-color);
}

.nav-buttons {
    display: flex;
    gap: 1rem;
    align-items: center;
}

.theme-toggle, .contact-btn {
    background: transparent;
    border: 2px solid var(--accent-color);
    padding: 10px 20px;
    border-radius: 25px;
    color: var(--accent-color);
    cursor: pointer;
    font-weight: 600;
    display: flex;
    align-items: center;
    gap: 8px;
}

.contact-btn {
    background: var(--accent-color);
    color: white;
}

/* Hero Section */
.hero {
    text-align: center;
    padding: 4rem 0;
    margin-bottom: 3rem;
}

.hero h1 {
    font-size: 3.5rem;
    font-weight: 700;
    margin-bottom: 1.5rem;
    background: linear-gradient(135deg, var(--accent-color), #5856D6);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.hero p {
    font-size: 1.3rem;
    color: var(--gray-color);
    max-width: 700px;
    margin: 0 auto 2rem;
}

.features {
    display: flex;
    justify-content: center;
    gap: 2rem;
    flex-wrap: wrap;
    margin-top: 2rem;
}

.feature {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 1.1rem;
}

.feature i {
    color: var(--accent-color);
}

/* Services Grid */
.services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
}

.service-card {
    background: var(--card-bg);
    border-radius: 20px;
    overflow: hidden;
    box-shadow: 0 10px 30px rgba(0,0,0,0.08);
    transform: translateY(0);
    transition: transform 0.4s ease, box-shadow 0.4s ease;
    position: relative;
    border: 1px solid rgba(0,0,0,0.05);
}

.service-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 20px 40px rgba(0,0,0,0.15);
}

.service-image {
    width: 100%;
    height: 220px;
    object-fit: cover;
    display: block;
    background: linear-gradient(135deg, var(--accent-color), #5856D6);
}

.service-info {
    padding: 1.8rem;
}

.service-name {
    font-size: 1.5rem;
    margin-bottom: 0.8rem;
    color: var(--text-color);
    display: flex;
    align-items: center;
    gap: 10px;
}

.service-name i {
    color: var(--accent-color);
}

.service-description {
    color: var(--gray-color);
    margin-bottom: 1.5rem;
    line-height: 1.6;
}

.service-price {
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--accent-color);
    margin-bottom: 1rem;
}

.service-features {
    list-style: none;
    margin-bottom: 1.5rem;
}

.service-features li {
    margin-bottom: 0.5rem;
    display: flex;
    align-items: center;
    gap: 8px;
}

.service-features i {
    color: #34C759;
    font-size: 0.9rem;
}

.service-button {
    width: 100%;
    padding: 12px;
    background: var(--accent-color);
    color: white;
    border: none;
    border-radius: 12px;
    font-weight: 600;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 8px;
    transition: all 0.3s ease;
}

.service-button:hover {
    background: #0056CC;
    transform: translateY(-2px);
}

/* Portfolio Section */
.portfolio {
    margin-top: 5rem;
    padding: 3rem 0;
}

.portfolio h2 {
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 3rem;
    color: var(--text-color);
}

.portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1.5rem;
}

.portfolio-item {
    border-radius: 15px;
    overflow: hidden;
    box-shadow: 0 8px 25px rgba(0,0,0,0.1);
    transition: transform 0.4s ease, box-shadow 0.4s ease;
    background: var(--card-bg);
    border: 1px solid rgba(0,0,0,0.05);
}

.portfolio-item:hover {
    transform: translateY(-8px);
    box-shadow: 0 15px 35px rgba(0,0,0,0.15);
}

.portfolio-image {
    width: 100%;
    height: 250px;
    object-fit: cover;
    display: block;
    background: linear-gradient(135deg, var(--accent-color), #5856D6);
}

.portfolio-info {
    padding: 1.5rem;
}

.portfolio-title {
    font-size: 1.3rem;
    margin-bottom: 0.5rem;
    color: var(--text-color);
}

.portfolio-description {
    color: var(--gray-color);
    font-size: 1rem;
    line-height: 1.5;
}

/* Loading States */
.loading {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 200px;
    font-size: 1.2rem;
    color: var(--gray-color);
}

.spinner {
    width: 40px;
    height: 40px;
    border: 4px solid var(--accent-color);
    border-left: 4px solid transparent;
    border-radius: 50%;
    animation: spin 1s linear infinite;
    margin-right: 1rem;
}

/* Footer */
.footer {
    margin-top: 5rem;
    padding: 3rem 0;
    border-top: 1px solid var(--gray-color);
    text-align: center;
    color: var(--gray-color);
}

.contact-info {
    display: flex;
    justify-content: center;
    gap: 3rem;
    flex-wrap: wrap;
    margin: 2rem 0;
}

.contact-item {
    display: flex;
    align-items: center;
    gap: 10px;
}

/* Animations */
@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}

.fade-in {
    animation: fadeIn 0.8s ease forwards;
}

/* Responsive Design */
@media (max-width: 768px) {
    .container {
        padding: 1rem;
    }
    
    .header {
        flex-direction: column;
        gap: 1.5rem;
    }
    
    .hero h1 {
        font-size: 2.5rem;
    }
    
    .services-grid {
        grid-template-columns: 1fr;
    }
    
    .portfolio-grid {
        grid-template-columns: 1fr;
    }
    
    .features {
        flex-direction: column;
        align-items: center;
    }
    
    .contact-info {
        flex-direction: column;
        gap: 1rem;
    }
}
`;

document.head.appendChild(style);

// Данные об услугах по ремонту Apple
const appleServices = [
    {
        id: 1,
        name: "Ремонт iPhone",
        icon: "fas fa-mobile-alt",
        description: "Полный спектр услуг по ремонту iPhone любой модели. Замена экрана, аккумулятора, камеры и других компонентов.",
        price: "от 1 990 ₽",
        features: ["Диагностика бесплатно", "Оригинальные дисплеи", "Гарантия 1 год", "Ремонт за 30 минут"],
        image: "iphone-repair"
    },
    {
        id: 2,
        name: "Ремонт MacBook",
        icon: "fas fa-laptop",
        description: "Профессиональный ремонт MacBook всех поколений. Чистка, замена клавиатуры, матрицы и ремонт материнской платы.",
        price: "от 3 990 ₽",
        features: ["Бесплатная диагностика", "Оригинальные запчасти", "Срочный ремонт", "Гарантия 2 года"],
        image: "macbook-repair"
    },
    {
        id: 3,
        name: "Ремонт iPad",
        icon: "fas fa-tablet-alt",
        description: "Качественный ремонт iPad и iPad Pro. Восстановление экрана, замена батареи, ремонт после попадания влаги.",
        price: "от 2 490 ₽",
        features: ["Оригинальные стекла", "Сохранение данных", "Ремонт за 1 день", "Гарантия 1 год"],
        image: "ipad-repair"
    },
    {
        id: 4,
        name: "Ремонт Apple Watch",
        icon: "fas fa-clock",
        description: "Ремонт умных часов Apple Watch. Замена стекла, дисплея, корпуса и аккумулятора.",
        price: "от 1 790 ₽",
        features: ["Оригинальные детали", "Герметизация", "Ремонт за 2 часа", "Гарантия 6 месяцев"],
        image: "watch-repair"
    },
    {
        id: 5,
        name: "Ремонт AirPods",
        icon: "fas fa-headphones",
        description: "Восстановление работы AirPods. Замена аккумуляторов, ремонт кейсов, чистка динамиков.",
        price: "от 990 ₽",
        features: ["Оригинальные батареи", "Чистка ультразвуком", "Ремонт за 1 час", "Гарантия 3 месяца"],
        image: "airpods-repair"
    },
    {
        id: 6,
        name: "Восстановление данных",
        icon: "fas fa-hdd",
        description: "Срочное восстановление данных с любых устройств Apple после сбоев, падений и попадания жидкости.",
        price: "от 2 990 ₽",
        features: ["Бесплатный анализ", "Высокая вероятность", "Конфиденциальность", "Срочное выполнение"],
        image: "data-recovery"
    }
];

class AppleServiceApp {
    constructor() {
        this.isDarkTheme = false;
        this.init();
    }
    
    init() {
        this.createPageStructure();
        this.setupEventListeners();
        this.setupPortfolioAnimation();
        this.loadServices();
    }
    
    createPageStructure() {
        // Создаем основной контейнер
        const container = document.createElement('div');
        container.className = 'container';
        document.body.appendChild(container);
        
        // Создаем заголовок
        const header = document.createElement('header');
        header.className = 'header';
        
        const logo = document.createElement('div');
        logo.className = 'logo';
        
        const logoIcon = document.createElement('i');
        logoIcon.className = 'fab fa-apple';
        
        const logoText = document.createElement('span');
        logoText.textContent = 'Apple Service Pro';
        
        logo.appendChild(logoIcon);
        logo.appendChild(logoText);
        
        const navButtons = document.createElement('div');
        navButtons.className = 'nav-buttons';
        
        this.themeToggle = document.createElement('button');
        this.themeToggle.className = 'theme-toggle';
        this.themeToggle.id = 'themeToggle';
        
        const themeIcon = document.createElement('i');
        themeIcon.className = 'fas fa-moon';
        
        const themeText = document.createTextNode(' Тёмная тема');
        
        this.themeToggle.appendChild(themeIcon);
        this.themeToggle.appendChild(themeText);
        
        this.contactBtn = document.createElement('button');
        this.contactBtn.className = 'contact-btn';
        this.contactBtn.id = 'contactBtn';
        
        const contactIcon = document.createElement('i');
        contactIcon.className = 'fas fa-phone';
        
        const contactText = document.createTextNode(' Связаться');
        
        this.contactBtn.appendChild(contactIcon);
        this.contactBtn.appendChild(contactText);
        
        navButtons.appendChild(this.themeToggle);
        navButtons.appendChild(this.contactBtn);
        
        header.appendChild(logo);
        header.appendChild(navButtons);
        
        container.appendChild(header);
        
        // Создаем герой-секцию
        const hero = document.createElement('section');
        hero.className = 'hero';
        
        const heroTitle = document.createElement('h1');
        heroTitle.textContent = 'Профессиональный ремонт техники Apple';
        
        const heroDescription = document.createElement('p');
        heroDescription.textContent = 'Официальный сервисный центр с оригинальными запчастями и гарантией до 2 лет. Вернём ваше устройство к жизни в кратчайшие сроки!';
        
        const features = document.createElement('div');
        features.className = 'features';
        
        const feature1 = this.createFeature('fas fa-check-circle', 'Оригинальные запчасти');
        const feature2 = this.createFeature('fas fa-check-circle', 'Гарантия до 2 лет');
        const feature3 = this.createFeature('fas fa-check-circle', 'Бесплатная диагностика');
        
        features.appendChild(feature1);
        features.appendChild(feature2);
        features.appendChild(feature3);
        
        hero.appendChild(heroTitle);
        hero.appendChild(heroDescription);
        hero.appendChild(features);
        
        container.appendChild(hero);
        
        // Создаем основной контент
        const main = document.createElement('main');
        
        this.servicesGrid = document.createElement('div');
        this.servicesGrid.className = 'services-grid';
        this.servicesGrid.id = 'servicesGrid';
        
        const loading = document.createElement('div');
        loading.className = 'loading';
        
        const spinner = document.createElement('div');
        spinner.className = 'spinner';
        
        const loadingText = document.createTextNode('Загружаем услуги...');
        
        loading.appendChild(spinner);
        loading.appendChild(loadingText);
        
        this.servicesGrid.appendChild(loading);
        
        main.appendChild(this.servicesGrid);
        container.appendChild(main);
        
        // Создаем раздел портфолио
        const portfolio = document.createElement('section');
        portfolio.className = 'portfolio';
        portfolio.id = 'portfolio';
        
        const portfolioTitle = document.createElement('h2');
        portfolioTitle.textContent = 'Примеры наших работ';
        
        const portfolioGrid = document.createElement('div');
        portfolioGrid.className = 'portfolio-grid';
        
        const portfolioItems = [
            {
                icon: 'fas fa-mobile-alt',
                title: 'Замена дисплея iPhone 12 Pro',
                description: 'Полная замена OLED-дисплея с сохранением оригинального True Tone. Устройство работает как новое!'
            },
            {
                icon: 'fas fa-laptop',
                title: 'Чистка и замена термопасты MacBook Pro',
                description: 'Профилактическая чистка системы охлаждения и замена термоинтерфейса. Устранены перегревы.'
            },
            {
                icon: 'fas fa-tablet-alt',
                title: 'Восстановление iPad Air после падения',
                description: 'Замена стекла и дигитайзера с калибровкой сенсорного слоя. Экран снова идеально откликается.'
            },
            {
                icon: 'fas fa-clock',
                title: 'Ремонт Apple Watch Series 6',
                description: 'Замена аккумулятора и герметизация корпуса для сохранения водонепроницаемости.'
            },
            {
                icon: 'fas fa-keyboard',
                title: 'Замена клавиатуры MacBook Pro',
                description: 'Установка новой клавиатуры с полной калибровкой и тестированием всех клавиш.'
            },
            {
                icon: 'fas fa-hdd',
                title: 'Восстановление данных с поврежденного iPhone',
                description: 'Спасение важной информации после серьезного повреждения устройства водой.'
            }
        ];
        
        portfolioItems.forEach(item => {
            const portfolioItem = document.createElement('div');
            portfolioItem.className = 'portfolio-item fade-in';
            
            const portfolioImage = document.createElement('div');
            portfolioImage.className = 'portfolio-image';
            portfolioImage.style.display = 'flex';
            portfolioImage.style.justifyContent = 'center';
            portfolioImage.style.alignItems = 'center';
            portfolioImage.style.color = 'white';
            portfolioImage.style.fontSize = '3rem';
            
            const portfolioIcon = document.createElement('i');
            portfolioIcon.className = item.icon;
            
            portfolioImage.appendChild(portfolioIcon);
            
            const portfolioInfo = document.createElement('div');
            portfolioInfo.className = 'portfolio-info';
            
            const itemTitle = document.createElement('h3');
            itemTitle.className = 'portfolio-title';
            itemTitle.textContent = item.title;
            
            const itemDescription = document.createElement('p');
            itemDescription.className = 'portfolio-description';
            itemDescription.textContent = item.description;
            
            portfolioInfo.appendChild(itemTitle);
            portfolioInfo.appendChild(itemDescription);
            
            portfolioItem.appendChild(portfolioImage);
            portfolioItem.appendChild(portfolioInfo);
            
            portfolioGrid.appendChild(portfolioItem);
        });
        
        portfolio.appendChild(portfolioTitle);
        portfolio.appendChild(portfolioGrid);
        container.appendChild(portfolio);
        
        // Создаем футер
        const footer = document.createElement('footer');
        footer.className = 'footer';
        
        const contactInfo = document.createElement('div');
        contactInfo.className = 'contact-info';
        
        const contactItem1 = this.createContactItem('fas fa-clock', 'Пн-Вс: 9:00-21:00');
        const contactItem2 = this.createContactItem('fas fa-phone', '+7 (495) 123-45-67');
        const contactItem3 = this.createContactItem('fas fa-map-marker-alt', 'Москва, ул. Тверская, 15');
        
        contactInfo.appendChild(contactItem1);
        contactInfo.appendChild(contactItem2);
        contactInfo.appendChild(contactItem3);
        
        const copyright = document.createElement('p');
        copyright.textContent = '© 2025 Apple Service Pro. Мы не являемся официальным представителем Apple Inc.';
        
        footer.appendChild(contactInfo);
        footer.appendChild(copyright);
        
        container.appendChild(footer);
    }
    
    createFeature(iconClass, text) {
        const feature = document.createElement('div');
        feature.className = 'feature';
        
        const icon = document.createElement('i');
        icon.className = iconClass;
        
        const textSpan = document.createElement('span');
        textSpan.textContent = text;
        
        feature.appendChild(icon);
        feature.appendChild(textSpan);
        
        return feature;
    }
    
    createContactItem(iconClass, text) {
        const contactItem = document.createElement('div');
        contactItem.className = 'contact-item';
        
        const icon = document.createElement('i');
        icon.className = iconClass;
        
        const textSpan = document.createElement('span');
        textSpan.textContent = text;
        
        contactItem.appendChild(icon);
        contactItem.appendChild(textSpan);
        
        return contactItem;
    }
    
    async loadServices() {
        // Имитация загрузки для плавного появления
        setTimeout(() => {
            this.renderServices();
        }, 1500);
    }
    
    renderServices() {
        this.servicesGrid.innerHTML = '';
        
        appleServices.forEach(service => {
            const card = document.createElement('div');
            card.className = 'service-card fade-in';
            
            const serviceImage = document.createElement('div');
            serviceImage.className = 'service-image';
            serviceImage.style.background = 'linear-gradient(135deg, var(--accent-color), #5856D6)';
            serviceImage.style.display = 'flex';
            serviceImage.style.justifyContent = 'center';
            serviceImage.style.alignItems = 'center';
            serviceImage.style.color = 'white';
            serviceImage.style.fontSize = '3rem';
            
            const serviceIcon = document.createElement('i');
            serviceIcon.className = service.icon;
            
            serviceImage.appendChild(serviceIcon);
            
            const serviceInfo = document.createElement('div');
            serviceInfo.className = 'service-info';
            
            const serviceName = document.createElement('h3');
            serviceName.className = 'service-name';
            
            const nameIcon = document.createElement('i');
            nameIcon.className = service.icon;
            
            const nameText = document.createTextNode(service.name);
            
            serviceName.appendChild(nameIcon);
            serviceName.appendChild(nameText);
            
            const serviceDescription = document.createElement('p');
            serviceDescription.className = 'service-description';
            serviceDescription.textContent = service.description;
            
            const servicePrice = document.createElement('div');
            servicePrice.className = 'service-price';
            servicePrice.textContent = service.price;
            
            const serviceFeatures = document.createElement('ul');
            serviceFeatures.className = 'service-features';
            
            service.features.forEach(feature => {
                const featureItem = document.createElement('li');
                
                const featureIcon = document.createElement('i');
                featureIcon.className = 'fas fa-check';
                
                const featureText = document.createTextNode(feature);
                
                featureItem.appendChild(featureIcon);
                featureItem.appendChild(featureText);
                
                serviceFeatures.appendChild(featureItem);
            });
            
            const serviceButton = document.createElement('button');
            serviceButton.className = 'service-button';
            serviceButton.setAttribute('data-service', service.name);
            
            const buttonIcon = document.createElement('i');
            buttonIcon.className = 'fas fa-tools';
            
            const buttonText = document.createTextNode(' Заказать ремонт');
            
            serviceButton.appendChild(buttonIcon);
            serviceButton.appendChild(buttonText);
            
            serviceInfo.appendChild(serviceName);
            serviceInfo.appendChild(serviceDescription);
            serviceInfo.appendChild(servicePrice);
            serviceInfo.appendChild(serviceFeatures);
            serviceInfo.appendChild(serviceButton);
            
            card.appendChild(serviceImage);
            card.appendChild(serviceInfo);
            
            this.servicesGrid.appendChild(card);
        });
        
        // Добавляем обработчики для кнопок заказа
        this.addOrderHandlers();
        
        // Применяем анимацию появления
        this.setupServicesAnimation();
    }
    
    addOrderHandlers() {
        const orderButtons = document.querySelectorAll('.service-button');
        orderButtons.forEach(button => {
            button.addEventListener('click', () => {
                const serviceName = button.getAttribute('data-service');
                this.openOrderModal(serviceName);
            });
        });
    }
    
    setupPortfolioAnimation() {
        const portfolioItems = document.querySelectorAll('.portfolio-item');
        portfolioItems.forEach(item => {
            item.style.opacity = '0';
            item.style.transform = 'translateY(20px)';
            item.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
        });
        
        const portfolioObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    setTimeout(() => {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }, 100);
                }
            });
        }, { threshold: 0.1 });
        
        portfolioItems.forEach(item => {
            portfolioObserver.observe(item);
        });
    }
    
    setupServicesAnimation() {
        const serviceCards = document.querySelectorAll('.service-card');
        serviceCards.forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(20px)';
            card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
        });
        
        const servicesObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    setTimeout(() => {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }, 100);
                }
            });
        }, { threshold: 0.1 });
        
        serviceCards.forEach(card => {
            servicesObserver.observe(card);
        });
    }
    
    openOrderModal(serviceName) {
        alert(`Заказ на услугу: ${serviceName}\n\nПозвоните нам по номеру +7 (495) 123-45-67 или оставьте заявку на сайте.`);
    }
    
    setupEventListeners() {
        this.themeToggle.addEventListener('click', () => {
            this.toggleTheme();
        });
        
        this.contactBtn.addEventListener('click', () => {
            this.openContactModal();
        });
    }
    
    toggleTheme() {
        this.isDarkTheme = !this.isDarkTheme;
        document.body.classList.toggle('dark-theme', this.isDarkTheme);
        
        const icon = this.themeToggle.querySelector('i');
        if (this.isDarkTheme) {
            this.themeToggle.innerHTML = '<i class="fas fa-sun"></i> Светлая тема';
        } else {
            this.themeToggle.innerHTML = '<i class="fas fa-moon"></i> Тёмная тема';
        }
    }
    
    openContactModal() {
        alert("Свяжитесь с нами:\n\n📞 Телефон: +7 (495) 123-45-67\n📍 Адрес: Москва, ул. Тверская, 15\n🕒 Время работы: Пн-Вс: 9:00-21:00");
    }
}

// Инициализация при загрузке страницы
document.addEventListener('DOMContentLoaded', () => {
    new AppleServiceApp();
});
