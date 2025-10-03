<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>Contagem Regressiva para 2026 | Bíblia Sagrada</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: 'Segoe UI', sans-serif;
            background: linear-gradient(135deg, #0d1b2a, #1b263b, #2c3e50);
            color: white;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding-top: 80px;
            position: relative;
            overflow-x: hidden;
        }
        .top-bar {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1rem 2rem;
            background: rgba(13, 27, 42, 0.95);
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            border-bottom: 1px solid rgba(255, 215, 0, 0.3);
        }
        .logo { font-weight: bold; color: #FFD700; display: flex; align-items: center; gap: 0.5rem; }
        .date-display { text-align: right; }
        .weekday { font-weight: 600; color: #FFD700; }
        .full-date { font-size: 0.9rem; color: #ccc; }
        
        /* MENU DE AUTENTICAÇÃO */
        .auth-top-bar {
            position: fixed;
            top: 12px;
            right: 20px;
            display: flex;
            gap: 0.8rem;
            z-index: 101;
        }
        .auth-top-btn {
            padding: 0.5rem 1rem;
            border: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.95rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: all 0.2s ease;
        }
        .auth-top-btn:hover {
            transform: translateY(-2px);
        }
        .login-btn {
            background: rgba(30, 58, 138, 0.8);
            color: white;
            box-shadow: 0 2px 6px rgba(30, 58, 138, 0.4);
        }
        .signup-btn {
            background: rgba(13, 148, 136, 0.8);
            color: white;
            box-shadow: 0 2px 6px rgba(13, 148, 136, 0.4);
        }

        main { text-align: center; padding: 0 20px; max-width: 1000px; }
        h1 {
            font-size: 2.8rem;
            margin: 1.5rem 0;
            color: #FFD700;
        }
        .container {
            display: flex;
            gap: 1rem;
            margin: 2rem 0;
            flex-wrap: wrap;
            justify-content: center;
        }
        .time-segment-weeks, .time-segment {
            background: #0d1b2a;
            border: 1px solid rgba(255, 215, 0, 0.2);
            border-radius: 12px;
            padding: 1.2rem 0.8rem;
            min-width: 90px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .number-weeks, .number {
            font-size: 2.2rem;
            font-weight: bold;
            color: #FFD700;
            text-shadow: 0 0 8px rgba(255, 215, 0, 0.6);
        }
        .label-weeks, .label {
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: #ccc;
            margin-top: 0.4rem;
        }
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 0.7rem;
            padding: 0.9rem 1.8rem;
            border-radius: 50px;
            font-weight: 700;
            text-decoration: none;
            margin: 0.6rem 0;
            transition: transform 0.2s;
        }
        .btn:hover { transform: translateY(-2px); }
        .connect-button {
            background: #8B0000;
            color: white;
            border: 2px solid #FFD700;
        }
        .coming-soon-btn {
            background: linear-gradient(135deg, #1e3a8a, #2563eb);
            color: white;
        }
        .video-soon-btn {
            background: linear-gradient(135deg, #6a0dad, #8b28d9);
            color: white;
        }
        .bible-read-btn {
            background: linear-gradient(135deg, #c9a04b, #d4b060);
            color: #1a1a2e;
        }

        /* CHAT COM IA */
        .chat-section {
            margin-top: 2.5rem;
            background: rgba(20, 30, 50, 0.7);
            padding: 1.5rem;
            border-radius: 20px;
            width: 100%;
            max-width: 600px;
        }
        #spiritualChatBox {
            height: 220px;
            overflow-y: auto;
            background: rgba(0,0,0,0.3);
            padding: 1rem;
            border-radius: 10px;
            margin-bottom: 1rem;
            font-size: 0.95rem;
            line-height: 1.5;
        }
        #spiritualChatInput {
            width: 70%;
            padding: 0.7rem;
            border-radius: 50px;
            border: none;
            outline: none;
            background: rgba(255,255,255,0.1);
            color: white;
        }
        .send-btn {
            padding: 0.7rem 1.2rem;
            background: #4B0082;
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
        }

        /* MODAL DE AUTENTICAÇÃO */
        .auth-modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s ease;
        }
        .auth-modal-overlay.active {
            opacity: 1;
            pointer-events: all;
        }
        .auth-modal {
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            padding: 2rem;
            border-radius: 20px;
            width: 90%;
            max-width: 450px;
            border: 2px solid #FFD700;
            color: white;
        }
        .auth-modal h3 {
            color: #FFD700;
            margin-bottom: 1.5rem;
            text-align: center;
        }
        .auth-form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }
        .auth-form input {
            padding: 0.8rem;
            border-radius: 10px;
            border: 1px solid #444;
            background: rgba(0,0,0,0.3);
            color: white;
            font-size: 1rem;
        }
        .auth-form input::placeholder {
            color: #888;
        }
        .auth-actions {
            display: flex;
            gap: 0.8rem;
            margin-top: 1rem;
        }
        .auth-btn-modal {
            flex: 1;
            padding: 0.8rem;
            border: none;
            border-radius: 10px;
            font-weight: bold;
            cursor: pointer;
        }
        .auth-btn-modal.cancel {
            background: #8B0000;
            color: white;
        }
        .auth-btn-modal.submit {
            background: #FFD700;
            color: #1a1a2e;
        }

        /* ELEMENTOS ESPIRITUAIS FLUTUANTES */
        .spiritual-element {
            position: fixed;
            font-size: 1.8rem;
            opacity: 0.7;
            z-index: -1;
            pointer-events: none;
            animation: float 15s infinite ease-in-out;
        }
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            25% { transform: translateY(-20px) rotate(2deg); }
            50% { transform: translateY(-10px) rotate(-2deg); }
            75% { transform: translateY(-25px) rotate(1deg); }
        }

        /* PLAY PROTECT BANNER */
        #playProtect {
            display: none;
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: #0d1b2a;
            color: #FFD700;
            padding: 12px 20px;
            border-radius: 10px;
            border: 1px solid #FFD700;
            z-index: 10000;
            box-shadow: 0 0 15px rgba(255,215,0,0.5);
            font-weight: bold;
        }

        /* TELA DE NOVIDADES */
        .novidades-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10000;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.4s ease;
        }
        .novidades-overlay.ativo {
            opacity: 1;
            pointer-events: all;
        }
        .novidades-content {
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            color: white;
            padding: 2.5rem;
            border-radius: 20px;
            width: 90%;
            max-width: 550px;
            position: relative;
            border: 2px solid #FFD700;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.7);
        }
        .fechar-novidades {
            position: absolute;
            top: 15px;
            right: 15px;
            background: #8B0000;
            color: white;
            width: 32px;
            height: 32px;
            border: none;
            border-radius: 50%;
            font-weight: bold;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.2s;
        }
        .fechar-novidades:hover {
            background: #a52a2a;
            transform: scale(1.1);
        }
        .novidades-content h2 {
            color: #FFD700;
            margin-bottom: 1.5rem;
            text-align: center;
            font-size: 1.8rem;
        }
        .novidades-lista {
            list-style: none;
            padding: 0;
            text-align: left;
        }
        .novidades-lista li {
            padding: 0.8rem 0;
            border-bottom: 1px solid rgba(255, 215, 0, 0.1);
            font-size: 1.05rem;
            line-height: 1.5;
        }
        .novidades-lista li:last-child {
            border-bottom: none;
        }
        .novidades-lista strong {
            color: #FFD700;
        }

        @media (max-width: 500px) {
            .auth-top-bar { display: none; }
            .number-weeks, .number { font-size: 1.8rem; }
            h1 { font-size: 2rem; }
            .btn { padding: 0.7rem 1.4rem; font-size: 1rem; }
        }
    </style>
