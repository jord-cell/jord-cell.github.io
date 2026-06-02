
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SUPER - Pistolet à Eau Électrique</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #0066ff;
            --secondary: #00d4ff;
            --accent: #ff6b1a;
            --dark: #0a1428;
            --darker: #050a14;
            --light: #f0f4ff;
            --text-dark: #ffffff;
            --text-light: #b0c4ff;
        }

        body {
            background: linear-gradient(135deg, var(--dark) 0%, var(--darker) 100%);
            color: var(--text-dark);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow-x: hidden;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            position: relative;
            z-index: 10;
        }

        .logo {
            font-size: 2rem;
            font-weight: 900;
            background: linear-gradient(135deg, var(--secondary), var(--primary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: 3px;
            text-transform: uppercase;
        }

        nav a {
            color: var(--text-light);
            text-decoration: none;
            margin: 0 25px;
            transition: all 0.3s ease;
            position: relative;
            font-weight: 500;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            transition: width 0.3s ease;
        }

        nav a:hover::after {
            width: 100%;
        }

        .hero {
            display: grid;
            grid-template-columns: 1fr 1fr;
            align-items: center;
            gap: 60px;
            padding: 80px 0 100px;
            min-height: 100vh;
            position: relative;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(0, 212, 255, 0.15) 0%, transparent 70%);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
            z-index: -1;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(30px); }
        }

        .hero-content h1 {
            font-size: 4.5rem;
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 30px;
            animation: slideInLeft 0.8s ease-out;
            text-transform: uppercase;
            letter-spacing: -2px;
        }

        .hero-content h1 span {
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero-content p {
            font-size: 1.3rem;
            color: var(--text-light);
            margin-bottom: 40px;
            animation: slideInLeft 0.8s ease-out 0.1s backwards;
            max-width: 500px;
        }

        .cta-button {
            display: inline-block;
            padding: 16px 45px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: var(--dark);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 15px 40px rgba(0, 102, 255, 0.4);
            cursor: pointer;
            border: none;
            animation: slideInLeft 0.8s ease-out 0.2s backwards;
        }

        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 60px rgba(0, 102, 255, 0.6);
        }

        .hero-image {
            position: relative;
            animation: slideInRight 0.8s ease-out;
        }

        .hero-image img {
            width: 100%;
            filter: drop-shadow(0 30px 60px rgba(0, 212, 255, 0.3));
            animation: bounce 3s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 40px;
            margin-top: 60px;
            animation: fadeIn 0.8s ease-out 0.4s backwards;
        }

        .stat {
            text-align: left;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 900;
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-label {
            color: var(--text-light);
            margin-top: 10px;
            font-size: 0.95rem;
        }

        .features {
            padding: 120px 0;
            background: linear-gradient(180deg, transparent 0%, rgba(0, 102, 255, 0.05) 50%, transparent 100%);
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            font-weight: 900;
            margin-bottom: 80px;
            text-transform: uppercase;
            letter-spacing: -1px;
        }

        .section-title span {
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 40px;
        }

        .feature-card {
            background: rgba(0, 102, 255, 0.08);
            border: 1px solid rgba(0, 212, 255, 0.2);
            padding: 40px;
            border-radius: 15px;
            transition: all 0.4s ease;
            animation: fadeInUp 0.8s ease-out;
        }

        .feature-card:nth-child(1) { animation-delay: 0.1s; }
        .feature-card:nth-child(2) { animation-delay: 0.2s; }
        .feature-card:nth-child(3) { animation-delay: 0.3s; }

        .feature-card:hover {
            background: rgba(0, 102, 255, 0.15);
            border-color: var(--secondary);
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(0, 212, 255, 0.2);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .feature-card p {
            color: var(--text-light);
            line-height: 1.8;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .products {
            padding: 120px 0;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 50px;
        }

        .product-card {
            background: rgba(0, 102, 255, 0.08);
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 15px;
            padding: 40px;
            text-align: center;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .product-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 212, 255, 0.1) 0%, transparent 70%);
            transition: all 0.4s ease;
        }

        .product-card:hover {
            transform: translateY(-15px);
            border-color: var(--secondary);
            background: rgba(0, 102, 255, 0.15);
            box-shadow: 0 30px 60px rgba(0, 212, 255, 0.3);
        }

        .product-card:hover::before {
            top: -25%;
            right: -25%;
        }

        .product-image {
            width: 100%;
            height: 300px;
            margin-bottom: 30px;
            position: relative;
            z-index: 1;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: contain;
            filter: drop-shadow(0 20px 40px rgba(0, 212, 255, 0.2));
        }

        .product-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .product-specs {
            list-style: none;
            margin: 25px 0;
            text-align: left;
            color: var(--text-light);
        }

        .product-specs li {
            padding: 8px 0;
            border-bottom: 1px solid rgba(0, 212, 255, 0.1);
        }

        .product-specs li::before {
            content: '✓ ';
            color: var(--secondary);
            font-weight: bold;
            margin-right: 10px;
        }

        .buy-now {
            display: inline-block;
            padding: 12px 35px;
            background: linear-gradient(135deg, var(--secondary), var(--primary));
            color: var(--dark);
            text-decoration: none;
            border-radius: 30px;
            font-weight: 700;
            margin-top: 20px;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
        }

        .buy-now:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(0, 212, 255, 0.4);
        }

        footer {
            background: rgba(0, 0, 0, 0.5);
            border-top: 1px solid rgba(0, 212, 255, 0.1);
            padding: 40px 0;
            text-align: center;
            color: var(--text-light);
        }

        @media (max-width: 768px) {
            .hero {
                grid-template-columns: 1fr;
                padding: 40px 0 60px;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            nav {
                display: none;
            }

            .hero-content p {
                font-size: 1rem;
            }

            .stats {
                grid-template-columns: 1fr;
                gap: 30px;
            }

            .section-title {
                font-size: 2rem;
            }
        }

        .scroll-reveal {
            opacity: 0;
            transform: translateY(30px);
        }

        .scroll-reveal.revealed {
            opacity: 1;
            transform: translateY(0);
            transition: all 0.8s ease-out;
        }
    </style>
</head>
<body>
    <header class="container">
        <div class="logo">SUPER</div>
        <nav>
            <a href="#features">Caractéristiques</a>
            <a href="#products">Produits</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <section class="hero container">
        <div class="hero-content">
            <h1>Dominez <span>l'été</span></h1>
            <p>Les pistolets à eau électriques les plus puissants et futuristes du marché. Capacité massive, portée incroyable, batterie longue durée.</p>
            <button class="cta-button">Acheter Maintenant</button>
            <div class="stats">
                <div class="stat">
                    <div class="stat-number">2.5L</div>
                    <div class="stat-label">Capacité Réservoir</div>
                </div>
                <div class="stat">
                    <div class="stat-number">10m+</div>
                    <div class="stat-label">Portée Maximale</div>
                </div>
                <div class="stat">
                    <div class="stat-number">8h</div>
                    <div class="stat-label">Autonomie Batterie</div>
                </div>
            </div>
        </div>
        <div class="hero-image">
            <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 400 300'%3E%3Crect fill='%23050a14' width='400' height='300'/%3E%3Ctext x='50%25' y='50%25' font-size='18' fill='%2300d4ff' text-anchor='middle' dy='.3em'%3E[Image produit chargée]%3C/text%3E%3C/svg%3E" alt="Pistolet à eau SUPER">
        </div>
    </section>

    <section id="features" class="features container">
        <h2 class="section-title">Caractéristiques <span>Épiques</span></h2>
        <div class="features-grid">
            <div class="feature-card scroll-reveal">
                <div class="feature-icon">⚡</div>
                <h3>Moteur Électrique</h3>
                <p>Technologie de pompe haute performance pour un débit constant et puissant sans effort.</p>
            </div>
            <div class="feature-card scroll-reveal">
                <div class="feature-icon">🔋</div>
                <h3>Batterie Rechargeable</h3>
                <p>4 batteries lithium incluses avec 4 chargeurs. Énergie illimitée pour vos batailles aquatiques.</p>
            </div>
            <div class="feature-card scroll-reveal">
                <div class="feature-icon">💧</div>
                <h3>Réservoir Interchangeable</h3>
                <p>Système modulaire avec réservoirs supplémentaires. Jeu sans interruption, remplissages rapides.</p>
            </div>
        </div>
    </section>

    <section id="products" class="products container">
        <h2 class="section-title">Nos <span>Modèles</span></h2>
        <div class="products-grid">
            <div class="product-card scroll-reveal">
                <div class="product-image">
                    <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 300 250'%3E%3Crect fill='%23050a14' width='300' height='250'/%3E%3Crect fill='%23333333' x='80' y='90' width='140' height='70' rx='5'/%3E%3Ccircle cx='200' cy='100' r='8' fill='%23ff6b1a'/%3E%3Crect fill='%23222222' x='60' y='50' width='180' height='20' rx='3'/%3E%3C/svg%3E" alt="Modèle Noir">
                </div>
                <h3>Modèle Noir</h3>
                <ul class="product-specs">
                    <li>Design Tactique Premium</li>
                    <li>Portée 10m</li>
                    <li>Réservoir 2.5L</li>
                    <li>Batterie 8h</li>
                </ul>
                <button class="buy-now">Acheter</button>
            </div>
            <div class="product-card scroll-reveal">
                <div class="product-image">
                    <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 300 250'%3E%3Crect fill='%23050a14' width='300' height='250'/%3E%3Crect fill='%230066ff' x='80' y='90' width='140' height='70' rx='5'/%3E%3Ccircle cx='200' cy='100' r='8' fill='%23ff6b1a'/%3E%3Crect fill='%230052cc' x='60' y='50' width='180' height='20' rx='3'/%3E%3C/svg%3E" alt="Modèle Bleu">
                </div>
                <h3>Modèle Bleu</h3>
                <ul class="product-specs">
                    <li>Design Moderne Futuriste</li>
                    <li>Portée 12m</li>
                    <li>Réservoir 2.8L</li>
                    <li>Batterie 10h</li>
                </ul>
                <button class="buy-now">Acheter</button>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2024 SUPER Pistolets à Eau. Tous droits réservés. | Livraison mondiale rapide</p>
        </div>
    </footer>

    <script>
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('revealed');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.scroll-reveal').forEach(el => {
            observer.observe(el);
        });

        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        document.querySelectorAll('.cta-button, .buy-now').forEach(button => {
            button.addEventListener('click', function() {
                alert('Merci ! Vous allez être redirigé vers la page d\'achat AliExpress.');
            });
        });

        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 50) {
                header.style.background = 'rgba(10, 20, 40, 0.95)';
                header.style.backdropFilter = 'blur(10px)';
                header.style.boxShadow = '0 4px 30px rgba(0, 212, 255, 0.1)';
            } else {
                header.style.background = 'transparent';
                header.style.boxShadow = 'none';
            }
        });
    </script>
</body>
</html>
