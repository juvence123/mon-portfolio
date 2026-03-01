<!DOCTYPE html>
<html lang="fr">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>mon portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* ========== ANIMATIONS GLOBALES ========== */
        @keyframes fadeIn {
            from {
                opacity: 0;
            }

            to {
                opacity: 1;
            }
        }

        @keyframes slideInLeft {
            from {
                transform: translateX(-50px);
                opacity: 0;
            }

            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes slideInRight {
            from {
                transform: translateX(50px);
                opacity: 0;
            }

            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes slideInUp {
            from {
                transform: translateY(50px);
                opacity: 0;
            }

            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        @keyframes bounce {

            0%,
            20%,
            50%,
            80%,
            100% {
                transform: translateY(0);
            }

            40% {
                transform: translateY(-20px);
            }

            60% {
                transform: translateY(-10px);
            }
        }

        @keyframes rotate {
            from {
                transform: rotate(0deg);
            }

            to {
                transform: rotate(360deg);
            }
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
            }

            50% {
                transform: scale(1.05);
            }

            100% {
                transform: scale(1);
            }
        }

        @keyframes shimmer {
            0% {
                background-position: -1000px 0;
            }

            100% {
                background-position: 1000px 0;
            }
        }

        @keyframes float {
            0% {
                transform: translateY(0px);
            }

            50% {
                transform: translateY(-10px);
            }

            100% {
                transform: translateY(0px);
            }
        }

        @keyframes gradientShift {
            0% {
                background-position: 0% 50%;
            }

            50% {
                background-position: 100% 50%;
            }

            100% {
                background-position: 0% 50%;
            }
        }

        /* ========== STYLES DE BASE ========== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ========== ANIMATIONS DES SECTIONS ========== */
        section {
            animation: fadeIn 1s ease-out;
        }

        /* ========== HEADER ANIMÉ ========== */
        header {
            background: linear-gradient(-45deg, #667eea, #764ba2, #6b8cff, #9f7aea);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            color: white;
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.1) 0%, transparent 50%);
            animation: rotate 20s linear infinite;
        }

        .profile-img {
            width: 150px !important;
            height: 150px !important;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid white;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            animation: bounce 2s ease infinite, float 3s ease-in-out infinite;
            transition: transform 0.3s;
        }

        .profile-img:hover {
            transform: scale(1.1) rotate(5deg);
            animation: none;
        }

        header h1 {
            animation: slideInLeft 1s ease-out;
            margin: 20px 0 10px;
            font-size: 2.5em;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        header p {
            animation: slideInRight 1s ease-out;
            font-size: 1.2em;
            opacity: 0.9;
        }

        /* ========== NAVIGATION ANIMÉE ========== */
        nav {
            background: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
            animation: slideInUp 0.8s ease-out;
        }

        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
            padding: 15px 0;
        }

        nav ul li {
            margin: 0 20px;
        }

        nav ul li a {
            text-decoration: none;
            color: #333;
            font-weight: 600;
            padding: 5px 10px;
            position: relative;
            transition: color 0.3s;
        }

        nav ul li a::before {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            transition: width 0.3s ease;
        }

        nav ul li a:hover {
            color: #667eea;
        }

        nav ul li a:hover::before {
            width: 100%;
        }

        /* ========== LETTRE DE BIENVENUE ANIMÉE ========== */
        .welcome-letter {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 40px;
            border-radius: 20px;
            margin: 40px auto;
            max-width: 900px;
            box-shadow: 0 20px 40px rgba(102, 126, 234, 0.4);
            position: relative;
            overflow: hidden;
            animation: slideInUp 1.2s ease-out, pulse 3s ease-in-out infinite;
            transform-origin: center;
        }

        .welcome-letter:hover {
            animation: pulse 1.5s ease-in-out infinite;
        }

        .welcome-letter::before,
        .welcome-letter::after {
            content: '"';
            font-size: 200px;
            position: absolute;
            opacity: 0.1;
            color: white;
            font-family: serif;
            animation: float 4s ease-in-out infinite;
        }

        .welcome-letter::before {
            top: -50px;
            left: -20px;
        }

        .welcome-letter::after {
            bottom: -80px;
            right: -20px;
            transform: rotate(180deg);
            animation-delay: 2s;
        }

        .welcome-title {
            font-size: 32px;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 15px;
            border-bottom: 2px solid rgba(255, 255, 255, 0.3);
            padding-bottom: 15px;
            animation: slideInLeft 1s ease-out;
        }

        .welcome-title i {
            font-size: 40px;
            animation: rotate 10s linear infinite;
        }

        .welcome-text {
            font-size: 18px;
            line-height: 1.8;
            margin-bottom: 30px;
            animation: fadeIn 2s ease-out;
        }

        .welcome-highlight {
            background: rgba(255, 255, 255, 0.2);
            padding: 20px;
            border-radius: 15px;
            margin: 25px 0;
            font-weight: 500;
            transform: scale(1);
            transition: transform 0.3s, box-shadow 0.3s;
            animation: pulse 3s ease-in-out infinite;
        }

        .welcome-highlight:hover {
            transform: scale(1.02);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .welcome-highlight i {
            animation: bounce 2s ease infinite;
        }

        .welcome-signature {
            font-size: 22px;
            font-style: italic;
            text-align: right;
            margin-top: 25px;
            border-top: 2px solid rgba(255, 255, 255, 0.3);
            padding-top: 25px;
            animation: slideInRight 1.2s ease-out;
        }

        .welcome-signature i {
            margin-left: 10px;
            font-size: 28px;
            animation: pulse 1.5s ease-in-out infinite;
        }

        /* ========== SECTION À PROPOS ANIMÉE ========== */
        #about {
            padding: 60px 20px;
            background: #f8f9fa;
            position: relative;
            overflow: hidden;
        }

        #about h2 {
            text-align: center;
            font-size: 2.5em;
            margin-bottom: 40px;
            color: #333;
            animation: slideInLeft 1s ease-out;
        }

        .about-content {
            max-width: 800px;
            margin: 0 auto;
            padding: 30px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transform: translateY(0);
            transition: transform 0.3s, box-shadow 0.3s;
            animation: slideInUp 1.2s ease-out;
        }

        .about-content:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(102, 126, 234, 0.2);
        }

        .about-content p {
            font-size: 1.2em;
            line-height: 1.8;
            color: #555;
        }

        /* ========== COMPÉTENCES ANIMÉES ========== */
        #skills {
            padding: 60px 20px;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        }

        #skills h2 {
            text-align: center;
            font-size: 2.5em;
            margin-bottom: 40px;
            color: #333;
            animation: slideInRight 1s ease-out;
        }

        .skills-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .skill-item {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            background-size: 200% 200%;
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            font-weight: 600;
            font-size: 1.1em;
            cursor: default;
            transition: all 0.3s;
            animation: slideInUp 1s ease-out, gradientShift 5s ease infinite;
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.3);
        }

        .skill-item:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 15px 30px rgba(102, 126, 234, 0.4);
        }

        .skill-item:nth-child(1) {
            animation-delay: 0.2s;
        }

        .skill-item:nth-child(2) {
            animation-delay: 0.4s;
        }

        .skill-item:nth-child(3) {
            animation-delay: 0.6s;
        }

        /* ========== SECTION CONTACT ANIMÉE ========== */
        #contact {
            padding: 60px 20px;
            background: white;
        }

        #contact h2 {
            text-align: center;
            font-size: 2.5em;
            margin-bottom: 20px;
            color: #333;
            animation: slideInLeft 1s ease-out;
        }

        .direct-contact {
            max-width: 500px;
            margin: 30px auto;
            padding: 30px;
            background: #f8f9fa;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            animation: slideInUp 1.2s ease-out;
            transition: transform 0.3s;
        }

        .direct-contact:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(102, 126, 234, 0.2);
        }

        .contact-item {
            display: flex;
            align-items: center;
            padding: 15px 20px;
            margin: 15px 0;
            background: white;
            border-radius: 10px;
            text-decoration: none;
            color: #333;
            transition: all 0.3s;
            animation: slideInLeft 1s ease-out;
            position: relative;
            overflow: hidden;
        }

        .contact-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .contact-item:hover::before {
            left: 100%;
        }

        .contact-item:hover {
            transform: translateX(10px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .contact-item i {
            font-size: 28px;
            margin-right: 20px;
            width: 35px;
            text-align: center;
            transition: transform 0.3s;
        }

        .contact-item:hover i {
            transform: scale(1.2) rotate(10deg);
        }

        .contact-item.whatsapp i {
            color: #25D366;
        }

        .contact-item.phone i {
            color: #007bff;
        }

        .btn-whatsapp {
            background: #25D366;
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            width: 100%;
            font-size: 18px;
            margin-top: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            text-decoration: none;
            transition: all 0.3s;
            animation: pulse 2s ease-in-out infinite;
            position: relative;
            overflow: hidden;
        }

        .btn-whatsapp::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .btn-whatsapp:hover::before {
            width: 300px;
            height: 300px;
        }

        .btn-whatsapp:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(37, 211, 102, 0.4);
            animation: none;
        }

        .btn-whatsapp i {
            font-size: 24px;
            animation: bounce 2s ease infinite;
        }

        .contact-form {
            max-width: 500px;
            margin: 0 auto;
            padding: 40px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            animation: slideInUp 1.4s ease-out;
        }

        .form-group {
            margin-bottom: 20px;
            animation: slideInLeft 1s ease-out;
        }

        .form-group:nth-child(1) {
            animation-delay: 0.2s;
        }

        .form-group:nth-child(2) {
            animation-delay: 0.4s;
        }

        .form-group:nth-child(3) {
            animation-delay: 0.6s;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #eee;
            border-radius: 8px;
            transition: all 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            border-color: #667eea;
            box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
            transform: scale(1.02);
        }

        .btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            font-size: 18px;
            font-weight: 600;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .btn::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .btn:hover::after {
            width: 300px;
            height: 300px;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.4);
        }

        /* ========== FOOTER ANIMÉ ========== */
        footer {
            background: linear-gradient(135deg, #333, #222);
            color: white;
            text-align: center;
            padding: 40px 20px;
            margin-top: 60px;
            position: relative;
            overflow: hidden;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #667eea, #764ba2, #667eea);
            background-size: 200% 100%;
            animation: gradientShift 3s linear infinite;
        }

        .social-links {
            margin-bottom: 20px;
        }

        .social-links a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-size: 1.2em;
            display: inline-block;
            transition: all 0.3s;
            animation: float 3s ease-in-out infinite;
        }

        .social-links a:nth-child(1) {
            animation-delay: 0s;
        }

        .social-links a:nth-child(2) {
            animation-delay: 0.5s;
        }

        .social-links a:nth-child(3) {
            animation-delay: 1s;
        }

        .social-links a:nth-child(4) {
            animation-delay: 1.5s;
        }

        .social-links a:hover {
            transform: translateY(-5px) scale(1.2);
            color: #667eea;
        }

        .social-links i {
            margin-right: 8px;
            transition: transform 0.3s;
        }

        .social-links a:hover i {
            transform: rotate(360deg);
        }

        /* ========== TOAST DE BIENVENUE ========== */
        .welcome-toast {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 18px 30px;
            border-radius: 60px;
            box-shadow: 0 10px 40px rgba(102, 126, 234, 0.3);
            display: flex;
            align-items: center;
            gap: 15px;
            z-index: 1000;
            animation: slideInRight 0.5s ease-out, pulse 2s ease-in-out infinite;
            cursor: pointer;
            transition: all 0.3s;
        }

        .welcome-toast:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 50px rgba(102, 126, 234, 0.5);
        }

        .welcome-toast i:first-child {
            animation: bounce 2s ease infinite;
        }

        /* ========== SCROLL REVEAL ANIMATIONS ========== */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* ========== LOADER ANIMATION ========== */
        .loader-wrapper {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: white;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.5s, visibility 0.5s;
        }

        .loader-wrapper.fade-out {
            opacity: 0;
            visibility: hidden;
        }

        .loader {
            width: 50px;
            height: 50px;
            border: 5px solid #f3f3f3;
            border-top: 5px solid #667eea;
            border-radius: 50%;
            animation: rotate 1s linear infinite;
        }
    </style>