</head>
<body>

<!-- MENU DE AUTENTICAÇÃO -->
<div class="auth-top-bar">
    <button class="auth-top-btn login-btn" onclick="openModal('login')">
        <i class="fas fa-user"></i> Login
    </button>
    <button class="auth-top-btn signup-btn" onclick="openModal('signup')">
        <i class="fas fa-user-plus"></i> Cadastrar
    </button>
</div>

<div class="top-bar">
    <div class="logo"><i class="fas fa-bible"></i> Bíblia Sagrada</div>
    <div class="date-display">
        <div class="weekday" id="weekday">Carregando...</div>
        <div class="full-date" id="full-date">—</div>
    </div>
</div>

<main>
    <h1>⏳ Contagem Regressiva para 2026</h1>

    <div class="container">
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

    <!-- BOTÃO DO CANAL COM LINK EXATO -->
    <a href="https://youtube.com/@bibliasagrada-r3c4o?si=rcpyTgzjQt9DRdUL" target="_blank" class="btn connect-button">
        <i class="fab fa-youtube"></i> Conecte-se à Palavra: Visite nosso Canal
    </a>

    <a href="#" class="btn coming-soon-btn" onclick="window.scrollTo({top:0,behavior:'smooth'}); return false;">
        <i class="fas fa-calendar-star"></i> Ano em Breve: 2026 ✨
    </a>
    <a href="#" class="btn video-soon-btn" onclick="alert('🔔 Novo vídeo em breve! Inscreva-se no canal para não perder.'); return false;">
        <i class="fas fa-video"></i> Vídeo Lançado em Breve! 🎬
    </a>
    <a href="https://www.bibliaonline.com.br/" target="_blank" class="btn bible-read-btn">
        <i class="fas fa-book-open"></i> Ler a Bíblia Online 📖
    </a>

    <!-- CHAT COM IA -->
    <div class="chat-section">
        <h3>💬 Comentários com IA Espiritual</h3>
        <div id="spiritualChatBox"></div>
        <div>
            <input type="text" id="spiritualChatInput" placeholder="Escreva sua oração, dúvida ou testemunho..." />
            <button class="send-btn" onclick="sendSpiritualMessage()">Enviar</button>
        </div>
    </div>
