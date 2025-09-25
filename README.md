<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Erro 404 – Site em Manutenção</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background: linear-gradient(135deg, #1a1a2e, #16213e, #0f3460);
      color: white;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 20px;
    }

    .container {
      max-width: 600px;
      background: rgba(0, 0, 0, 0.6);
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
    }

    .error-code {
      font-size: 5rem;
      font-weight: 800;
      color: #ff6b6b;
      margin-bottom: 10px;
      text-shadow: 0 0 15px rgba(255, 107, 107, 0.5);
    }

    h1 {
      font-size: 2.2rem;
      margin-bottom: 20px;
      color: #4ecdc4;
    }

    p {
      font-size: 1.1rem;
      line-height: 1.7;
      margin-bottom: 25px;
      color: #e0e0e0;
    }

    .reason {
      background: rgba(255, 107, 107, 0.15);
      border-left: 4px solid #ff6b6b;
      padding: 15px;
      margin: 20px 0;
      text-align: left;
      border-radius: 0 8px 8px 0;
    }

    .reason strong {
      color: #ff9e9e;
    }

    .footer {
      margin-top: 30px;
      font-size: 0.95rem;
      color: #aaa;
    }

    @media (max-width: 600px) {
      .container { padding: 25px; }
      .error-code { font-size: 3.5rem; }
      h1 { font-size: 1.8rem; }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="error-code">404</div>
    <h1>⚠️ Site Temporariamente Indisponível</h1>
    
    <p>Estamos realizando ajustes técnicos para melhorar sua experiência.</p>

    <div class="reason">
      <strong>Motivo:</strong> Arquivo principal (<code>index.html</code>) não encontrado no servidor.<br>
      Isso geralmente acontece durante atualizações ou configuração do site.
    </div>

    <p>Por favor, tente novamente em alguns minutos. Agradecemos sua paciência! 🙏</p>

    <div class="footer">
      <p>— Equipe de Desenvolvimento</p>
    </div>
  </div>
</body>
</html>
