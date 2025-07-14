# Barq-Sat
Network internet 
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>شبكة Barq-Sat الفضائية - كروت الإنترنت</title>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Arabic:wght@300;400;500;600;700&family=Roboto:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Noto Sans Arabic', 'Roboto', sans-serif;
            font-size: 12px;
            line-height: 1.6;
            color: #ffffff;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            min-height: 100vh;
            position: relative;
            overflow-x: hidden;
        }

        .background-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(circle at 20% 80%, rgba(0, 150, 200, 0.4) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255, 165, 0, 0.2) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(0, 212, 255, 0.15) 0%, transparent 50%);
            z-index: -2;
        }

        .aljazeera-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url('./aljazeera-studio.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            opacity: 0.15;
            z-index: -1;
            animation: backgroundPulse 8s ease-in-out infinite;
        }

        @keyframes backgroundPulse {
            0%, 100% { 
                opacity: 0.15;
                transform: scale(1);
            }
            50% { 
                opacity: 0.25;
                transform: scale(1.02);
            }
        }

        .news-ticker {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 40px;
            background: linear-gradient(90deg, rgba(255, 165, 0, 0.9), rgba(0, 150, 200, 0.9));
            display: flex;
            align-items: center;
            z-index: 10;
            overflow: hidden;
        }

        .ticker-content {
            white-space: nowrap;
            animation: scroll 30s linear infinite;
            font-size: 14px;
            font-weight: 600;
            color: white;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.8);
        }

        @keyframes scroll {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
            margin-bottom: 50px;
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
            padding: 30px 0;
            background: rgba(255, 255, 255, 0.08);
            border-radius: 20px;
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 165, 0, 0.1), transparent);
            animation: headerShine 4s ease-in-out infinite;
        }

        @keyframes headerShine {
            0%, 100% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            50% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        .logo {
            font-size: 36px;
            font-weight: 700;
            color: #ff9500;
            margin-bottom: 10px;
            text-shadow: 0 0 20px rgba(255, 149, 0, 0.6);
            animation: logoGlow 3s ease-in-out infinite alternate;
            position: relative;
            z-index: 2;
        }

        @keyframes logoGlow {
            from { 
                text-shadow: 0 0 20px rgba(255, 149, 0, 0.6);
                color: #ff9500;
            }
            to { 
                text-shadow: 0 0 30px rgba(255, 149, 0, 0.9), 0 0 40px rgba(255, 149, 0, 0.4);
                color: #ffb347;
            }
        }

        .subtitle {
            font-size: 18px;
            color: #e0e0e0;
            margin-bottom: 20px;
            position: relative;
            z-index: 2;
        }

        .main-content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 30px;
            margin-bottom: 40px;
        }

        .pricing-section {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 30px;
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
            position: relative;
            overflow: hidden;
        }

        .pricing-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 150, 200, 0.1), transparent);
            animation: sectionSweep 6s ease-in-out infinite;
        }

        @keyframes sectionSweep {
            0%, 100% { left: -100%; }
            50% { left: 100%; }
        }

        .section-title {
            font-size: 24px;
            font-weight: 600;
            color: #ff9500;
            margin-bottom: 20px;
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(90deg, #ff9500, #0096c8);
            border-radius: 2px;
            animation: underlineGlow 2s ease-in-out infinite alternate;
        }

        @keyframes underlineGlow {
            from { box-shadow: 0 0 5px rgba(255, 149, 0, 0.5); }
            to { box-shadow: 0 0 15px rgba(255, 149, 0, 0.8); }
        }

        .pricing-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
            position: relative;
            z-index: 2;
        }

        .pricing-table th {
            background: linear-gradient(135deg, #ff9500, #0096c8);
            color: white;
            padding: 15px 10px;
            font-weight: 600;
            font-size: 14px;
            text-align: center;
            border-bottom: 2px solid rgba(255, 255, 255, 0.3);
            position: relative;
        }

        .pricing-table th::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            animation: headerShimmer 3s ease-in-out infinite;
        }

        @keyframes headerShimmer {
            0%, 100% { transform: translateX(-100%); }
            50% { transform: translateX(100%); }
        }

        .pricing-table td {
            padding: 12px 10px;
            text-align: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 12px;
            transition: all 0.3s ease;
            position: relative;
        }

        .pricing-table tr:hover td {
            background: rgba(255, 149, 0, 0.15);
            transform: scale(1.01);
            box-shadow: 0 4px 15px rgba(255, 149, 0, 0.2);
        }

        .pricing-table tr:nth-child(even) td {
            background: rgba(255, 255, 255, 0.03);
        }

        .price-cell {
            font-weight: 600;
            color: #00ff88;
            font-size: 14px;
            text-shadow: 0 0 10px rgba(0, 255, 136, 0.5);
        }

        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .info-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 25px;
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .info-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 149, 0, 0.1) 0%, transparent 70%);
            animation: cardPulse 4s ease-in-out infinite;
            opacity: 0;
        }

        .info-card:hover::before {
            opacity: 1;
        }

        @keyframes cardPulse {
            0%, 100% { transform: scale(0.8) rotate(0deg); }
            50% { transform: scale(1.2) rotate(180deg); }
        }

        .info-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 50px rgba(255, 149, 0, 0.3);
            border-color: rgba(255, 149, 0, 0.5);
        }

        .card-title {
            font-size: 18px;
            font-weight: 600;
            color: #ff9500;
            margin-bottom: 15px;
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .location-item, .contact-item {
            padding: 8px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 12px;
            display: flex;
            align-items: center;
            gap: 10px;
            position: relative;
            z-index: 2;
            transition: all 0.3s ease;
        }

        .location-item:hover, .contact-item:hover {
            padding-left: 10px;
            color: #ff9500;
        }

        .location-item:last-child, .contact-item:last-child {
            border-bottom: none;
        }

        .icon {
            width: 16px;
            height: 16px;
            background: linear-gradient(45deg, #ff9500, #0096c8);
            border-radius: 50%;
            flex-shrink: 0;
            animation: iconPulse 2s ease-in-out infinite;
        }

        @keyframes iconPulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }

        .contact-number {
            color: #00ff88;
            font-weight: 600;
            direction: ltr;
            text-align: left;
            text-shadow: 0 0 8px rgba(0, 255, 136, 0.4);
        }

        .footer {
            text-align: center;
            padding: 20px;
            background: rgba(0, 0, 0, 0.4);
            border-radius: 15px;
            margin-top: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            z-index: 2;
        }

        .footer-text {
            font-size: 11px;
            color: #aaa;
            margin-bottom: 10px;
        }

        .aljazeera-logo {
            position: absolute;
            top: 20px;
            left: 20px;
            width: 60px;
            height: 40px;
            background-image: url('./aljazeera-broadcast.jpg');
            background-size: contain;
            background-repeat: no-repeat;
            background-position: center;
            opacity: 0.8;
            border-radius: 8px;
            animation: logoFloat 4s ease-in-out infinite;
            z-index: 5;
        }

        @keyframes logoFloat {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-15px) rotate(2deg); }
        }

        .broadcast-elements {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .broadcast-dot {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #ff9500;
            border-radius: 50%;
            animation: broadcastFloat 6s ease-in-out infinite;
        }

        @keyframes broadcastFloat {
            0%, 100% { 
                opacity: 0.3;
                transform: translateY(0px);
            }
            50% { 
                opacity: 1;
                transform: translateY(-20px);
            }
        }

        @media (max-width: 768px) {
            .container {
                padding: 15px;
                margin-bottom: 60px;
            }
            
            .logo {
                font-size: 28px;
            }
            
            .subtitle {
                font-size: 16px;
            }
            
            .pricing-table th,
            .pricing-table td {
                padding: 8px 5px;
                font-size: 11px;
            }
            
            .info-grid {
                grid-template-columns: 1fr;
            }
            
            .aljazeera-background {
                background-attachment: scroll;
            }

            .ticker-content {
                font-size: 12px;
            }
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -3;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.2; }
            50% { opacity: 1; }
        }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>
    <div class="background-overlay"></div>
    <div class="aljazeera-background"></div>
    <div class="broadcast-elements" id="broadcastElements"></div>
    <div class="aljazeera-logo"></div>

    <div class="news-ticker">
        <div class="ticker-content">
            🔴 أخبار عاجلة: شبكة Barq-Sat تقدم أفضل خدمات الإنترنت الفضائي • باقات متنوعة تناسب جميع الاحتياجات • تغطية شاملة وسرعة عالية • اتصل الآن للحصول على أفضل العروض
        </div>
    </div>

    <div class="container">
        <header class="header">
            <h1 class="logo">شبكة Barq-Sat الفضائية</h1>
            <p class="subtitle">كروت الإنترنت عالية السرعة - تغطية فضائية شاملة</p>
        </header>

        <main class="main-content">
            <section class="pricing-section">
                <h2 class="section-title">باقات كروت الإنترنت</h2>
                <table class="pricing-table">
                    <thead>
                        <tr>
                            <th>السعر</th>
                            <th>الوقت</th>
                            <th>الحجم</th>
                            <th>الصلاحية</th>
                            <th>المستخدمين</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="price-cell">100</td>
                            <td>8 ساعات</td>
                            <td>600 ميجا</td>
                            <td>1 يوم</td>
                            <td>1</td>
                        </tr>
                        <tr>
                            <td class="price-cell">300</td>
                            <td>72 ساعة</td>
                            <td>2000 ميجا</td>
                            <td>3 أيام</td>
                            <td>1</td>
                        </tr>
                        <tr>
                            <td class="price-cell">500</td>
                            <td>5 أيام</td>
                            <td>6 جيجا</td>
                            <td>5 أيام</td>
                            <td>2</td>
                        </tr>
                        <tr>
                            <td class="price-cell">1000</td>
                            <td>أسبوع</td>
                            <td>8 جيجا</td>
                            <td>أسبوع</td>
                            <td>5</td>
                        </tr>
                        <tr>
                            <td class="price-cell">1500</td>
                            <td>15 يوم</td>
                            <td>15 جيجا</td>
                            <td>نصف شهر</td>
                            <td>3</td>
                        </tr>
                        <tr>
                            <td class="price-cell">2000</td>
                            <td>باقة مفتوحة</td>
                            <td>20 جيجا</td>
                            <td>شهر</td>
                            <td>5</td>
                        </tr>
                        <tr>
                            <td class="price-cell">3500</td>
                            <td>باقة مفتوحة</td>
                            <td>35 جيجا</td>
                            <td>شهر</td>
                            <td>7</td>
                        </tr>
                        <tr>
                            <td class="price-cell">5000</td>
                            <td>باقة مفتوحة</td>
                            <td>45 جيجا</td>
                            <td>شهر</td>
                            <td>12</td>
                        </tr>
                    </tbody>
                </table>
            </section>

            <div class="info-grid">
                <div class="info-card">
                    <h3 class="card-title">نقاط البيع</h3>
                    <div class="location-item">
                        <div class="icon"></div>
                        <span>بقالة المريسي - بحيرة</span>
                    </div>
                    <div class="location-item">
                        <div class="icon"></div>
                        <span>بقالة الشرعبي - دوار بحيرة</span>
                    </div>
                    <div class="location-item">
                        <div class="icon"></div>
                        <span>بقالة شكري - بارفعة</span>
                    </div>
                    <div class="location-item">
                        <div class="icon"></div>
                        <span>سوبر ماركت الأسرة - المسيلة</span>
                    </div>
                    <div class="location-item">
                        <div class="icon"></div>
                        <span>ميني ماركت محطة شبام - المحطة الحكومية</span>
                    </div>
                </div>

                <div class="info-card">
                    <h3 class="card-title">أرقام التواصل</h3>
                    <div class="contact-item">
                        <div class="icon"></div>
                        <div>
                            <div>للتواصل والاستفسار (واتساب):</div>
                            <div class="contact-number">774713211</div>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="icon"></div>
                        <div>
                            <div>الاشتراك الشهري للعائلة (واتساب):</div>
                            <div class="contact-number">772692525</div>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="icon"></div>
                        <div>
                            <div>الشكاوى والاقتراحات:</div>
                            <div class="contact-number">738866236</div>
                        </div>
                    </div>
                </div>
            </div>
        </main>

        <footer class="footer">
            <p class="footer-text">شبكة Barq-Sat الفضائية - تقنية متقدمة لخدمة الإنترنت</p>
            <p class="footer-text">جميع الحقوق محفوظة © 2025</p>
        </footer>
    </div>

    <script>
        // إنشاء النجوم المتحركة
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const numberOfStars = 80;

            for (let i = 0; i < numberOfStars; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 3 + 's';
                star.style.animationDuration = (Math.random() * 4 + 2) + 's';
                starsContainer.appendChild(star);
            }
        }

        // إنشاء عناصر البث المتحركة
        function createBroadcastElements() {
            const container = document.getElementById('broadcastElements');
            const numberOfDots = 15;

            for (let i = 0; i < numberOfDots; i++) {
                const dot = document.createElement('div');
                dot.className = 'broadcast-dot';
                dot.style.left = Math.random() * 100 + '%';
                dot.style.top = Math.random() * 100 + '%';
                dot.style.animationDelay = Math.random() * 6 + 's';
                dot.style.animationDuration = (Math.random() * 8 + 4) + 's';
                container.appendChild(dot);
            }
        }

        // تأثيرات تفاعلية للجدول
        document.addEventListener('DOMContentLoaded', function() {
            createStars();
            createBroadcastElements();
            
            const tableRows = document.querySelectorAll('.pricing-table tbody tr');
            tableRows.forEach((row, index) => {
                row.addEventListener('mouseenter', function() {
                    this.style.transform = 'scale(1.02) translateZ(10px)';
                    this.style.transition = 'all 0.3s ease';
                    this.style.zIndex = '10';
                });
                
                row.addEventListener('mouseleave', function() {
                    this.style.transform = 'scale(1) translateZ(0px)';
                    this.style.zIndex = '1';
                });

                // تأثير تدرجي للظهور
                row.style.opacity = '0';
                row.style.transform = 'translateY(20px)';
                setTimeout(() => {
                    row.style.transition = 'all 0.5s ease';
                    row.style.opacity = '1';
                    row.style.transform = 'translateY(0)';
                }, index * 100);
            });

            // تأثير التمرير السلس للكروت
            const cards = document.querySelectorAll('.info-card');
            cards.forEach((card, index) => {
                card.addEventListener('mouseenter', function() {
                    this.style.background = 'rgba(255, 255, 255, 0.15)';
                    this.style.borderColor = 'rgba(255, 149, 0, 0.6)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.background = 'rgba(255, 255, 255, 0.1)';
                    this.style.borderColor = 'rgba(255, 255, 255, 0.2)';
                });

                // تأثير تدرجي للظهور
                card.style.opacity = '0';
                card.style.transform = 'translateY(30px)';
                setTimeout(() => {
                    card.style.transition = 'all 0.6s ease';
                    card.style.opacity = '1';
                    card.style.transform = 'translateY(0)';
                }, 500 + index * 200);
            });

            // تأثير الشريط الإخباري
            const ticker = document.querySelector('.ticker-content');
            ticker.addEventListener('mouseenter', function() {
                this.style.animationPlayState = 'paused';
            });
            
            ticker.addEventListener('mouseleave', function() {
                this.style.animationPlayState = 'running';
            });
        });

        // تأثير المتابعة للماوس
        document.addEventListener('mousemove', function(e) {
            const dots = document.querySelectorAll('.broadcast-dot');
            const mouseX = e.clientX / window.innerWidth;
            const mouseY = e.clientY / window.innerHeight;
            
            dots.forEach((dot, index) => {
                const speed = (index % 3 + 1) * 0.5;
                const x = mouseX * speed * 10;
                const y = mouseY * speed * 10;
                
              dot.style.transform = `translate(${x}px, ${y}px)`;
            });
        });
    </script>
</body>
</html>

