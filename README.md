<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=deviceلجهاز, initial-scale=1.0">
    <title>معرض أعمالي | Portfolio</title>
    <!-- خطوط جوجل العربية -->
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700&display=swap" rel="stylesheet">
    <!-- مكتبة الأيقونات FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #4f46e5;
            --secondary-color: #818cf8;
            --bg-color: #0f172a;
            --card-bg: #1e293b;
            --text-color: #f8fafc;
            --text-muted: #94a3b8;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Cairo', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        /* شريط التنقل */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: rgba(15, 23, 42, 0.9);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 8%;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--text-color);
            text-decoration: none;
        }

        .logo span {
            color: var(--primary-color);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav ul li a {
            text-decoration: none;
            color: var(--text-muted);
            font-weight: 600;
            transition: var(--transition);
        }

        nav ul li a:hover, nav ul li a.active {
            color: var(--primary-color);
        }

        /* القسم الرئيسي (Hero Section) */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 8%;
            padding-top: 80px;
            gap: 40px;
        }

        .hero-content h1 {
            font-size: 3rem;
            margin-bottom: 15px;
        }

        .hero-content h1 span {
            color: var(--primary-color);
        }

        .hero-content p {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 30px;
            max-width: 600px;
        }

        .btn {
            display: inline-block;
            background: var(--primary-color);
            color: white;
            padding: 12px 30px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            box-shadow: 0 4px 14px rgba(79, 70, 229, 0.4);
        }

        .btn:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
        }

        .hero-img img {
            width: 320px;
            height: 320px;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid var(--primary-color);
            box-shadow: 0 0 30px rgba(79, 70, 229, 0.3);
        }

        /* أقسام الموقع العامة */
        section {
            padding: 100px 8%;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background: var(--primary-color);
            border-radius: 2px;
        }

        /* قسم المهارات */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 25px;
        }

        .skill-card {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 12px;
            text-align: center;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .skill-card:hover {
            transform: translateY(-5px);
            border-color: var(--primary-color);
        }

        .skill-card i {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 15px;
        }

        .skill-card h3 {
            font-size: 1.2rem;
        }

        /* قسم الأعمال (Projects) */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        .project-img {
            height: 180px;
            background: #334155;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-muted);
            font-size: 1.2rem;
        }

        .project-info {
            padding: 25px;
        }

        .project-info h3 {
            margin-bottom: 10px;
            font-size: 1.4rem;
        }

        .project-info p {
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-bottom: 20px;
        }

        .project-links a {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 5px;
        }

        .project-links a:hover {
            text-decoration: underline;
        }

        /* قسم التواصل (Contact) */
        .contact-form {
            max-width: 700px;
            margin: 0 auto;
            background: var(--card-bg);
            padding: 40px;
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 12px;
            background: var(--bg-color);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            color: white;
            font-size: 1rem;
            outline: none;
            transition: var(--transition);
        }

        .form-group input:focus, .form-group textarea:focus {
            border-color: var(--primary-color);
        }

        .form-group textarea {
            height: 150px;
            resize: vertical;
        }

        /* الفوتر */
        footer {
            text-align: center;
            padding: 30px;
            background: rgba(15, 23, 42, 0.95);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--text-muted);
        }

        /* تجاوب الشاشات الصغيرة */
        @media (max-width: 768px) {
            .hero {
                flex-direction: column-reverse;
                text-align: center;
                padding-top: 120px;
            }
            .hero-content p {
                margin: 0 auto 30px auto;
            }
            nav ul {
                display: none; /* يمكن تطوير قائمة الجوال لاحقاً */
            }
        }
    </style>
