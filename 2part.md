
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>О игре</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #245c2e;
            color: #333;
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
            background: #fff;
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
        }
        .feedback-form button {
            background: #28a745;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            transition: background 0.3s;
        }
        .feedback-form button:hover {
            background: #218838;
        }
        .faq {
            margin-top: 40px;
            animation: fadeIn 1s;
        }
        .faq-item {
            margin: 10px 0;
            cursor: pointer;
        }
        .faq-answer {
            display: none;
            padding: 10px;
            background: #f9f9f9;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <h1>О нашей игре</h1>
    <div class="game-description">
        <p>Здесь вы можете узнать больше о нашей увлекательной игре, которая погружает вас в мир приключений и захватывающих событий!</p>
        <img src="images/game_image.jpg" alt="Изображение из игры" style="width: 100%; max-width: 600px; display: block; margin: 0 auto;">
        <h2>Смотрите наш трейлер</h2>
        <video width="100%" controls>
            <source src="10 ОБЯЗАТЕЛЬНЫХ модов для СИМС 4 - смотреть онлайн в поиске Яндекса по Видео - Google Chrome 2025-03-10 21-14-52.mp4" type="video/mp4">
            Ваш браузер не поддерживает видео.
        </video>
    </div>
    <h2>Галерея</h2>
    <div class="gallery">
        <img src="1517948329_38-sims-4-forgotten-hollow.jpg" alt="Галерея 1" onclick="openImage(this.src)">
        <img src="1642847466_vampire_bloodlines.jpg" alt="Галерея 2" onclick="openImage(this.src)">
        <img src="2021-04-29_174854.jpg" alt="Галерея 3" onclick="openImage(this.src)">
        <img src="DfsBFDgTBV4BXDgnebjQRA.jpg" alt="Галерея 4" onclick="openImage(this.src)">
        <img src="e5804d18740c39a19fb23004b1092.jpeg" alt="Галерея 5" onclick="openImage(this.src)">
    </div>
    <div class="faq">
        <h2>Часто задаваемые вопросы (FAQ)</h2>
        <div class="faq-item" onclick="toggleFAQ(this)">
            <strong>Вопрос 1: Как скачать игру?</strong>
            <div class="faq-answer">Ответ: Вы можете скачать игру на нашем официальном сайте в разделе "Скачать".</div>
        <div>
        <div class="faq-item" onclick="toggleFAQ(this)">
            <strong>Вопрос 2: Есть ли мультиплеер?</strong>
            <div class="faq-answer">Ответ: Да, игра поддерживает мультиплеер для до 4-х игроков.</div>
        <div>
        <div class="faq-item" onclick="toggleFAQ(this)">
            <strong>Вопрос 3: Какой минимальный системный требования?</strong>
            <div class="faq-answer">Ответ: Минимальные требования: 4 ГБ ОЗУ, процессор 2.0 ГГц, видеокарта с 1 ГБ видеопамяти.</div>
        <div>
        </div>
    <script>
    </div class="feedback-form">
        <h3>Обратная связь</h3>
        <p>Не нашли ответа на свой вопрос? Пишите, мы поможем!<p>
        <input type="text" id="name" placeholder="Ваше имя" required>
        <input type="email" id="email" placeholder="Ваш Email" required>
        <textarea id="message" rows="4" placeholder="Ваше сообщение" required></textarea>
        <button id="send-feedback">Отправить</button>
        <p id="feedback-message" style="color: green; display: none;">Ваше сообщение принято! Скоро мы на него ответим.</p>
    </div>
        function sendFeedback() {
            document.getElementById('feedback-message').style.display = 'block';
        }
        function toggleFAQ(element) {
            const answer = element.querySelector('.faq-answer');
            answer.style.display = answer.style.display === 'block' ? 'none' : 'block';
        }
        function openImage(src) {
            const imgWindow = window.open("", "_blank");
            imgWindow.document.write(`<img src="${src}" style="width:100%;max-width:600px;">`);
        }
        document.getElementById('send-feedback').addEventListener('click', function() {
            sendFeedback();
            // Здесь можно добавить код для отправки данных на сервер
        });
    </script>