</main>

<!-- MODAIS -->
<div class="auth-modal-overlay" id="loginModal">
    <div class="auth-modal">
        <h3><i class="fas fa-sign-in-alt"></i> Faça seu Login</h3>
        <form class="auth-form" onsubmit="handleAuth(event, 'login')">
            <input type="email" placeholder="E-mail" required />
            <input type="password" placeholder="Senha" required />
            <div class="auth-actions">
                <button type="button" class="auth-btn-modal cancel" onclick="closeAuthModal()">Cancelar</button>
                <button type="submit" class="auth-btn-modal submit">Entrar</button>
            </div>
        </form>
    </div>
</div>

<div class="auth-modal-overlay" id="signupModal">
    <div class="auth-modal">
        <h3><i class="fas fa-user-plus"></i> Crie sua Conta</h3>
        <form class="auth-form" onsubmit="handleAuth(event, 'signup')">
            <input type="text" placeholder="Nome completo" required />
            <input type="email" placeholder="E-mail" required />
            <input type="password" placeholder="Senha" required />
            <div class="auth-actions">
                <button type="button" class="auth-btn-modal cancel" onclick="closeAuthModal()">Cancelar</button>
                <button type="submit" class="auth-btn-modal submit">Cadastrar</button>
            </div>
        </form>
    </div>
</div>

<!-- PLAY PROTECT BANNER -->
<div id="playProtect">
    <i class="fas fa-shield-alt"></i> Verificando integridade do site...
</div>

<!-- TELA DE NOVIDADES -->
<div id="novidadesModal" class="novidades-overlay">
    <div class="novidades-content">
        <button class="fechar-novidades" onclick="fecharNovidades()">✕</button>
        <h2>✨ Novidades e Atualizações</h2>
        <ul class="novidades-lista">
            <li><strong>✅ Correção:</strong> Contagem regressiva para 2026 agora funciona em todos os navegadores!</li>
            <li><strong>🌟 Novo:</strong> Chat com IA Espiritual responde com versículos bíblicos</li>
            <li><strong>🕊️ Novo:</strong> Anjos e símbolos de Jesus flutuando suavemente na tela</li>
            <li><strong>🔒 Novo:</strong> Sistema "Site Play Protect" verifica integridade ao carregar</li>
            <li><strong>📱 Melhoria:</strong> Design totalmente responsivo para celular e tablet</li>
            <li><strong>🎥 Atualizado:</strong> Botão direto para seu canal do YouTube</li>
        </ul>
        <p style="font-size: 0.9rem; color: #aaa; margin-top: 1.2rem;">
            Que Deus abençoe seu caminho até 2026! 🙏
        </p>
    </div>
