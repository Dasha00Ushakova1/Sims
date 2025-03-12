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
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
            animation: fadeIn 1s;
        }
        .gallery img {
            width: 200px;
            height: auto;
            cursor: pointer;
            transition: transform 0.3s;
        }
        .gallery img:hover {
            transform: scale(1.05);
        }
        .feedback-form {
            max-width: 400px;
            margin: 20px auto;
            padding: 20px;
            background: black;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            animation: fadeIn 1s;
        }
        .feedback-form input, .feedback-form textarea {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
            color: black;
        }
        .feedback-form button {
            background: #9c091a;
            border: none;
            padding: 10px;
            cursor: pointer;
            transition: background 0.3s;
            color: black;
        }
        .feedback-form button:hover {
            background: #218838;
        }
        .faq {
            margin-top: 40px;
            animation: fadeIn 1s;
            color: black;
        }
        details {
            margin-bottom: 10px;
            cursor: pointer;
            background: #fff;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 10px;
            transition: background 0.3s;
        }
        details:hover {
            background: #f9f9f9;
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
    <h1>О игре</h1>
    <div class="game-description">
        <p>Описание игры и ее особенностей.</p>
    </div>
    <h2>Галерея</h2>
    <div class="gallery">
        <img src="1517948329_38-sims-4-forgotten-hollow.jpg" alt="Галерея 1" onclick="openImage(this.src)">
        <img src="1642847466_vampire_bloodlines.jpg" alt="Галерея 2" onclick="openImage(this.src)">
        <img src="2021-04-29_174854.jpg" alt="Галерея 3" onclick="openImage(this.src)">
        <img src="DfsBFDgTBV4BXDgnebjQRA.jpg" alt="Галерея 4" onclick="openImage(this.src)">
        <img src="e5804d18740c39a19fb23004b1092.jpeg" alt="Галерея 5" onclick="openImage(this.src)">
    </div>
    <script>
        function openImage(src) {
            // Здесь можно добавить функционал для открытия изображения в модальном окне или новой вкладке
            window.open(src, '_blank');
        }
    </script>
</body>
</html>
