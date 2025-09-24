<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Site em Manutenção</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background: linear-gradient(135deg, #1a2a6c, #b21f1f, #1a2a6c);
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
      background: rgba(0, 0, 0, 0.7);
      padding: 40px;
      border-radius: 16px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
    }

    h1 {
      font-size: 2.5rem;
      margin-bottom: 20px;
      color: #ffcc00;
    }

    p.subtitle {
      font-size: 1.2rem;
      margin-bottom: 30px;
      line-height: 1.6;
    }

    .menu {
      list-style: none;
      margin: 30px 0;
    }

    .menu li {
      margin: 15px 0;
    }

    .menu a {
      color: #4fc3f7;
      text-decoration: none;
      font-size: 1.1rem;
      display: inline-block;
      padding: 10px 20px;
      border: 1px solid #4fc3f7;
      border-radius: 8px;
      transition: all 0.3s ease;
    }

    .menu a:hover {
      background-color: #4fc3f7;
      color: #000;
      transform: translateY(-2px);
    }

    .footer {
      margin-top: 30px;
      font-size: 0.95rem;
      color: #bbb;
    }

    @media (max-width: 600px) {
      .container {
        padding: 25px;
      }

      h1 {
        font-size: 2rem;
      }

      .menu a {
        font-size: 1rem;
        padding: 8px 16px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🛠️ Site em Manutenção</h1>
    <p class="subtitle">Estamos realizando melhorias para oferecer uma experiência ainda melhor!</p>

    <ul class="menu">
      <li><a href="#">&#127968; Página Inicial</a></li>
      <li><a href="mailto:contato@seudominio.com.br">&#128231; Contato</a></li>
      <li><a href="https://status.seudominio.com.br" target="_blank">&#128201; Status da Manutenção</a></li>
      <li><a href="https://seudominio.com.br">&#8617; Voltar ao Site</a></li>
    </ul>

    <div class="footer">
      <p><strong>Previsão de retorno:</strong> Em breve!</p>
      <p>Agradecemos sua paciência. 😊</p>
    </div>
  </div>
</body>
</html>
