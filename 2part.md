
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Галерея и FAQ</title>
    <style>
        /* Стили для галереи изображений */
        .gallery {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            margin-bottom: 20px;
        }
        .thumbnail {
            width: 100%;
            cursor: pointer;
            transition: transform 0.2s;
        }
        .thumbnail:hover {
            transform: scale(1.05);
        }
        #full-image {
            width: 500px;
            display: none; /* Скрываем изображение по умолчанию */
            margin-top: 20px;
        }
        .hidden {
            display: none;
        }
        /* Стили для FAQ */
        details {
            margin-bottom: 10px;
            cursor: pointer;
        }
        summary {
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Галерея изображений</h1>
    <div class="gallery">
        <img src="img1.jpg" class="thumbnail" alt="Изображение 1">
        <img src="img2.jpg" class="thumbnail" alt="Изображение 2">
        <img src="img3.jpg" class="thumbnail" alt="Изображение 3">
        <img src="img4.jpg" class="thumbnail" alt="Изображение 4">
        <img src="img5.jpg" class="thumbnail" alt="Изображение 5">
        <img src="img6.jpg" class="thumbnail" alt="Изображение 6">
    </div>
    <img id="full-image" class="hidden" alt="Увеличенное изображение">
    <script>
        // Добавление обработчиков событий для увеличения изображений
        document.querySelectorAll('.thumbnail').forEach(img => {
            img.addEventListener('click', function() {
                document.getElementById('full-image').src = this.src;
                document.getElementById('full-image').classList.remove('hidden');
            });
        });
    </script>
    <h2>Часто задаваемые вопросы (FAQ)</h2>
    <details>
        <summary>Какие системные требования у игры?</summary>
        <p>Минимальные требования: 8GB RAM, GTX 1050, 50GB свободного места.</p>
    </details>
    <details>
        <summary>Как установить игру?</summary>
        <p>Скачайте установочный файл с нашего сайта и следуйте инструкциям на экране.</p>
    </details>
    <details>
        <summary>Есть ли мультиплеер в игре?</summary>
        <p>Да, игра поддерживает мультиплеерный режим. Вы можете играть с друзьями онлайн.</p>
    </details>
     <h2>О нашей игре</h2>
<p>Это увлекательная компьютерная игра в жанре RPG с открытым миром...</p>
<img src="фооооооон.jpg" alt="Изображение из игры">
<iframe width="200" height="100" src="10 ОБЯЗАТЕЛЬНЫХ модов для СИМС 4 - смотреть онлайн в поиске Яндекса по Видео - Google Chrome 2025-03-10 21-14-52.mp4"></iframe>
<form id="contact-form">
    <label>Имя: <input type="text" id="name"></label>
    <label>Email: <input type="email" id="email"></label>
    <label>Сообщение: <textarea id="message"></textarea></label>
    <button type="submit">Отправить</button>
</form>
<p id="response"></p>
<script>
    document.getElementById('contact-form').addEventListener('submit', function(event) {
        event.preventDefault();
        document.getElementById('response').innerText = "Форма отправлена!";
    });
</script>
   



