<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contagem Regressiva para 2026 | Bíblia Sagrada</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0d1b2a, #1b263b, #2c3e50);
            color: white;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            overflow-x: hidden;
            position: relative;
        }

        /* MENU SUPERIOR */
        .top-bar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 1rem 2rem;
            background: rgba(13, 27, 42, 0.9);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
            border-bottom: 1px solid rgba(255, 215, 0, 0.3);
        }

        .logo {
            font-weight: bold;
            font-size: 1.5rem;
            letter-spacing: 1px;
            color: #FFD700;
            text-shadow: 0 0 8px rgba(255, 215, 0, 0.7);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo i {
            font-size: 1.3rem;
        }

        .date-display {
            font-size: 1rem;
            text-align: right;
            line-height: 1.4;
        }

        .weekday {
            font-weight: 600;
            color: #FFD700;
        }

        .full-date {
            font-size: 0.9rem;
            color: #ccc;
        }

        /* CONTEÚDO PRINCIPAL */
        main {
            margin-top: 80px;
            z-index: 10;
            padding: 0 20px;
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
            animation: fadeInDown 1s ease-in-out;
            color: #FFD700;
            font-weight: 800;
        }

        .subtitle {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: #e0e0e0;
            max-width: 600px;
            line-height: 1.6;
        }

        .container {
            display: flex;
            gap: 1.5rem;
            margin: 2rem 0;
            flex-wrap: wrap;
            justify-content: center;
        }

        .time-segment {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 1.5rem;
            min-width: 120px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 215, 0, 0.2);
            transition: transform 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .time-segment:hover {
            transform: translateY(-5px);
            border-color: rgba(255, 215, 0, 0.6);
        }

        .number {
            font-size: 3rem;
            font-weight: bold;
            color: #ffdd59;
            text-shadow: 0 0 15px rgba(255, 221, 89, 0.7);
        }

        .label {
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 0.5rem;
            color: #e0e0e0;
        }

        /* BOTÃO DO CANAL */
        .bible-btn {
            margin-top: 2rem;
            padding: 1.2rem 2.5rem;
            background: linear-gradient(135deg, #8B0000, #4B0000);
            color: #FFD700;
            font-size: 1.3rem;
            font-weight: 700;
            border: 2px solid #FFD700;
            border-radius: 50px;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 1rem;
            box-shadow: 0 5px 20px rgba(139, 0, 0, 0.5);
            transition: all 0.3s ease;
            text-decoration: none;
            animation: pulse 2s infinite;
        }

        .bible-btn:hover {
            transform: translateY(-3px) scale(1.03);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.4);
            background: linear-gradient(135deg, #a52a2a, #6b0f0f);
        }

        .bible-btn i {
            font-size: 1.6rem;
        }

        /* BOTÃO 2026 */
        .coming-soon-btn {
            margin-top: 1.5rem;
            padding: 1rem 2.5rem;
            background: linear-gradient(135deg, #1e3a8a, #0c1b44);
            color: #fff;
            font-size: 1.2rem;
            font-weight: 700;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            box-shadow: 0 5px 20px rgba(30, 58, 138, 0.5);
            transition: all 0.4s ease;
            text-decoration: none;
            position: relative;
            overflow: hidden;
        }

        .coming-soon-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: 0.5s;
        }

        .coming-soon-btn:hover::before {
            left: 100%;
        }

        .coming-soon-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(59, 130, 246, 0.5);
            background: linear-gradient(135deg, #2563eb, #1d4ed8);
        }

        .coming-soon-btn i {
            font-size: 1.3rem;
            color: #FFD700;
        }

        /* BOTÃO VÍDEO EM BREVE */
        .video-soon-btn {
            margin-top: 1.5rem;
            padding: 1rem 2.5rem;
            background: linear-gradient(135deg, #6a0dad, #3b006b);
            color: #fff;
            font-size: 1.2rem;
            font-weight: 700;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            box-shadow: 0 5px 20px rgba(106, 13, 173, 0.4);
            transition: all 0.4s ease;
            text-decoration: none;
            animation: glow 2s infinite alternate;
        }

        .video-soon-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(155, 50, 255, 0.6);
            background: linear-gradient(135deg, #8b28d9, #5a00b3);
        }

        .video-soon-btn i {
            font-size: 1.3rem;
            color: #FFD700;
        }

        @keyframes glow {
            from { box-shadow: 0 5px 20px rgba(106, 13, 173, 0.4); }
            to { box-shadow: 0 5px 25px rgba(186, 85, 255, 0.8); }
        }

        /* MODAL DE LANÇAMENTO */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 200;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.4s ease;
        }

        .modal-overlay.active {
            opacity: 1;
            pointer-events: all;
        }

        .modal {
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            padding: 2.5rem;
            border-radius: 20px;
            text-align: center;
            max-width: 90%;
            max-width: 550px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.7);
            border: 2px solid #FFD700;
            position: relative;
            transform: scale(0.9);
            transition: transform 0.4s ease;
        }

        .modal-overlay.active .modal {
            transform: scale(1);
        }

        .modal h2 {
            color: #FFD700;
            font-size: 1.8rem;
            margin-bottom: 1rem;
        }

        .modal p {
            font-size: 1.1rem;
            line-height: 1.6;
            margin-bottom: 1.5rem;
            color: #e0e0e0;
        }

        /* CONTAINER DO VÍDEO */
        .video-container {
            position: relative;
            padding-bottom: 56.25%; /* Proporção 16:9 */
            height: 0;
            overflow: hidden;
            border-radius: 12px;
            margin-bottom: 1.5rem;
        }

        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }

        .close-modal {
            background: #8B0000;
            color: white;
            border: none;
            padding: 0.8rem 1.8rem;
            font-size: 1.1rem;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .close-modal:hover {
            background: #a52a2a;
        }

        @keyframes pulse {
            0% { box-shadow: 0 5px 20px rgba(139, 0, 0, 0.5); }
            50% { box-shadow: 0 5px 20px rgba(255, 215, 0, 0.6); }
            100% { box-shadow: 0 5px 20px rgba(139, 0, 0, 0.5); }
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media (max-width: 768px) {
            .top-bar {
                flex-direction: column;
                gap: 0.5rem;
                padding: 1rem;
                text-align: center;
            }
            h1 {
                font-size: 2.5rem;
            }
            .subtitle {
                font-size: 1.1rem;
                padding: 0 1rem;
            }
            .bible-btn, .coming-soon-btn, .video-soon-btn {
                padding: 1rem 2rem;
                font-size: 1.1rem;
                gap: 0.8rem;
            }
            .bible-btn i, .coming-soon-btn i, .video-soon-btn i {
                font-size: 1.4rem;
            }
        }

        @media (max-width: 480px) {
            .container {
                gap: 0.5rem;
            }
            .time-segment {
                min-width: 80px;
                padding: 0.8rem;
            }
            .number {
                font-size: 2rem;
            }
            .label {
                font-size: 0.9rem;
            }
            .bible-btn, .coming-soon-btn, .video-soon-btn {
                padding: 0.8rem 1.5rem;
                font-size: 1rem;
                flex-direction: column;
                gap: 0.5rem;
            }
            .bible-btn i, .coming-soon-btn i, .video-soon-btn i {
                font-size: 1.5rem;
            }
            .modal {
                padding: 1.5rem;
                margin: 1rem;
            }
        }

        /* Estrelas / Céu de fundo */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.2; }
            50% { opacity: 1; }
        }

        /* Cruz sutil no canto */
        .cross {
            position: fixed;
            bottom: 20px;
            right: 20px;
            font-size: 1.5rem;
            color: rgba(255, 215, 0, 0.3);
            z-index: 5;
        }
    </style>
