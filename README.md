
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сайт Игры</title>
    <style>
        /* Общие стили */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
            transition: background-color 0.3s, color 0.3s;
            background-image: url('images/background.png'); /* Путь к изображению */
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }
        /* Стили для темной темы */
        body.dark-mode {
            background-color: #333;
            color: #f4f4f4;
        }
        header {
            text-align: center;
            padding: 20px;
            background-color: rgba(0, 0, 0, 0.8);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
            color: white;
        }
        #logo {
            width: 200px;
            transition: transform 0.3s;
            cursor: pointer;
        }
        #logo:hover {
            transform: scale(1.05);
        }
        nav {
            margin: 20px 0;
            background-color: rgba(255, 255, 255, 0.2);
            padding: 10px;
            border-radius: 5px;
            display: flex;
            justify-content: center;
        }
        nav img {
            width: 50px;
            margin: 0 10px;
            cursor: pointer;
            transition: transform 0.3s;
            opacity: 0.7;
        }
        nav img:hover {
            transform: scale(1.1);
            opacity: 1;
        }
        main {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            background-color: rgba(0, 0, 0, 0.7);
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
            color: white;
            margin: 20px auto;
            max-width: 800px;
        }
        h1 {
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
        }
        h2 {
            margin-bottom: 15px;
        }
        .screenshot {
            width: 100%;
            max-width: 500px;
            margin-bottom: 10px;
            border-radius: 5px;
            display: none;
        }
        .screenshot.show {
            display: block;
        }
        #news {
            margin-top: 30px;
            width: 100%;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
        }
        .news-item {
            margin-bottom: 20px;
            padding: 15px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 5px;
        }
        .news-item h3 {
            margin-top: 0;
        }
        .comment-form {
            margin-top: 10px;
        }
        .comment-form textarea {
            width: 95%;
            padding: 5px;
            margin-bottom: 5px;
            border-radius: 3px;
            border: 1px solid #ccc;
        }
        .comment-form button {
            background-color: #5cb85c;
            color: white;
            padding: 8px 12px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
        .comments-section {
            margin-top: 15px;
        }
        .comment {
            padding: 10px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 5px;
            margin-bottom: 5px;
            color: white;
        }
        /* Footer Styles */
        footer {
            text-align: center;
            padding: 10px;
            background-color: rgba(0, 0, 0, 0.8);
            color: white;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
        /* Theme Toggle Button */
        #theme-toggle {
            background-color: #4CAF50;
            border: none;
            color: white;
            padding: 10px 20px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin: 4px 2px;
            cursor: pointer;
            border-radius: 5px;
            position: absolute;
            top: 15px;
            right: 20px;
        }
    </style>
</head>
<body>
    <header>
        <img id="logo" src="images (2).jpg" alt="Логотип игры">
        <nav>
            <img src="icon-menu.png" alt="Иконка 1" onclick="showImages('category1')">
            <img src="icon-menu.png" alt="Иконка 2" onclick="showImages('category2')">
            <img src="icon-menu.png" alt="Показать все" onclick="showImages('all')">
        </nav>
        <button id="theme-toggle">Сменить тему</button>
    </header>
    <main>
        <h1>Добро пожаловать в игру!</h1>
        <h2>Скриншоты игры</h2>
        <img class="screenshot category1" src="the-sims-5-chego-ozhidat-5.jpg" alt="Скриншот 1">
        <img class="screenshot category2" src="images (1).jpg" alt="Скриншот 2">
        <img class="screenshot category2" src="The_Sims_4_Screenshot_39.webp" alt="Скриншот 3">
        <!-- Раздел новостей -->
        <section id="news">
            <h2>Новости</h2>
            <div class="news-item">
                <h3>Обновление игры 5.2</h3>
                <p>Новые персонажи и функции</p>
                <div class="comments-section">
                    <h3>Комментарии:</h3>
                    <div class="comment">
                        <p>Отличная обнова! Спасибо разработчикам!</p>
                    </div>
                    <div class="comment">
                        <p>Есть небольшие баги, но в целом хорошо.</p>
                    </div>
                    <div class="comment-form">
                        <textarea id="commentText1" placeholder="Оставить комментарий"></textarea>
                        <button onclick="addComment(1)">Отправить</button>
                    </div>
                </div>
            </div>
            <div class="news-item">
                <h3>Турнир по игре</h3>
                <p>Объявляем о начале турнира с ценными призами! Регистрация открыта до 20.12.2023.</p>
                <div class="comments-section">
                    <h3>Комментарии:</h3>
                    <div class="comment">
                        <p>Участвую!</p>
                    </div>
                    <div class="comment-form">
                        <textarea id="commentText2" placeholder="Оставить комментарий"></textarea>
                        <button onclick="addComment(2)">Отправить</button>
                    </div>
                </div>
            </div>
        </section>
    </main>
    <script>
        function addComment(newsId) {
            const commentText = document.getElementById(`commentText${newsId}`).value;
            if (commentText.trim() === "") {
                alert("Введите комментарий!");
                return;
            }
            const newComment = document.createElement('div');
            newComment.classList.add('comment');
            newComment.innerHTML = `<p>${commentText}</p>`;
            const commentsSection = document.querySelector(`.news-item:nth-child(${newsId}) .comments-section`);
            commentsSection.insertBefore(newComment, commentsSection.querySelector('.comment-form'));
            document.getElementById(`commentText${newsId}`).value = "";
        }
        function showImages(category) {
            const screenshots = document.querySelectorAll('.screenshot');
            screenshots.forEach(img => {
                if (category === 'all' || img.classList.contains(category)) {
                    img.classList.add('show');
                } else {
                    img.classList.remove('show');
                }
            });
        }
        // Смена темы
        document.getElementById('theme-toggle').addEventListener('click', function() {
            document.body.classList.toggle('dark-mode');
            this.textContent = document.body.classList.contains('dark-mode') ? 'Светлая тема' : 'Темная тема';
        });
        // Инициализация отображения изображений
        showImages('all');
    </script>
    <title>Информация</title> 
<body>
    <h2>Информация</h2>
    <p>Это страница с дополнительной информацией. Здесь вы можете узнать больше о нашем проекте.</p>
    <p><a href="2part">глянуть</a></p>
</body>
