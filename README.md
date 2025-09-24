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

        /* BLOCO DE SEMANAS NO ESTILO DA IMAGEM */
        .time-segment-weeks {
            background: #0d1b2a;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
            padding: 1.2rem;
            min-width: 110px;
            border-radius: 12px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .time-segment-weeks:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(255, 215, 0, 0.3);
        }

        .number-weeks {
            font-size: 2.8rem;
            font-weight: bold;
            color: #FFD700;
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.7);
        }

        .label-weeks {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 0.3rem;
            color: #ccc;
        }

        /* BOTÃO DO CANAL (ESTILO DA IMAGEM) */
        .connect-button {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            background: #8B0000;
            color: white;
            font-size: 1.2rem;
            font-weight: 700;
            padding: 1rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            border: 2px solid #FFD700;
            box-shadow: 0 0 10px rgba(255, 215, 0, 0.7);
            transition: all 0.3s ease;
            margin-top: 2rem;
        }

        .connect-button:hover {
            background: #a52a2a;
            transform: translateY(-3px);
            box-shadow: 0 0 15px rgba(255, 215, 0, 0.9);
        }

        .connect-button i {
            font-size: 1.4rem;
            color: #FFD700;
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

        /* BOTÃO LER A BÍBLIA */
        .bible-read-btn {
            margin-top: 1.5rem;
            padding: 1rem 2.5rem;
            background: linear-gradient(135deg, #c9a04b, #a67c00);
            color: white;
            font-size: 1.2rem;
            font-weight: 700;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            box-shadow: 0 5px 20px rgba(199, 160, 75, 0.4);
            transition: all 0.4s ease;
            text-decoration: none;
            animation: shine 3s infinite alternate;
        }

        .bible-read-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.5);
            background: linear-gradient(135deg, #d4b060, #c9a04b);
        }

        .bible-read-btn i {
            font-size: 1.3rem;
            color: #fff;
        }

        @keyframes shine {
            from { box-shadow: 0 5px 20px rgba(199, 160, 75, 0.4); }
            to { box-shadow: 0 5px 25px rgba(255, 215, 0, 0.7); }
        }

        /* MODAL DE LANÇAMENTO COM IMAGEM */
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

        /* CHAT COM IA */
        .chat-section {
            margin-top: 3rem;
            background: rgba(20, 30, 50, 0.7);
            padding: 1.5rem;
            border-radius: 20px;
            max-width: 600px;
            width: 90%;
        }

        .chat-section h3 {
            color: #FFD700;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        #aiChatBox {
            height: 250px;
            overflow-y: auto;
            background: rgba(0,0,0,0.3);
            padding: 1rem;
            border-radius: 10px;
            margin-bottom: 1rem;
            font-size: 0.95rem;
            line-height: 1.5;
        }

        #aiChatBox div {
            margin-bottom: 0.8rem;
            padding: 0.6rem;
            border-radius: 10px;
            max-width: 85%;
        }

        #aiChatBox div[sender="user"] {
            background: rgba(255,255,255,0.08);
            margin-left: auto;
            text-align: right;
        }

        #aiChatBox div[sender="ai"] {
            background: rgba(75, 0, 130, 0.3);
            margin-right: auto;
            text-align: left;
        }

        .chat-input-area {
            display: flex;
            gap: 0.5rem;
        }

        #aiChatInput {
            flex: 1;
            padding: 0.8rem;
            border-radius: 50px;
            border: none;
            outline: none;
            font-size: 1rem;
            background: rgba(255,255,255,0.1);
            color: white;
        }

        #aiChatInput::placeholder {
            color: #aaa;
        }

        .send-btn {
            background: #4B0082;
            color: white;
            border: none;
            padding: 0 1.5rem;
            border-radius: 50px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 4px 10px rgba(75, 0, 130, 0.4);
        }

        .send-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(75, 0, 130, 0.6);
        }

        .chat-footer {
            font-size: 0.85rem;
            color: #aaa;
            margin-top: 0.5rem;
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
            .container {
                gap: 1rem;
            }
            .time-segment, .time-segment-weeks {
                min-width: 90px;
                padding: 1rem;
            }
            .number {
                font-size: 2.5rem;
            }
            .number-weeks {
                font-size: 2.2rem;
            }
        }

        @media (max-width: 480px) {
            .container {
                gap: 0.5rem;
            }
            .time-segment, .time-segment-weeks {
                min-width: 80px;
                padding: 0.8rem;
            }
            .number {
                font-size: 2rem;
            }
            .number-weeks {
                font-size: 1.8rem;
            }
            .label, .label-weeks {
                font-size: 0.85rem;
            }
            .connect-button, .coming-soon-btn, .video-soon-btn, .bible-read-btn {
                padding: 0.8rem 1.5rem;
                font-size: 1rem;
                flex-direction: column;
                gap: 0.5rem;
            }
            .modal {
                padding: 1.5rem;
                margin: 1rem;
            }
            .chat-section {
                margin-top: 2rem;
                padding: 1rem;
            }
            #aiChatBox {
                height: 200px;
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
            <!-- BLOCO DE SEMANAS NOVO -->
            <div class="time-segment-weeks">
                <div class="number-weeks" id="weeks-display">000</div>
                <div class="label-weeks">Semanas</div>
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

        <!-- BOTÃO "CONECTE-SE À PALAVRA" -->
        <a href="https://youtube.com/@bibliasagrada-r3c4o?si=6siww098EMGjsXL6" target="_blank" class="connect-button">
            <i class="fab fa-youtube"></i>
            Conecte-se à Palavra: Visite nosso Canal
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

        <!-- BOTÃO LER A BÍBLIA -->
        <a href="https://www.bibliaonline.com.br/" target="_blank" class="bible-read-btn">
            <i class="fas fa-book-open"></i>
            <span>Ler a Bíblia Online 📖</span>
        </a>

        <!-- CHAT COM IA -->
        <div class="chat-section">
            <h3>💬 Fale com a IA da Palavra</h3>
            <div id="aiChatBox"></div>
            <div class="chat-input-area">
                <input type="text" id="aiChatInput" placeholder="Escreva sua mensagem, dúvida ou oração...">
                <button onclick="sendAiMessage()" class="send-btn">Enviar</button>
            </div>
            <p class="chat-footer">
                Uma IA espiritual responde com mensagens baseadas na Palavra de Deus. 🙏
            </p>
        </div>
    </main>

    <!-- MODAL DE LANÇAMENTO COM IMAGEM -->
    <div class="modal-overlay" id="videoModal">
        <div class="modal">
            <h2><i class="fas fa-bell"></i> Novo Vídeo em Breve!</h2>
            <p>Um novo vídeo está sendo preparado com muito carinho para abençoar sua vida. 🙏</p>

            <div style="background: #1a1a2e; padding: 1rem; border-radius: 15px; border: 2px solid #FFD700; margin-bottom: 1.5rem;">
                <img 
                    src="https://via.placeholder.com/400x225/1a1a2e/FFFFFF?text=DEUS+CUMPRE+SUAS+PROMESSAS" 
                    alt="Novo Vídeo em Breve" 
                    style="width: 100%; max-width: 380px; border-radius: 10px; box-shadow: 0 5px 15