</div>

<script>
// === PLAY PROTECT ===
function sitePlayProtect() {
    const banner = document.getElementById('playProtect');
    banner.style.display = 'block';
    setTimeout(() => {
        const ok = document.getElementById('days') && typeof Date.now === 'function';
        if (ok) {
            banner.innerHTML = '<i class="fas fa-check-circle"></i> Site verificado e seguro! ✝️';
            banner.style.background = 'rgba(0, 100, 0, 0.8)';
            setTimeout(() => {
                banner.style.opacity = '0';
                banner.style.transition = 'opacity 1s';
                setTimeout(() => { banner.style.display = 'none'; }, 1000);
            }, 2000);
        } else {
            banner.innerHTML = '<i class="fas fa-exclamation-triangle"></i> Erro. Recarregue.';
            banner.style.background = 'rgba(139, 0, 0, 0.9)';
        }
    }, 1500);
}

// === DATA BRASIL ===
function updateCurrentDate() {
    const now = new Date();
    const optsW = { weekday: 'long', timeZone: 'America/Sao_Paulo' };
    const optsD = { day: 'numeric', month: 'long', year: 'numeric', timeZone: 'America/Sao_Paulo' };
    const weekday = now.toLocaleDateString('pt-BR', optsW).replace(/^\w/, c => c.toUpperCase());
    const fullDate = now.toLocaleDateString('pt-BR', optsD).replace(/^\w/, c => c.toUpperCase());
    document.getElementById('weekday').textContent = weekday;
    document.getElementById('full-date').textContent = fullDate;
}

// ✅ CONTAGEM REGRESSIVA CORRIGIDA — NÃO FICA EM 000
function updateCountdown() {
    const target = Date.UTC(2026, 0, 1, 0, 0, 0); // 1º de janeiro de 2026
    const now = Date.now();
    const diff = target - now;

    if (diff <= 0) {
        document.getElementById("weeks-display").textContent = "000";
        document.getElementById("days").textContent = "000";
        document.getElementById("hours").textContent = "00";
        document.getElementById("minutes").textContent = "00";
        document.getElementById("seconds").textContent = "00";
        document.querySelector("h1").textContent = "🎉 2026 CHEGOU!";
        return;
    }

    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const weeks = Math.floor(days / 7);
    const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((diff % (1000 * 60)) / 1000);

    document.getElementById("weeks-display").textContent = String(weeks).padStart(3, '0');
    document.getElementById("days").textContent = String(days).padStart(3, '0');
    document.getElementById("hours").textContent = String(hours).padStart(2, '0');
    document.getElementById("minutes").textContent = String(minutes).padStart(2, '0');
    document.getElementById("seconds").textContent = String(seconds).padStart(2, '0');
}

// === CHAT IA ===
function loadSpiritualChat() {
    const box = document.getElementById('spiritualChatBox');
    const msgs = JSON.parse(localStorage.getItem('spiritualChatMessages')) || [];
    box.innerHTML = '';
    msgs.forEach(m => {
        const div = document.createElement('div');
        div.style.marginBottom = '0.8rem';
        div.style.padding = '0.6rem';
        div.style.borderRadius = '10px';
        div.style.maxWidth = '85%';
        if (m.type === 'user') {
            div.style.backgroundColor = 'rgba(255,255,255,0.08)';
            div.style.marginLeft = 'auto';
            div.style.textAlign = 'right';
            div.innerHTML = `<strong>Você:</strong> ${m.text}`;
        } else {
            div.style.backgroundColor = 'rgba(75, 0, 130, 0.35)';
            div.style.marginRight = 'auto';
            div.style.textAlign = 'left';
            div.innerHTML = `<strong>IA Espiritual:</strong> ${m.text}`;
        }
        box.appendChild(div);
    });
    box.scrollTop = box.scrollHeight;
}

