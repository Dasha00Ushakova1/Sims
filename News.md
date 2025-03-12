<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>О игре</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #4d0000;
            color: #fff5f5;
            margin: 0;
            padding: 20px;
            transition: background-color 0.5s;
        }
        h1, h2 {
            text-align: center;
        }
        .game-description {
            margin: 20px 0;
            animation: fadeIn 1s;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        summary {
            font-weight: bold;
            outline: none; /* Убираем обводку при фокусе */
        }
        summary::-webkit-details-marker {
            display: none; /* Убираем стандартный маркер */
        }
        summary::before {
            content: " "; /* Добавляем свой маркер */
            font-size: 1.2em;
            transition: transform 0.3s;
        }
        details[open] summary::before {
            transform: rotate(90deg); /* Поворачиваем маркер при открытии */
        }
    </style>
</head>
<body>
    <h1>О нашей игре</h1>
    <div class="game-description">
        <p>Здесь вы можете узнать больше о нашей увлекательной игре, которая погружает вас в мир приключений и захватывающих событий!</p>
        <img src="black.png" alt="Изображение из игры" style="width: 100%; max-width: 600px; display: block; margin: 0 auto;">
</body>
</html>

