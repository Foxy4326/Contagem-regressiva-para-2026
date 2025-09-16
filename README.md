<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contagem Regressiva para 2026</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #1a1a2e, #16213e, #0f3460);
            color: white;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            overflow: hidden;
            position: relative;
        }

        body::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, rgba(0,0,0,0) 70%);
            z-index: -1;
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
            animation: fadeInDown 1s ease-in-out;
        }

        .container {
            display: flex;
            gap: 1.5rem;
            margin: 2rem 0;
            flex-wrap: wrap;
            justify-content: center;
        }

        .time-segment {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 1.5rem;
            min-width: 120px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.18);
            transition: transform 0.3s ease;
        }

        .time-segment:hover {
            transform: translateY(-5px);
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

        .message {
            margin-top: 2rem;
            font-size: 1.2rem;
            max-width: 600px;
            line-height: 1.6;
            opacity: 0;
            animation: fadeInUp 1s ease-in-out 1s forwards;
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

        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            .number {
                font-size: 2.5rem;
            }
            .time-segment {
                min-width: 100px;
                padding: 1rem;
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
        }

        /* Estrelas de fundo */
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
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>

    <h1>⏳ Contagem Regressiva para 2026</h1>

    <div class="container">
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

    <p class="message">Prepare-se para um novo ano cheio de possibilidades! 🎆✨</p>

    <script>
        // Gera estrelas no fundo
        const starsContainer = document.getElementById('stars');
        for (let i = 0; i < 100; i++) {
            const star = document.createElement('div');
            star.classList.add('star');
            star.style.width = Math.random() * 3 + 'px';
            star.style.height = star.style.width;
            star.style.left = Math.random() * 100 + 'vw';
            star.style.top = Math.random() * 100 + 'vh';
            star.style.animationDelay = Math.random() * 3 + 's';
            starsContainer.appendChild(star);
        }

        // Define a data alvo: 1º de janeiro de 2026, 00:00:00
        const targetDate = new Date("January 1, 2026 00:00:00").getTime();

        function updateCountdown() {
            const now = new Date().getTime();
            const distance = targetDate - now;

            if (distance < 0) {
                document.getElementById("days").innerText = "000";
                document.getElementById("hours").innerText = "00";
                document.getElementById("minutes").innerText = "00";
                document.getElementById("seconds").innerText = "00";
                document.querySelector("h1").innerText = "🎉 Feliz 2026! 🎉";
                document.querySelector(".message").innerText = "O futuro chegou! Aproveite cada momento.";
                return;
            }

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("days").innerText = days.toString().padStart(3, '0');
            document.getElementById("hours").innerText = hours.toString().padStart(2, '0');
            document.getElementById("minutes").innerText = minutes.toString().padStart(2, '0');
            document.getElementById("seconds").innerText = seconds.toString().padStart(2, '0');
        }

        // Atualiza a cada 1 segundo
        setInterval(updateCountdown, 1000);

        // Executa ao carregar
        updateCountdown();
    </script>
</body>
</html>
