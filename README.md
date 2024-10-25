<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موقعي الاحترافي</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css" />
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f8ff;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
        }
        header {
            background-color: #008CBA;
            color: white;
            padding: 20px;
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        h1 {
            font-size: 36px;
        }
        nav {
            margin: 20px 0;
        }
        nav a {
            margin: 0 15px;
            color: white;
            text-decoration: none;
            font-size: 20px;
            transition: color 0.3s;
        }
        nav a:hover {
            color: #ffcc00;
        }
        section {
            margin: 20px;
            padding: 20px;
            border: 2px solid #008CBA;
            border-radius: 5px;
            background-color: #ffffff;
            opacity: 0; /* لجعل القسم غير مرئي قبل الأنيميشن */
            transform: translateY(50px); /* للنقل لأسفل قليلاً */
            transition: opacity 0.5s, transform 0.5s; /* تأثير الانتقال */
        }
        img {
            max-width: 100%;
            height: auto;
            border-radius: 10px;
        }
        footer {
            margin-top: 20px;
            padding: 10px;
            background-color: #008CBA;
            color: white;
            position: relative;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>مرحبًا بكم في موقعي الاحترافي</h1>
        <nav>
            <a href="#about">حول</a>
            <a href="#services">خدماتنا</a>
            <a href="#contact">تواصل معنا</a>
        </nav>
    </header>
    
    <section id="about" class="animate__animated">
        <h2 class="animate__fadeInDown">حول الموقع</h2>
        <p class="animate__fadeIn">هذا موقع احترافي مصمم لعرض الخدمات والمعلومات بشكل جذاب.</p>
        <img src="https://via.placeholder.com/800x400" alt="صورة تمثيلية">
    </section>

    <section id="services" class="animate__animated">
        <h2 class="animate__fadeInDown">خدماتنا</h2>
        <p class="animate__fadeIn">نقدم مجموعة متنوعة من الخدمات لتلبية احتياجاتك.</p>
        <img src="https://via.placeholder.com/800x400" alt="خدماتنا">
    </section>

    <footer>
        <p>&copy; 2024 موقعي الاحترافي. جميع الحقوق محفوظة.</p>
    </footer>

    <script>
        // وظيفة لتشغيل الأنيميشن عند التمرير
        const sections = document.querySelectorAll('section');
        
        const showSection = (entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = 1; // جعل القسم مرئيًا
                    entry.target.style.transform = 'translateY(0)'; // إعادة تعيين النقل
                    entry.target.classList.add('animate__fadeInUp'); // إضافة تأثير الأنيميشن
                }
            });
        };

        const observer = new IntersectionObserver(showSection, {
            threshold: 0.1 // عندما يظهر 10% من القسم
        });

        sections.forEach(section => {
            observer.observe(section); // مراقبة كل قسم
        });
    </script>
</body>
</html>
