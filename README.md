<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal de Notícias - Seu site de notícias atualizado</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Reset e estilos base */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Roboto', Arial, sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
        }
        
        a {
            text-decoration: none;
            color: #c4170c;
            transition: all 0.3s ease;
        }
        
        a:hover {
            text-decoration: underline;
            color: #9a1209;
        }
        
        /* Cabeçalho */
        header {
            background-color: #c4170c;
            padding: 10px 0;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .header-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .logo {
            color: white;
            font-size: 2.2rem;
            font-weight: bold;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
        }
        
        .search-box {
            display: flex;
        }
        
        .search-box input {
            padding: 10px;
            border: none;
            border-radius: 4px 0 0 4px;
            width: 250px;
        }
        
        .search-box button {
            background: #333;
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        .search-box button:hover {
            background: #555;
        }
        
        /* Menu de navegação */
        nav {
            background-color: #b0130a;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .menu {
            display: flex;
            list-style: none;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .menu li {
            padding: 12px 15px;
            transition: background 0.3s;
        }
        
        .menu li a {
            color: white;
            font-weight: 500;
            display: flex;
            align-items: center;
        }
        
        .menu li a i {
            margin-right: 8px;
            font-size: 0.9rem;
        }
        
        .menu li:hover {
            background-color: #a11109;
        }
        
        /* Conteúdo principal */
        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 0 15px;
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 30px;
        }
        
        /* Destaque principal */
        .main-news {
            grid-column: 1 / -1;
            margin-bottom: 20px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        
        .highlight {
            position: relative;
            cursor: pointer;
        }
        
        .highlight img {
            width: 100%;
            height: 450px;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .highlight:hover img {
            transform: scale(1.02);
        }
        
        .highlight-content {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.9));
            color: white;
            padding: 30px;
        }
        
        .highlight-content h1 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            line-height: 1.2;
        }
        
        .highlight-content p {
            font-size: 1.2rem;
            margin-bottom: 15px;
            max-width: 80%;
        }
        
        .news-meta {
            display: flex;
            align-items: center;
            font-size: 0.9rem;
            color: #ddd;
        }
        
        .news-meta span {
            margin-right: 20px;
            display: flex;
            align-items: center;
        }
        
        .news-meta i {
            margin-right: 5px;
        }
        
        /* Notícias secundárias */
        .secondary-news {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
            margin-bottom: 40px;
        }
        
        .news-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }
        
        .news-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .news-card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }
        
        .news-content {
            padding: 20px;
        }
        
        .news-content h3 {
            margin-bottom: 12px;
            font-size: 1.25rem;
            line-height: 1.3;
        }
        
        .news-content p {
            color: #666;
            font-size: 0.95rem;
            margin-bottom: 15px;
        }
        
        .news-tag {
            display: inline-block;
            background: #f0f0f0;
            color: #c4170c;
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
            margin-bottom: 10px;
        }
        
        /* Lista de últimas notícias */
        .content {
            margin-bottom: 40px;
        }
        
        .content h2 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #c4170c;
            color: #333;
        }
        
        .news-list {
            background: white;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.08);
        }
        
        .news-item {
            padding: 15px 0;
            border-bottom: 1px solid #eee;
        }
        
        .news-item:last-child {
            border-bottom: none;
        }
        
        .news-item h3 {
            margin-bottom: 8px;
            font-size: 1.1rem;
        }
        
        .news-item p {
            color: #666;
            font-size: 0.9rem;
        }
        
        .news-item time {
            font-size: 0.8rem;
            color: #888;
            display: block;
            margin-top: 5px;
        }
        
        /* Coluna lateral */
        .sidebar h2 {
            font-size: 1.5rem;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #c4170c;
            color: #333;
        }
        
        .sidebar-news {
            margin-bottom: 35px;
            background: white;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.08);
        }
        
        .sidebar-item {
            display: flex;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
            transition: transform 0.3s;
        }
        
        .sidebar-item:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }
        
        .sidebar-item:hover {
            transform: translateX(5px);
        }
        
        .sidebar-item img {
            width: 80px;
            height: 80px;
            object-fit: cover;
            margin-right: 15px;
            border-radius: 4px;
        }
        
        .sidebar-item h3 {
            font-size: 0.95rem;
            line-height: 1.3;
        }
        
        .sidebar-item .number {
            font-size: 1.2rem;
            font-weight: bold;
            color: #c4170c;
            margin-right: 10px;
        }
        
        /* Rodapé */
        footer {
            background: #333;
            color: white;
            padding: 40px 0 20px;
            margin-top: 50px;
        }
        
        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 30px;
        }
        
        .footer-section h3 {
            margin-bottom: 20px;
            font-size: 1.2rem;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-section h3:after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 2px;
            background: #c4170c;
        }
        
        .footer-section ul {
            list-style: none;
        }
        
        .footer-section ul li {
            margin-bottom: 12px;
        }
        
        .footer-section a {
            color: #ddd;
            transition: color 0.3s;
            display: flex;
            align-items: center;
        }
        
        .footer-section a:hover {
            color: white;
        }
        
        .footer-section a i {
            margin-right: 8px;
            font-size: 0.9rem;
        }
        
        .footer-section p {
            color: #bbb;
            margin-bottom: 15px;
            font-size: 0.9rem;
        }
        
        .newsletter-form {
            display: flex;
            flex-direction: column;
        }
        
        .newsletter-form input {
            padding: 12px;
            margin-bottom: 10px;
            border: none;
            border-radius: 4px;
        }
        
        .newsletter-form button {
            padding: 12px;
            background: #c4170c;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background 0.3s;
            font-weight: 500;
        }
        
        .newsletter-form button:hover {
            background: #a11109;
        }
        
        .footer-bottom {
            max-width: 1200px;
            margin: 30px auto 0;
            padding: 20px 15px 0;
            border-top: 1px solid #555;
            text-align: center;
            color: #bbb;
            font-size: 0.9rem;
        }
        
        .social-icons {
            display: flex;
            margin-top: 15px;
        }
        
        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 36px;
            height: 36px;
            background: #444;
            border-radius: 50%;
            margin-right: 10px;
            transition: background 0.3s;
        }
        
        .social-icons a:hover {
            background: #c4170c;
        }
        
        /* Responsividade */
        @media (max-width: 1100px) {
            .highlight-content h1 {
                font-size: 2rem;
            }
            
            .highlight-content p {
                font-size: 1.1rem;
            }
        }
        
        @media (max-width: 992px) {
            .secondary-news {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .footer-content {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .menu {
                overflow-x: auto;
                padding-bottom: 5px;
            }
            
            .menu::-webkit-scrollbar {
                height: 5px;
            }
            
            .menu::-webkit-scrollbar-thumb {
                background: #888;
                border-radius: 10px;
            }
        }
        
        @media (max-width: 768px) {
            .container {
                grid-template-columns: 1fr;
            }
            
            .secondary-news {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
            }
            
            .header-top {
                flex-direction: column;
                gap: 15px;
            }
            
            .search-box input {
                width: 100%;
            }
            
            .highlight img {
                height: 350px;
            }
            
            .highlight-content {
                padding: 20px;
            }
            
            .highlight-content h1 {
                font-size: 1.7rem;
            }
            
            .highlight-content p {
                max-width: 100%;
                font-size: 1rem;
            }
            
            .news-meta {
                flex-wrap: wrap;
            }
            
            .news-meta span {
                margin-bottom: 5px;
            }
            
            .logo {
                font-size: 1.8rem;
            }
        }
        
        @media (max-width: 576px) {
            .highlight img {
                height: 300px;
            }
            
            .highlight-content h1 {
                font-size: 1.5rem;
            }
            
            .news-card img {
                height: 160px;
            }
            
            .menu li {
                padding: 10px 12px;
            }
            
            .menu li a {
                font-size: 0.9rem;
            }
            
            .menu li a i {
                display: none;
            }
        }
        
        .breaking-news {
            background: #ffd700;
            padding: 10px 0;
            margin-bottom: 20px;
        }
        
        .breaking-news-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
            display: flex;
            align-items: center;
        }
        
        .breaking-news span {
            background: #c4170c;
            color: white;
            padding: 5px 10px;
            border-radius: 4px;
            font-weight: bold;
            margin-right: 15px;
            font-size: 0.9rem;
        }
        
        .breaking-news p {
            font-weight: 500;
            margin: 0;
        }
        
        .breaking-news a {
            color: #c4170c;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <header>
        <div class="header-top">
            <div class="logo"><i class="fas fa-newspaper"></i>PORTAL DE NOTÍCIAS</div>
            <div class="search-box">
                <input type="text" placeholder="Buscar notícias...">
                <button><i class="fas fa-search"></i></button>
            </div>
        </div>
        <nav>
            <ul class="menu">
                <li><a href="#"><i class="fas fa-home"></i>Home</a></li>
                <li><a href="#"><i class="fas fa-globe-americas"></i>Últimas</a></li>
                <li><a href="#"><i class="fas fa-landmark"></i>Política</a></li>
                <li><a href="#"><i class="fas fa-chart-line"></i>Economia</a></li>
                <li><a href="#"><i class="fas fa-futbol"></i>Esportes</a></li>
                <li><a href="#"><i class="fas fa-microchip"></i>Tecnologia</a></li>
                <li><a href="#"><i class="fas fa-theater-masks"></i>Cultura</a></li>
                <li><a href="#"><i class="fas fa-heartbeat"></i>Saúde</a></li>
                <li><a href="#"><i class="fas fa-globe"></i>Mundo</a></li>
            </ul>
        </nav>
    </header>

    <div class="breaking-news">
        <div class="breaking-news-content">
            <span>PLANTÃO</span>
            <p><a href="#">Ministério da Economia anuncia nova medida para conter inflação. Mercado reage positivamente.</a></p>
        </div>
    </div>

    <main class="container">
        <section class="main-news">
            <div class="highlight">
                <img src="https://placehold.co/1200x600/cc0000/white?text=Notícia+Principal" alt="Destaque principal">
                <div class="highlight-content">
                    <h1><a href="#">Grande evento mundial acontece nesta semana: saiba todos os detalhes</a></h1>
                    <p>Encontro reunirá líderes de mais de 50 países para discutir acordos internacionais e mudanças climáticas.</p>
                    <div class="news-meta">
                        <span><i class="far fa-clock"></i> Há 2 horas</span>
                        <span><i class="far fa-eye"></i> 5.4k visualizações</span>
                        <span><i class="far fa-comment"></i> 342 comentários</span>
                    </div>
                </div>
            </div>
        </section>

        <section class="secondary-news">
            <div class="news-card">
                <div class="news-tag">Política</div>
                <img src="https://placehold.co/600x400/cccccc/333?text=Política" alt="Notícia de política">
                <div class="news-content">
                    <h3><a href="#">Novas medidas econômicas são anunciadas pelo governo</a></h3>
                    <p>Pacote inclui redução de impostos para setor de tecnologia e incentivos à exportação.</p>
                    <div class="news-meta">
                        <span><i class="far fa-clock"></i> Há 4h</span>
                    </div>
                </div>
            </div>
            
            <div class="news-card">
                <div class="news-tag">Esportes</div>
                <img src="https://placehold.co/600x400/cccccc/333?text=Esportes" alt="Notícia de esportes">
                <div class="news-content">
                    <h3><a href="#">Time local vence campeonato após 10 anos de espera</a></h3>
                    <p>Equipe conquista título nacional em jogo emocionante decidido nos últimos minutos.</p>
                    <div class="news-meta">
                        <span><i class="far fa-clock"></i> Há 6h</span>
                    </div>
                </div>
            </div>
            
            <div class="news-card">
                <div class="news-tag">Tecnologia</div>
                <img src="https://placehold.co/600x400/cccccc/333?text=Tecnologia" alt="Notícia de tecnologia">
                <div class="news-content">
                    <h3><a href="#">Nova tecnologia promete revolucionar setor de energia</a></h3>
                    <p>Startup desenvolve sistema que aumenta eficiência de painéis solares em 40%.</p>
                    <div class="news-meta">
                        <span><i class="far fa-clock"></i> Há 8h</span>
                    </div>
                </div>
            </div>
        </section>

        <section class="content">
            <h2><i class="fas fa-bolt"></i> Últimas Notícias</h2>
            <div class="news-list">
                <div class="news-item">
                    <h3><a href="#">Mercado financeiro reage positivamente a novas medidas governamentais</a></h3>
                    <p>Bolsa de valores tem alta histórica após anúncio de reformas econômicas.</p>
                    <time><i class="far fa-clock"></i> Publicado há 1 hora</time>
                </div>
                <div class="news-item">
                    <h3><a href="#">Pesquisa revela aumento no uso de aplicativos de saúde mental</a></h3>
                    <p>Número de usuários cresceu 65% no último ano, segundo estudo.</p>
                    <time><i class="far fa-clock"></i> Publicado há 3 horas</time>
                </div>
                <div class="news-item">
                    <h3><a href="#">Festival de cinema anuncia programação com produções internacionais</a></h3>
                    <p>Evento acontecerá no próximo mês com exibições gratuitas ao ar livre.</p>
                    <time><i class="far fa-clock"></i> Publicado há 5 horas</time>
                </div>
                <div class="news-item">
                    <h3><a href="#">Descoberta científica pode levar a novo tratamento para doenças raras</a></h3>
                    <p>Pesquisadores identificam mecanismo celular que pode revolucionar medicina.</p>
                    <time><i class="far fa-clock"></i> Publicado há 7 horas</time>
                </div>
            </div>
        </section>

        <aside class="sidebar">
            <div class="sidebar-news">
                <h2><i class="fas fa-fire"></i> Mais Lidas</h2>
                <div class="sidebar-item">
                    <span class="number">1</span>
                    <div>
                        <h3><a href="#">Celebridade internacional anuncia visita ao país</a></h3>
                    </div>
                </div>
                <div class="sidebar-item">
                    <span class="number">2</span>
                    <div>
                        <h3><a href="#">Previsão do tempo: frente fria chega ao sul do país</a></h3>
                    </div>
                </div>
                <div class="sidebar-item">
                    <span class="number">3</span>
                    <div>
                        <h3><a href="#">Novo aplicativo de mobilidade urbana chega às principais cidades</a></h3>
                    </div>
                </div>
                <div class="sidebar-item">
                    <span class="number">4</span>
                    <div>
                        <h3><a href="#">Reality show nacional tem maior audiência da temporada</a></h3>
                    </div>
                </div>
                <div class="sidebar-item">
                    <span class="number">5</span>
                    <div>
                        <h3><a href="#">Produtores rurais esperam maior safra dos últimos 5 anos</a></h3>
                    </div>
                </div>
            </div>

            <div class="sidebar-news">
                <h2><i class="fas fa-futbol"></i> Esportes</h2>
                <div class="sidebar-item">
                    <img src="https://placehold.co/100x100/cccccc/333?text=Esporte" alt="Notícia de esportes">
                    <div>
                        <h3><a href="#">Seleção se prepara para amistoso internacional</a></h3>
                    </div>
                </div>
                <div class="sidebar-item">
                    <img src="https://placehold.co/100x100/cccccc/333?text=Esporte" alt="Notícia de esportes">
                    <div>
                        <h3><a href="#">Atleta brasileiro quebra recorde sul-americano</a></h3>
                    </div>
                </div>
                <div class="sidebar-item">
                    <img src="https://placehold.co/100x100/cccccc/333?text=Esporte" alt="Notícia de esportes">
                    <div>
                        <h3><a href="#">Clube fecha contratação de jogador estrangeiro</a></h3>
                    </div>
                </div>
            </div>
        </aside>
    </main>

    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>Editoriais</h3>
                <ul>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Economia</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Política</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Esportes</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Tecnologia</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Cultura</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Portal de Notícias</h3>
                <ul>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Quem somos</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Nossa missão</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Equipe</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Fale conosco</a></li>
                    <li><a href="#"><i class="fas fa-chevron-right"></i> Anuncie</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Redes Sociais</h3>
                <ul>
                    <li><a href="#"><i class="fab fa-facebook"></i> Facebook</a></li>
                    <li><a href="#"><i class="fab fa-twitter"></i> Twitter</a></li>
                    <li><a href="#"><i class="fab fa-instagram"></i> Instagram</a></li>
                    <li><a href="#"><i class="fab fa-youtube"></i> YouTube</a></li>
                    <li><a href="#"><i class="fab fa-telegram"></i> Telegram</a></li>
                </ul>
                <div class="social-icons">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
            <div class="footer-section">
                <h3>Newsletter</h3>
                <p>Inscreva-se para receber as principais notícias no seu e-mail.</p>
                <form class="newsletter-form">
                    <input type="email" placeholder="Seu e-mail" required>
                    <button type="submit">Inscrever</button>
                </form>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2023 Portal de Notícias. Todos os direitos reservados.</p>
        </div>
    </footer>

    <script>
        // Simular atualização de tempo das notícias
        function updateTimes() {
            const times = document.querySelectorAll('time');
            times.forEach(time => {
                const text = time.textContent;
                if (text.includes('hora')) {
                    const hours = parseInt(text.match(/\d+/)[0]);
                    time.textContent = text.replace(hours, hours + 1);
                }
            });
        }
        
        // Atualizar a cada hora (simulação)
        setInterval(updateTimes, 60000);
        
        // Adicionar data atual no footer
        document.addEventListener('DOMContentLoaded', function() {
            const date = new Date();
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            const dateString = date.toLocaleDateString('pt-BR', options);
            
            const dateElement = document.createElement('p');
            dateElement.textContent = dateString;
            dateElement.style.marginTop = '10px';
            dateElement.style.color = '#999';
            
            document.querySelector('.footer-bottom').appendChild(dateElement);
        });
    </script>
</body>
</html>
