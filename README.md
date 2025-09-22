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
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
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

        /* MENU SUPERIOR ESTILIZADO */
        .top-bar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 1rem 2rem;
            background: rgba(20, 20, 40, 0.8);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .logo {
            font-weight: bold;
            font-size: 1.5rem;
            letter-spacing: 1px;
            color: #ffdd59;
            text-shadow: 0 0 8px rgba(255, 221, 89, 0.7);
        }

        .date-display {
            font-size: 1rem;
            text-align: right;
            line-height: 1.4;
        }

        .weekday {
            font-weight: 600;
            color: #ffdd59;
        }

        .full-date {
            font-size: 0.9rem;
            color: #ccc;
        }

        /* CONTEÚDO PRINCIPAL */
        main {
            margin-top: 80px; /* Para não ficar escondido pelo menu */
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
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
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
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