</head>
<body>
    <!-- MENU SUPERIOR -->
    <div class="top-bar">
        <div class="logo">
            <i class="fas fa-bible"></i>
            Bíblia Sagrada
        </div>
        <div class="date-display">
            <div class="weekday" id="weekday">Carregando...</div>
            <div class="full-date" id="full-date">—</div>
        </div>
    </div>

    <!-- CONTEÚDO PRINCIPAL -->
    <main>
        <h1>⏳ Contagem Regressiva para 2026</h1>
        <p class="subtitle">Prepare seu coração. Um novo tempo está chegando. Que a Palavra de Deus te guie até lá.</p>

        <div class="container">
            <div class="time-segment">
                <div class="number" id="weeks">000</div>
                <div class="label">Semanas</div>
            </div>
            <div class="time-segment">
                <div class="number" id="days">000</div>
                <div class="label">Dias</div>
            </div>
            <div class="time-segment">
                <div class="number" id="hours">00</div>
                <div class="label">Horas</div>
            </div>
            <div class="time-segment">
                <div class="number" id="minutes">00</div>
                <div class="label">Minutos</div>
            </div>
            <div class="time-segment">
                <div class="number" id="seconds">00</div>
                <div class="label">Segundos</div>
            </div>
        </div>

        <!-- BOTÃO DO CANAL -->
        <a href="https://youtube.com/@bibliasagrada-r3c4o?si=6siww098EMGjsXL6" target="_blank" class="bible-btn">
            <i class="fab fa-youtube"></i>
            <span>Conecte-se à Palavra: Visite nosso Canal</span>
        </a>

        <!-- BOTÃO 2026 -->
        <a href="#top" class="coming-soon-btn" onclick="scrollToTop(); return false;">
            <i class="fas fa-calendar-star"></i>
            <span>Ano em Breve: 2026 ✨</span>
        </a>

        <!-- BOTÃO VÍDEO EM BREVE -->
        <a class="video-soon-btn" onclick="openModal(); return false;">
            <i class="fas fa-video"></i>
            <span>Vídeo Lançado em Breve! 🎬</span>
        </a>
    </main>

    <!-- MODAL DE LANÇAMENTO COM VÍDEO -->
    <div class="modal-overlay" id="videoModal">
        <div class="modal">
            <h2><i class="fas fa-bell"></i> Novo Vídeo em Breve!</h2>
            <p>Um novo vídeo está sendo preparado com muito carinho para abençoar sua vida. 🙏</p>

            <!-- VÍDEO DO YOUTUBE EMBUTIDO -->
            <div class="video-container">
                <iframe 
                    src="https://www.youtube.com/embed/ryt0Ze7o0eE?si=u73GF-s3QqxxIWnE&autoplay=1&mute=1" 
                    frameborder="0" 
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                    allowfullscreen>
                </iframe>
            </div>

            <p>👉 <strong>Inscreva-se</strong> e <strong>ative o sininho</strong> para não perder!</p>
            <button class="close-modal" onclick="closeModal()">Fechar</button>
        </div>
    </div>

    <!-- CRUZ DECORATIVA -->
    <div class="cross">
        ✝
    </div>

    <div class="stars" id="stars"></div>

    <script>
        // Gera estrelas no fundo
        const starsContainer = document.getElementById('stars');
        for (let i = 0; i < 120; i++) {
            const star = document.createElement('div');
            star.classList.add('star');
            star.style.width = Math.random() * 3 + 'px';
            star.style.height = star.style.width;
            star.style.left = Math.random() * 100 + 'vw';
            star.style.top = Math.random() * 100 + 'vh';
            star.style.animationDelay = Math.random() * 3 + 's';
            starsContainer.appendChild(star);
        }

        // Data alvo: 1º de janeiro de 2026
        const targetDate = new Date("January 1, 2026 00:00:00").getTime();

        // Atualiza data e dia da semana
        function updateCurrentDate() {
            const now = new Date();
            const optionsWeekday = { weekday: 'long', timeZone: 'America/Sao_Paulo' };
            const optionsFullDate = { 
                day: 'numeric', 
                month: 'long', 
                year: 'numeric',
                timeZone: 'America/Sao_Paulo'
            };

            const weekday = now.toLocaleDateString('pt-BR', optionsWeekday)
                .replace(/^\w/, c => c.toUpperCase());
            const fullDate = now.toLocaleDateString('pt-BR', optionsFullDate)
                .replace(/^\w/, c => c.toUpperCase());

            document.getElementById('weekday').textContent = weekday;
            document.getElementById('full-date').textContent = fullDate;
        }

        // Atualiza contagem regressiva
        function updateCountdown() {
            const now = new Date().getTime();
            const distance = targetDate - now;

            if (distance < 0) {
                document.getElementById("weeks").innerText = "000";
                document.getElementById("days").innerText = "000";
                document.getElementById("hours").innerText = "00";
                document.getElementById("minutes").innerText = "00";
                document.getElementById("seconds").innerText = "00";
                document.querySelector("h1").innerText = "🎉 2026 CHEGOU! 🎉";
                document.querySelector(".subtitle").innerText = "Que este novo ano seja abençoado pela luz da Palavra!";
                return;
            }

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const weeks = Math.floor(days / 7);
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("weeks").innerText = weeks.toString().padStart(3, '0');
            document.getElementById("days").innerText = days.toString().padStart(3, '0');
            document.getElementById("hours").innerText = hours.toString().padStart(2, '0');
            document.getElementById("minutes").innerText = minutes.toString().padStart(2, '0');
            document.getElementById("seconds").innerText = seconds.toString().padStart(2, '0');
        }

        // Função para rolar suavemente até o topo
        function scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        }

        // Funções do Modal
        function openModal() {
            document.getElementById('videoModal').classList.add('active');
        }

        function closeModal() {
            document.getElementById('videoModal').classList.remove('active');
        }

        // Fecha modal se clicar fora
        document.getElementById('videoModal').addEventListener('click', function(e) {
            if (e.target === this) {
                closeModal();
            }
        });

        setInterval(() => {
            updateCountdown();
            updateCurrentDate();
        }, 1000);

        updateCountdown();
        updateCurrentDate();
    </script>
</body>
</html>