</head>

<body>
    <!-- Loader -->
    <div class="loader-wrapper" id="loader">
        <div class="loader"></div>
    </div>

    <!-- Message Toast de bienvenue -->
    <div class="welcome-toast" id="welcomeToast" onclick="this.style.display='none'">
        <i class="fas fa-hand-wave"></i>
        <span>Bienvenue sur mon portfolio ! 👋</span>
        <i class="fas fa-times" style="margin-left: 10px; font-size: 14px;"></i>
    </div>

    <header>
        <div class="container">
            <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/607659755_1463068238867849_5910067843189255172_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=9pzhD1W93rAQ7kNvwENXcF7&_nc_oc=AdkEU0jzQHf-PNEAzasd6TyAZIeNkMvEn4_sb3200L--EakwXRXTAuAJn8e-pni1zo4&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=P6ESBeg1HEvz1XSkVjgmUg&_nc_ss=8&oh=00_AfurLLBUzuaz9knwqx5Fi_WjHuWt-WosjDEdLVkcNHdDpw&oe=69A8571E"
                alt="Photo de profil" class="profile-img">
            <h1>Razanajokiny Aririvo Juvence Evans Norton</h1>
            <p>Développeur Web & Designer Créatif</p>
        </div>
    </header>

    <!-- Lettre de bienvenue -->
    <div class="container">
        <div class="welcome-letter">
            <div class="welcome-content">
                <div class="welcome-title">
                    <i class="fas fa-envelope-open-text"></i>
                    Bienvenue sur mon portfolio
                </div>

                <div class="welcome-text">
                    <p>Cher visiteur, cher futur collaborateur,</p>

                    <p>C'est avec un immense plaisir que je vous accueille sur mon portfolio personnel. Je suis
                        <strong>Razanajokiny Aririvo Juvence Evans Norton</strong>, développeur web passionné et créatif
                        basé à Madagascar.
                    </p>

                    <div class="welcome-highlight">
                        <i class="fas fa-quote-left"></i>
                        Le code est ma passion, la créativité ma motivation, et votre satisfaction ma plus grande
                        récompense.
                    </div>

                    <p>À travers ce portfolio, je souhaite vous faire découvrir mon univers, mes compétences et les
                        projets
                        qui me tiennent à cœur.</p>

                    <p>Que vous soyez ici pour :</p>
                    <ul style="list-style: none; padding-left: 0;">
                        <li><i class="fas fa-check-circle" style="color: #ffd700; margin-right: 10px;"></i>Découvrir mon
                            travail</li>
                        <li><i class="fas fa-check-circle" style="color: #ffd700; margin-right: 10px;"></i>Proposer une
                            collaboration</li>
                        <li><i class="fas fa-check-circle" style="color: #ffd700; margin-right: 10px;"></i>Ou simplement
                            par curiosité</li>
                    </ul>

                    <p>N'hésitez pas à explorer les différentes sections et à me contacter. Je serais ravi d'échanger
                        avec vous
                        et de donner vie à vos idées !</p>
                </div>

                <div class="welcome-signature">
                    Bien cordialement,
                    <br>
                    <strong>Juvence Evans Norton</strong>
                    <i class="fas fa-heart" style="color: #ffd700;"></i>
                </div>
            </div>
        </div>
    </div>

    <nav>
        <div class="container">
            <ul>
                <li><a href="#about">À propos</a></li>
                <li><a href="#skills">Compétences</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <section id="about">
        <div class="container">
            <h2>À propos de moi</h2>
            <div class="about-content">
                <p>Je suis un développeur de site web et codage. J'aime transformer des idées créatives en solutions
                    numériques fonctionnelles et esthétiques. Avec une passion pour l'innovation et le design, je
                    m'efforce
                    de créer des expériences web uniques qui marquent les esprits.</p>
            </div>
        </div>
    </section>

    <section id="skills">
        <div class="container">
            <h2>Mes Compétences</h2>
            <div class="skills-container">
                <span class="skill-item">HTML</span>
                <span class="skill-item">CSS</span>
                <span class="skill-item">JavaScript</span>
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="container">
            <h2>Contactez-moi</h2>

            <!-- Section Contact Direct (WhatsApp & Téléphone) -->
            <div class="direct-contact">
                <h3 class="contact-section-title">
                    <i class="fas fa-phone-alt"></i> Me contacter directement
                </h3>

                <!-- WhatsApp -->
                <a href="https://wa.me/261373436938" class="contact-item whatsapp" target="_blank">
                    <i class="fab fa-whatsapp"></i>
                    <div class="contact-info">
                        <div class="contact-label">WhatsApp</div>
                        <div class="contact-value">+261 37 34 369 38</div>
                    </div>
                </a>

                <!-- Téléphone -->
                <a href="tel:+261383146589" class="contact-item phone">
                    <i class="fas fa-phone"></i>
                    <div class="contact-info">
                        <div class="contact-label">Téléphone</div>
                        <div class="contact-value">+261 38 31 465 89</div>
                    </div>
                </a>

                <!-- Bouton WhatsApp rapide -->
                <a href="https://wa.me/261373436938?text=Bonjour%20Juvence%2C%20je%20vous%20contacte%20depuis%20votre%20portfolio"
                    class="btn-whatsapp" target="_blank">
                    <i class="fab fa-whatsapp"></i>
                    Envoyer un message WhatsApp
                </a>
            </div>

            <!-- Formulaire de contact existant -->
            <h3 class="contact-section-title">
                <i class="fas fa-envelope"></i> Ou par email
            </h3>
            <form class="contact-form" id="contactForm">
                <div class="form-group">
                    <label for="name">Nom</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" name="message" required></textarea>
                </div>
                <button type="submit" class="btn">Envoyer</button>
            </form>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#"><i class="fab fa-linkedin"></i> LinkedIn</a>
                <a href="#"><i class="fab fa-github"></i> GitHub</a>
                <a href="#"><i class="fab fa-twitter"></i> Twitter</a>
                <a href="https://wa.me/261373436938" target="_blank"><i class="fab fa-whatsapp"></i> WhatsApp</a>
            </div>
            <p>&copy; 2026 Razanajokiny Aririvo Juvence Evans Norton. Tous droits réservés.</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling pour les liens de navigation
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                targetElement.scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Gestion du formulaire de contact
        document.getElementById('contactForm').addEventListener('submit', function (e) {
            e.preventDefault();

            // Récupérer les valeurs du formulaire
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;

            // Créer le sujet et le corps de l'email
            const subject = encodeURIComponent(`Message de ${name} depuis votre portfolio`);
            const body = encodeURIComponent(`Nom: ${name}\nEmail: ${email}\n\nMessage:\n${message}`);

            // Ouvrir le client email par défaut
            window.location.href = `mailto:votre@email.com?subject=${subject}&body=${body}`;

            alert('Merci pour votre message ! Je vous répondrai dans les plus brefs délais.');
            this.reset();
        });

        // Ajouter un message de confirmation pour les clics sur téléphone
        const phoneLink = document.querySelector('.contact-item.phone');
        if (phoneLink) {
            phoneLink.addEventListener('click', function (e) {
                if (!confirm('Voulez-vous appeler ce numéro ?')) {
                    e.preventDefault();
                }
            });
        }

        // Disparition automatique du toast après 5 secondes
        setTimeout(() => {
            const toast = document.getElementById('welcomeToast');
            if (toast) {
                toast.style.opacity = '0';
                toast.style.transition = 'opacity 0.5s';
                setTimeout(() => {
                    toast.style.display = 'none';
                }, 500);
            }
        }, 5000);

        // Animation au scroll pour la lettre
        window.addEventListener('scroll', function () {
            const letter = document.querySelector('.welcome-letter');
            if (letter) {
                const rect = letter.getBoundingClientRect();
                if (rect.top < window.innerHeight && rect.bottom > 0) {
                    letter.style.opacity = '1';
                    letter.style.transform = 'translateY(0)';
                }
            }
        });

        // Loader
        window.addEventListener('load', function () {
            setTimeout(() => {
                document.getElementById('loader').classList.add('fade-out');
            }, 500);
        });

        // Animation au scroll (reveal)
        function reveal() {
            const reveals = document.querySelectorAll('.reveal');

            reveals.forEach(element => {
                const windowHeight = window.innerHeight;
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;

                if (elementTop < windowHeight - elementVisible) {
                    element.classList.add('active');
                }
            });
        }

        window.addEventListener('scroll', reveal);

        // Ajouter la classe reveal à certains éléments
        document.querySelectorAll('section, .welcome-letter, .direct-contact, .contact-form').forEach(el => {
            el.classList.add('reveal');
        });

        // Déclencher une fois au chargement
        reveal();
    </script>
</body>

</html>