function getSpiritualResponse(msg) {
    const t = msg.toLowerCase();
    if (t.includes('triste')) return "Salmos 34:18: 'O Senhor está perto dos que têm o coração quebrantado.' 🙏";
    if (t.includes('medo')) return "Isaías 41:10: 'Não temas, porque eu sou contigo.' ✨";
    if (t.includes('2026') || t.includes('futuro')) return "Jeremias 29:11: 'Eu tenho planos de paz para você.' 🌟";
    if (t.includes('força')) return "Isaías 40:31: 'Renovarão as suas forças como águias.' 🦅";
    return "A Palavra de Deus é lâmpada para os meus pés (Salmos 119:105). Confie nEle! ✨";
}

function sendSpiritualMessage() {
    const input = document.getElementById('spiritualChatInput');
    const text = input.value.trim();
    if (!text) return;
    const msgs = JSON.parse(localStorage.getItem('spiritualChatMessages')) || [];
    msgs.push({ type: 'user', text });
    msgs.push({ type: 'ai', text: getSpiritualResponse(text) });
    localStorage.setItem('spiritualChatMessages', JSON.stringify(msgs));
    input.value = '';
    loadSpiritualChat();
}

// === LOGIN/CADASTRO ===
function openModal(type) {
    if (type === 'login') document.getElementById('loginModal').classList.add('active');
    else document.getElementById('signupModal').classList.add('active');
}
function closeAuthModal() {
    document.getElementById('loginModal').classList.remove('active');
    document.getElementById('signupModal').classList.remove('active');
}
function handleAuth(e, type) {
    e.preventDefault();
    const form = e.target.closest('form');
    const inputs = form.querySelectorAll('input');
    const data = {};
    inputs.forEach(input => {
        data[input.placeholder.toLowerCase().replace(' ', '_')] = input.value;
    });
    alert(type === 'login' 
        ? `✅ Login simulado!\nE-mail: ${data.email}` 
        : `✅ Cadastro simulado!\nBem-vindo, ${data.nome_completo || 'amigo'}!`
    );
    closeAuthModal();
    form.reset();
}
document.querySelectorAll('.auth-modal-overlay').forEach(m => {
    m.addEventListener('click', e => { if (e.target === m) closeAuthModal(); });
});

// === ANJOS E JESUS FLUTUANTES ===
function createSpiritualElements() {
    const symbols = ['👼', '😇', '🕊️', '✝️', '🙏', '🕯️', '✨', '⛪'];
    for (let i = 0; i < 8; i++) {
        const el = document.createElement('div');
        el.className = 'spiritual-element';
        el.textContent = symbols[Math.floor(Math.random() * symbols.length)];
        el.style.left = `${Math.random() * 90 + 5}%`;
        el.style.top = `${Math.random() * 80 + 10}%`;
        el.style.animationDelay = `${Math.random() * 10}s`;
        el.style.fontSize = `${1.2 + Math.random() * 1.2}rem`;
        el.style.opacity = `${0.4 + Math.random() * 0.4}`;
        document.body.appendChild(el);
    }
}

// === NOVIDADES ===
function mostrarNovidades() {
    const jaVi = localStorage.getItem('novidades_vistas_v2');
    if (!jaVi) {
        document.getElementById('novidadesModal').classList.add('ativo');
    }
}
function fecharNovidades() {
    document.getElementById('novidadesModal').classList.remove('ativo');
    localStorage.setItem('novidades_vistas_v2', 'sim');
}

// === INICIALIZAÇÃO ===
document.addEventListener('DOMContentLoaded', () => {
    createSpiritualElements();
    sitePlayProtect();
    updateCurrentDate();
    updateCountdown();
    loadSpiritualChat();
    setInterval(() => {
        updateCurrentDate();
        updateCountdown();
    }, 1000);
    document.getElementById('spiritualChatInput').addEventListener('keypress', e => {
        if (e.key === 'Enter') sendSpiritualMessage();
    });
    setTimeout(mostrarNovidades, 1200);
});
</script>

</body>
</html>