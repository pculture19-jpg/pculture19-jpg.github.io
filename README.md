<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PopCulture | Tu sitio de cultura pop</title>
    <style>
        /* Estilos generales y reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background-color: #fff5f7;
            color: #333;
            overflow-x: hidden;
        }
        
        /* Animaciones */
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        @keyframes shine {
            0% { background-position: -100px; }
            100% { background-position: 200px; }
        }
        
        /* Encabezado y navegación */
        header {
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: #fff;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
            animation: pulse 2s infinite;
        }
        
        .logo span {
            color: #ff5e8e;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 30px;
        }
        
        nav ul li a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
            padding: 5px 0;
        }
        
        nav ul li a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 0;
            background-color: #fff;
            transition: width 0.3s ease;
        }
        
        nav ul li a:hover:after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            height: 80vh;
            background: linear-gradient(rgba(255, 255, 255, 0.7), rgba(255, 245, 247, 0.9)), url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%23ff9a9e" opacity="0.2"/><path d="M0 0L100 100" stroke="%23ff5e8e" stroke-width="2" opacity="0.2"/><path d="M100 0L0 100" stroke="%23ff5e8e" stroke-width="2" opacity="0.2"/></svg>');
            display: flex;
            align-items: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero-content {
            width: 100%;
            animation: fadeIn 1.5s ease-out;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            color: #ff5e8e;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            color: #777;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            color: white;
            text-decoration: none;
            border-radius: 30px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 94, 142, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 94, 142, 0.4);
            animation: pulse 1s infinite;
        }
        
        /* Secciones de contenido */
        section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: #ff5e8e;
            display: inline-block;
            padding-bottom: 10px;
        }
        
        .section-title h2:after {
            content: '';
            position: absolute;
            width: 60px;
            height: 3px;
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }
        
        /* Tarjetas de categorías */
        .categories {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }
        
        .category-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            text-align: center;
            padding: 30px 20px;
            position: relative;
        }
        
        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(255, 94, 142, 0.2);
        }
        
        .category-card i {
            font-size: 3rem;
            color: #ff5e8e;
            margin-bottom: 20px;
            display: block;
        }
        
        .category-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #ff5e8e;
        }
        
        .category-card p {
            color: #777;
            margin-bottom: 20px;
        }
        
        /* Artículos destacados */
        .featured-articles {
            background: linear-gradient(to bottom, #fff5f7, #ffeef2);
            padding: 80px 0;
        }
        
        .articles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .article-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        .article-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(255, 94, 142, 0.2);
        }
        
        .article-img {
            height: 200px;
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            position: relative;
            overflow: hidden;
        }
        
        .article-img:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(255,255,255,0.3) 0%, rgba(255,255,255,0) 100%);
            animation: shine 2s infinite;
        }
        
        .article-content {
            padding: 20px;
        }
        
        .article-content h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: #ff5e8e;
        }
        
        .article-content p {
            color: #777;
            margin-bottom: 20px;
        }
        
        .read-more {
            color: #ff5e8e;
            text-decoration: none;
            font-weight: bold;
            display: inline-block;
            position: relative;
        }
        
        .read-more:after {
            content: '→';
            margin-left: 5px;
            transition: all 0.3s ease;
        }
        
        .read-more:hover:after {
            margin-left: 10px;
        }
        
        /* Newsletter */
        .newsletter {
            text-align: center;
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            padding: 80px 0;
            color: white;
        }
        
        .newsletter h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }
        
        .newsletter p {
            max-width: 600px;
            margin: 0 auto 30px;
        }
        
        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
        }
        
        .newsletter-form input {
            flex: 1;
            padding: 15px;
            border: none;
            border-radius: 30px 0 0 30px;
            outline: none;
        }
        
        .newsletter-form button {
            padding: 0 30px;
            background: #ff5e8e;
            color: white;
            border: none;
            border-radius: 0 30px 30px 0;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        
        .newsletter-form button:hover {
            background: #ff3d7d;
        }
        
        /* Footer */
        footer {
            background: #333;
            color: white;
            padding: 60px 0 30px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: #ff9a9e;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 10px;
        }
        
        .footer-column ul li a {
            color: #ddd;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .footer-column ul li a:hover {
            color: #ff9a9e;
            padding-left: 5px;
        }
        
        .social-icons {
            display: flex;
            gap: 15px;
        }
        
        .social-icons a {
            display: inline-block;
            width: 40px;
            height: 40px;
            background: #ff9a9e;
            border-radius: 50%;
            color: white;
            text-align: center;
            line-height: 40px;
            transition: all 0.3s ease;
        }
        
        .social-icons a:hover {
            transform: translateY(-5px);
            background: #ff5e8e;
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid #444;
            color: #ddd;
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
            }
            
            nav ul {
                margin-top: 20px;
            }
            
            nav ul li {
                margin: 0 10px;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .newsletter-form {
                flex-direction: column;
            }
            
            .newsletter-form input {
                border-radius: 30px;
                margin-bottom: 10px;
            }
            
            .newsletter-form button {
                border-radius: 30px;
                padding: 15px;
            }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <!-- Encabezado -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">Pop<span>Culture</span></div>
                <nav>
                    <ul>
                        <li><a href="#">Inicio</a></li>
                        <li><a href="#">Música</a></li>
                        <li><a href="#">Cine</a></li>
                        <li><a href="#">Moda</a></li>
                        <li><a href="#">Tendencias</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Explora el Mundo de la Cultura Pop</h1>
                <p>Descubre las últimas tendencias en música, cine, moda y mucho más. Mantente al día con lo que está pasando en el mundo del entretenimiento.</p>
                <a href="#" class="btn">Explorar Ahora</a>
            </div>
        </div>
    </section>

    <!-- Categorías -->
    <section class="categories-section">
        <div class="container">
            <div class="section-title">
                <h2>Nuestras Categorías</h2>
            </div>
            <div class="categories">
                <div class="category-card">
                    <i class="fas fa-music"></i>
                    <h3>Música</h3>
                    <p>Los últimos lanzamientos, conciertos y noticias del mundo de la música.</p>
                    <a href="#" class="read-more">Descubrir</a>
                </div>
                <div class="category-card">
                    <i class="fas fa-film"></i>
                    <h3>Cine & TV</h3>
                    <p>Estrenos, críticas y detrás de cámaras de tus películas y series favoritas.</p>
                    <a href="#" class="read-more">Descubrir</a>
                </div>
                <div class="category-card">
                    <i class="fas fa-tshirt"></i>
                    <h3>Moda</h3>
                    <p>Tendencias, estilo celebrity y lo último en el mundo de la moda.</p>
                    <a href="#" class="read-more">Descubrir</a>
                </div>
                <div class="category-card">
                    <i class="fas fa-star"></i>
                    <h3>Celebridades</h3>
                    <p>Todo sobre la vida de tus celebridades favoritas y lo que está pasando.</p>
                    <a href="#" class="read-more">Descubrir</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Artículos Destacados -->
    <section class="featured-articles">
        <div class="container">
            <div class="section-title">
                <h2>Artículos Destacados</h2>
            </div>
            <div class="articles-grid">
                <div class="article-card">
                    <div class="article-img"></div>
                    <div class="article-content">
                        <h3>Los mejores álbumes del año</h3>
                        <p>Repasamos los lanzamientos musicales que han definido el año y que no puedes perderte.</p>
                        <a href="#" class="read-more">Leer más</a>
                    </div>
                </div>
                <div class="article-card">
                    <div class="article-img"></div>
                    <div class="article-content">
                        <h3>Tendencias de moda primavera-verano</h3>
                        <p>Descubre qué se llevará esta temporada y cómo incorporarlo a tu armario.</p>
                        <a href="#" class="read-more">Leer más</a>
                    </div>
                </div>
                <div class="article-card">
                    <div class="article-img"></div>
                    <div class="article-content">
                        <h3>Las series que arrasan en streaming</h3>
                        <p>Un análisis de las producciones que están conquistando las plataformas digitales.</p>
                        <a href="#" class="read-more">Leer más</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="newsletter">
        <div class="container">
            <h2>Mantente Actualizado</h2>
            <p>Suscríbete a nuestro newsletter para recibir las últimas noticias y tendencias de cultura pop directamente en tu correo.</p>
            <form class="newsletter-form">
                <input type="email" placeholder="Tu correo electrónico" required>
                <button type="submit">Suscribirse</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>PopCulture</h3>
                    <p>Tu destino para todo sobre cultura pop, tendencias y entretenimiento.</p>
                    <div class="social-icons">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-pinterest-p"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Secciones</h3>
                    <ul>
                        <li><a href="#">Música</a></li>
                        <li><a href="#">Cine & TV</a></li>
                        <li><a href="#">Moda</a></li>
                        <li><a href="#">Celebridades</a></li>
                        <li><a href="#">Tendencias</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Enlaces útiles</h3>
                    <ul>
                        <li><a href="#">Sobre nosotros</a></li>
                        <li><a href="#">Contacto</a></li>
                        <li><a href="#">Política de privacidad</a></li>
                        <li><a href="#">Términos y condiciones</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 PopCulture. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>
</body>
</html>