</head>
<body>

    <!-- شريط التنقل العلوي -->
    <header>
        <a href="#" class="logo">معرض<span>أعمالي</span></a>
        <nav>
            <ul>
                <li><a href="#home" class="active">الرئيسية</a></li>
                <li><a href="#skills">المهارات</a></li>
                <li><a href="#projects">المشاريع</a></li>
                <li><a href="#contact">اتصل بي</a></li>
            </ul>
        </nav>
    </header>

    <!-- القسم الرئيسي -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>مرحباً، أنا <span>اسمك هنا</span></h1>
            <p>مطور ومبرمج ومصمم واجهات وبطاقات تفاعلية. أساعد الشركات والأفراد على تحويل أفكارهم الإبداعية إلى مواقع ويب احترافية وعصرية.</p>
            <a href="#projects" class="btn">استعرض أعمالي</a>
        </div>
        <div class="hero-img">
            <!-- يمكنك وضع رابط صورتك الشخصية هنا -->
            <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=500&auto=format&fit=crop&q=60" alt="صورة شخصية">
        </div>
    </section>

    <!-- قسم المهارات -->
    <section id="skills">
        <h2 class="section-title">مهاراتي التقنية</h2>
        <div class="skills-grid">
            <div class="skill-card">
                <i class="fab fa-html5"></i>
                <h3>HTML5</h3>
            </div>
            <div class="skill-card">
                <i class="fab fa-css3-alt"></i>
                <h3>CSS3</h3>
            </div>
            <div class="skill-card">
                <i class="fab fa-js"></i>
                <h3>JavaScript</h3>
            </div>
            <div class="skill-card">
                <i class="fab fa-git-alt"></i>
                <h3>Git & GitHub</h3>
            </div>
        </div>
    </section>

    <!-- قسم المشاريع -->
    <section id="projects">
        <h2 class="section-title">مشاريعي المميزة</h2>
        <div class="projects-grid">
            <!-- المشروع الأول -->
            <div class="project-card">
                <div class="project-img">معاينة المشروع 1</div>
                <div class="project-info">
                    <h3>متجر إلكتروني تفاعلي</h3>
                    <p>تطوير واجهة متجر إلكتروني متكاملة تدعم التصفح السلس وعربة التسوق باستخدام تقنيات الويب الحديثة.</p>
                    <div class="project-links">
                        <a href="#" target="_blank"><i class="fas fa-external-link-alt"></i> عرض المشروع</a>
                    </div>
                </div>
            </div>

            <!-- المشروع الثاني -->
            <div class="project-card">
                <div class="project-img">معاينة المشروع 2</div>
                <div class="project-info">
                    <h3>تطبيق الطقس الذكي</h3>
                    <p>تطبيق ويب لجلب درجات الحرارة وحالة الطقس الفورية لمختلف مدن العالم باستخدام جافاسكريبت و APIS.</p>
                    <div class="project-links">
                        <a href="#" target="_blank"><i class="fas fa-external-link-alt"></i> عرض المشروع</a>
                    </div>
                </div>
            </div>

            <!-- المشروع الثالث -->
            <div class="project-card">
                <div class="project-img">معاينة المشروع 3</div>
                <div class="project-info">
                    <h3>لوحة تحكم إدارية</h3>
                    <p>تصميم وتطوير لوحة تحكم عصرية متجاوبة بالكامل مع مختلف الشاشات وتحتوي على رسوم بيانية.</p>
                    <div class="project-links">
                        <a href="#" target="_blank"><i class="fas fa-external-link-alt"></i> عرض المشروع</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- قسم التواصل -->
    <section id="contact">
        <h2 class="section-title">تواصل معي</h2>
        <div class="contact-form">
            <form id="contactForm">
                <div class="form-group">
                    <label for="name">الاسم الكريم</label>
                    <input type="text" id="name" required placeholder="أدخل اسمك هنا">
                </div>
                <div class="form-group">
                    <label for="email">البريد الإلكتروني</label>
                    <input type="email" id="email" required placeholder="example@domain.com">
                </div>
                <div class="form-group">
                    <label for="message">الرسالة</label>
                    <textarea id="message" required placeholder="اكتب رسالتك هنا..."></textarea>
                </div>
                <button type="submit" class="btn" style="width: 100%;">إرسال الرسالة</button>
            </form>
        </div>
    </section>

    <!-- الفوتر -->
    <footer>
        <p>جميع الحقوق محفوظة &copy; 2026 | تم الإنشاء والتطوير بواسطة GitHub Pages</p>
    </footer>

    <!-- سكربت تفاعلي بسيط -->
    <script>
        // تفاعل نموذج الاتصال
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('شكراً لتواصلك معي! تم إرسال رسالتك بنجاح.');
            this.reset();
        });

        // تمييز الروابط النشطة عند التمرير
        const sections = document.querySelectorAll('section');
        const navLinks = document.querySelectorAll('nav ul li a');

        window.addEventListener('scroll', () => {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                if (pageYOffset >= sectionTop - 150) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').includes(current)) {
                    link.classList.add('active');
                }
            });
        });
    </script>
</body>
</html>
