<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Contagem Regressiva para 2026 | Bíblia Sagrada</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background: linear-gradient(135deg, #0d1b2a, #1b263b, #2c3e50);
      color: white;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      overflow-x: hidden;
      position: relative;
    }

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

    .date-display {
      font-size: 1rem;
      text-align: right;
      line-height: 1.4;
    }

    .weekday { font-weight: 600; color: #FFD700; }
    .full-date { font-size: 0.9rem; color: #ccc; }

    main {
      margin-top: 80px;
      z-index: 10;
      padding: 0 20px;
      width: 100%;
      max-width: 800px;
    }

    h1 {
      font-size: 3.2rem;
      margin-bottom: 0.8rem;
      color: #FFD700;
      font-weight: 800;
    }

    .highlight-year {
      font-size: 2.8rem;
      color: #ffdd59;
      margin: 0.5rem 0;
      font-weight: 900;
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

    .number {
      font-size: 3rem;
      font-weight: bold;
      color: #ffdd59;
    }

    .label {
      font-size: 1rem;
      text-transform: uppercase;
      letter-spacing: 1px;
      margin-top: 0.5rem;
      color: #e0e0e0;
    }

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
      text-decoration: none;
      animation: pulse 2s infinite;
    }

    .launch-info {
      margin-top: 1.5rem;
      padding: 1rem 2.5rem;
      background: rgba(255, 255, 255, 0.1);
      color: #FFD700;
      font-size: 1.2rem;
      font-weight: 700;
      border: 1px solid rgba(255, 215, 0, 0.5);
      border-radius: 50px;
      display: inline-block;
    }

    .auth-buttons {
      display: flex;
      gap: 1rem;
      margin-top: 2rem;
      flex-wrap: wrap;
      justify-content: center;
    }

    .auth-btn {
      padding: 0.9rem 1.8rem;
      font-size: 1.1rem;
      font-weight: 600;
      border-radius: 50px;
      border: none;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 0.7rem;
      color: white;
      min-width: 160px;
    }

    .register-btn { background: linear-gradient(135deg, #065f46, #022c22); }
    .login-btn { background: linear-gradient(135deg, #1e3a8a, #0c1b44); }

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
      text-decoration: none;
    }

    /* TELAS DE LOGIN/CADASTRO */
    .auth-screen {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(13, 27, 42, 0.95);
      z-index: 1000;
      justify-content: center;
      align-items: center;
      padding: 20px;
    }

    .auth-form {
      background: rgba(20, 30, 50, 0.9);
      padding: 2.5rem;
      border-radius: 20px;
      width: 100%;
      max-width: 420px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
      border: 1px solid rgba(255, 215, 0, 0.3);
      text-align: center;
    }

    .close-btn {
      position: absolute;
      top: 20px;
      right: 20px;
      background: none;
      border: none;
      color: white;
      font-size: 1.5rem;
      cursor: pointer;
    }

    .input-group {
      margin-bottom: 1.2rem;
      text-align: left;
    }

    .input-group label {
      display: block;
      margin-bottom: 0.5rem;
      color: #e0e0e0;
      font-weight: 500;
    }

    .input-group input {
      width: 100%;
      padding: 0.9rem;
      border-radius: 10px;
      border: 1px solid #444;
      background: rgba(0, 0, 0, 0.3);
      color: white;
      font-size: 1rem;
    }

    .error {
      color: #ff6b6b;
      font-size: 0.9rem;
      margin-top: 0.5rem;
      display: none;
    }

    /* DASHBOARD */
    .dashboard {
      display: none;
      text-align: center;
      padding: 2rem;
      background: rgba(20, 30, 50, 0.8);
      border-radius: 20px;
      max-width: 500px;
      width: 90%;
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
      border: 1px solid rgba(255, 215, 0, 0.4);
    }

    .user-email {
      background: rgba(0,0,0,0.3);
      padding: 0.6rem 1.2rem;
      border-radius: 10px;
      margin: 1rem 0;
      font-size: 1.1rem;
    }

    .logout-btn {
      background: #8B0000;
      color: #FFD700;
      border: 1px solid #FFD700;
      padding: 0.8rem 1.8rem;
      border-radius: 50px;
      font-size: 1.1rem;
      cursor: pointer;
      margin-top: 1.5rem;
    }

    @keyframes pulse {
      0%, 100% { box-shadow: 0 5px 20px rgba(139, 0, 0, 0.5); }
      50% { box-shadow: 0 5px 20px rgba(255, 215, 0, 0.6); }
    }

    @media (max-width: 768px) {
      .top-bar { flex-direction: column; gap: 0.5rem; padding: 1rem; text-align: center; }
      h1 { font-size: 2.4rem; }
      .highlight-year { font-size: 2.2rem; }
      .container { gap: 1rem; }
      .time-segment { min-width: 100px; padding: 1rem; }
      .number { font-size: 2.5rem; }
    }
  </style>
</head>
<body>

  <!-- Menu Superior -->
  <div class="top-bar">
    <div class="logo">
      <i class="fas fa-bible"></i> Bíblia Sagrada
    </div>
    <div class="date-display">
      <div class="weekday" id="currentWeekday">Carregando...</div>
      <div class="full-date" id="currentDate">Carregando...</div>
    </div>
  </div>

  <!-- CONTEÚDO PRINCIPAL -->
  <main id="homeScreen">
    <h1>CONTAGEM REGRESSIVA</h1>
    <div class="highlight-year">2026</div>
    <p class="subtitle">Aguardando o grande momento em 2026. Cada segundo conta para a transformação espiritual.</p>

    <div class="container">
      <div class="time-segment">
        <div class="number" id="days">00</div>
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

    <a href="https://www.bible.com/pt-BR" target="_blank" class="bible-btn">
      <i class="fas fa-book-bible"></i> Ler Bíblia Online
    </a>

    <div class="launch-info">
      ✨ Em breve lançará em 2026
    </div>

    <div class="auth-buttons">
      <button class="auth-btn register-btn" onclick="showScreen('register')">
        <i class="fas fa-user-plus"></i> Cadastrar
      </button>
      <button class="auth-btn login-btn" onclick="showScreen('login')">
        <i class="fas fa-sign-in-alt"></i> Login
      </button>
    </div>

    <button class="video-soon-btn">
      <i class="fas fa-video"></i> Vídeo em Breve
    </button>
  </main>

  <!-- TELA DE CADASTRO -->
  <div id="registerScreen" class="auth-screen">
    <button class="close-btn" onclick="hideScreen()">×</button>
    <div class="auth-form">
      <div class="logo"><i class="fas fa-bible"></i> Bíblia Sagrada</div>
      <h2>✨ Criar Conta</h2>
      <form id="registerForm">
        <div class="input-group">
          <label for="regEmail">E-mail</label>
          <input type="email" id="regEmail" placeholder="seu@email.com" required>
        </div>
        <div class="input-group">
          <label for="regPassword">Senha (mín. 6 caracteres)</label>
          <input type="password" id="regPassword" placeholder="••••••••" required minlength="6">
          <div class="error" id="regError"></div>
        </div>
        <button type="submit" class="auth-btn register-btn">Cadastrar</button>
      </form>
    </div>
  </div>

  <!-- TELA DE LOGIN -->
  <div id="loginScreen" class="auth-screen">
    <button class="close-btn" onclick="hideScreen()">×</button>
    <div class="auth-form">
      <div class="logo"><i class="fas fa-bible"></i> Bíblia Sagrada</div>
      <h2>Entrar na sua conta</h2>
      <form id="loginForm">
        <div class="input-group">
          <label for="loginEmail">E-mail</label>
          <input type="email" id="loginEmail" placeholder="seu@email.com" required>
        </div>
        <div class="input-group">
          <label for="loginPassword">Senha</label>
          <input type="password" id="loginPassword" placeholder="••••••••" required>
          <div class="error" id="loginError"></div>
        </div>
        <button type="submit" class="auth-btn login-btn">Acessar Conta</button>
      </form>
    </div>
  </div>

  <!-- DASHBOARD (ÁREA LOGADA) -->
  <div id="dashboardScreen" class="auth-screen">
    <div class="dashboard">
      <h1>✨ Bem-vindo!</h1>
      <p>Você está logado com sucesso.</p>
      <div class="user-email" id="userEmail">Carregando...</div>
      <button class="logout-btn" onclick="logout()">Sair da conta</button>
      <button class="auth-btn" style="margin-top:1rem; background:#4B0000;" onclick="hideScreen('dashboard')">
        ← Voltar
      </button>
    </div>
  </div>

  <!-- Firebase SDK -->
  <script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-auth-compat.js"></script>

  <script>
    // 🔥 🔥 🔥 SUBSTITUA ESTE BLOCO PELO SEU DO FIREBASE 🔥 🔥 🔥
    const firebaseConfig = {
      apiKey: "YOUR_API_KEY",
      authDomain: "YOUR_PROJECT.firebaseapp.com",
      projectId: "YOUR_PROJECT",
      storageBucket: "YOUR_PROJECT.appspot.com",
      messagingSenderId: "123456789",
      appId: "1:123456789:web:abc123..."
    };

    // Inicializa o Firebase
    firebase.initializeApp(firebaseConfig);
    const auth = firebase.auth();

    // Atualiza data
    function updateDate() {
      const now = new Date();
      document.getElementById('currentDate').textContent = now.toLocaleDateString('pt-BR', { year: 'numeric', month: 'long', day: 'numeric' });
      document.getElementById('currentWeekday').textContent = now.toLocaleDateString('pt-BR', { weekday: 'long' }).charAt(0).toUpperCase() + now.toLocaleDateString('pt-BR', { weekday: 'long' }).slice(1);
    }
    updateDate();

    // Contagem regressiva
    function updateCountdown() {
      const target = new Date("January 1, 2026 00:00:00").getTime();
      const now = new Date().getTime();
      const dist = target - now;

      if (dist > 0) {
        const days = Math.floor(dist / (1000 * 60 * 60 * 24));
        const hours = Math.floor((dist % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const mins = Math.floor((dist % (1000 * 60 * 60)) / (1000 * 60));
        const secs = Math.floor((dist % (1000 * 60)) / 1000);
        document.getElementById("days").innerText = days.toString().padStart(2, '0');
        document.getElementById("hours").innerText = hours.toString().padStart(2, '0');
        document.getElementById("minutes").innerText = mins.toString().padStart(2, '0');
        document.getElementById("seconds").innerText = secs.toString().padStart(2, '0');
      }
    }
    updateCountdown();
    setInterval(updateCountdown, 1000);

    // Navegação entre telas
    function showScreen(screen) {
      document.getElementById('homeScreen').style.display = 'none';
      document.getElementById(registerScreen).style.display = 'none';
      document.getElementById(loginScreen).style.display = 'none';
      document.getElementById(dashboardScreen).style.display = 'none';
      if (screen === 'register') document.getElementById('registerScreen').style.display = 'flex';
      if (screen === 'login') document.getElementById('loginScreen').style.display = 'flex';
    }

    function hideScreen() {
      document.getElementById('registerScreen').style.display = 'none';
      document.getElementById('loginScreen').style.display = 'none';
      document.getElementById('dashboardScreen').style.display = 'none';
      document.getElementById('homeScreen').style.display = 'block';
    }

    // Cadastro
    document.getElementById('registerForm').addEventListener('submit', async (e) => {
      e.preventDefault();
      const email = document.getElementById('regEmail').value.trim();
      const password = document.getElementById('regPassword').value;
      const errorEl = document.getElementById('regError');
      errorEl.style.display = 'none';

      try {
        await auth.createUserWithEmailAndPassword(email, password);
        alert('Conta criada com sucesso! ✅');
        document.getElementById('userEmail').textContent = email;
        hideScreen();
        document.getElementById('homeScreen').style.display = 'none';
        document.getElementById('dashboardScreen').style.display = 'flex';
      } catch (err) {
        let msg = 'Erro ao criar conta.';
        if (err.code === 'auth/email-already-in-use') msg = 'Este e-mail já está cadastrado!';
        else if (err.code === 'auth/weak-password') msg = 'A senha deve ter pelo menos 6 caracteres.';
        errorEl.textContent = msg;
        errorEl.style.display = 'block';
      }
    });

    // Login
    document.getElementById('loginForm').addEventListener('submit', async (e) => {
      e.preventDefault();
      const email = document.getElementById('loginEmail').value.trim();
      const password = document.getElementById('loginPassword').value;
      const errorEl = document.getElementById('loginError');
      errorEl.style.display = 'none';

      try {
        await auth.signInWithEmailAndPassword(email, password);
        document.getElementById('userEmail').textContent = email;
        hideScreen();
        document.getElementById('homeScreen').style.display = 'none';
        document.getElementById('dashboardScreen').style.display = 'flex';
      } catch (err) {
        errorEl.textContent = 'E-mail ou senha incorretos.';
        errorEl.style.display = 'block';
      }
    });

    // Logout
    function logout() {
      auth.signOut().then(() => {
        alert('Você saiu da sua conta.');
        document.getElementById('dashboardScreen').style.display = 'none';
        document.getElementById('homeScreen').style.display = 'block';
      });
    }

    // Verifica login automático
    auth.onAuthStateChanged(user => {
      if (user) {
        document.getElementById('userEmail').textContent = user.email;
        document.getElementById('homeScreen').style.display = 'none';
        document.getElementById('dashboardScreen').style.display = 'flex';
      }
    });
  </script>
</body>
</html>
