
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
            background-image: url(''); /* Укажите путь к Вашему изображению */
            background-size: cover; /* Растягиваем изображение на весь экран */
            background-position: center; /* Центрируем изображение */
            background-attachment: fixed; /* Фон остается фиксированным при прокрутке */
                }
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
        /* Стили для темной темы */
        body.dark-mode header {
            background-color: rgba(0, 0, 0, 0.9);
        }
        #logo {
            width: 200px; /* Размер логотипа */
            transition: transform 0.3s;
            cursor: pointer;
        }
        #logo:hover {
            transform: scale(1.05); /* Увеличение логотипа при наведении */
        }
        nav {
            margin: 20px 0;
            background-color: rgba(255, 255, 255, 0.2); /* Полупрозрачный фон для навигации */
            padding: 10px;
            border-radius: 5px;
        }
        nav img {
            width: 50px; /* Размер иконок меню */
            margin: 0 10px;
            cursor: pointer;
            transition: transform 0.3s;
            opacity: 0.7;
        }
        nav img:hover {
            transform: scale(1.1);
            opacity: 1;
        }
        .active {
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
        /* Стили для темной темы */
        body.dark-mode main {
            background-color: rgba(0, 0, 0, 0.9);
        }
        h1 {
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7); /* Тень для заголовка */
        }
        h2 {
            margin-bottom: 15px;
        }
        .screenshot {
            width: 300px; /* Размер скриншотов */
            margin: 10px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
            display: none; /* Скрыть скриншоты по умолчанию */
        }
        .screenshot.show {
            display: block; /* Показать скриншоты при добавлении класса show */
        }
        @media (max-width: 768px) {
            #logo {
                width: 150px; /* Уменьшение размера логотипа на мобильных устройствах */
            }
            .screenshot {
                width: 80%; /* Адаптивная ширина скриншотов */
            }
        }
        #news {
            margin-top: 30px;
            width: 100%;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.2);
        border-radius: 5px;
    }
    /* Стили для темной темы */
    body.dark-mode .news-item {
        border: 1px solid rgba(255, 255, 255, 0.1);
    }
  .news-item {
            margin-bottom: 20px;
            padding: 15px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 5px;
        }
        /* Стили для темной темы */
        body.dark-mode .news-item {
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        .news-item h3 {
            margin-top: 0;
        }
        /* Comment Form Styles */
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
        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1;
        }
        .modal-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: white;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .close {
            position: absolute;
            top: 0;
            right: 0;
            padding: 10px;
            cursor: pointer;
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
        }
        /* Responsive Design */
        @media (max-width: 768px) {
            header {
                padding: 10px;
            }
            #logo {
                width: 150px;
            }
            nav img {
                width: 40px;
                margin: 0 5px;
            }
            main {
                padding: 10px;
                margin: 10px;
            }
        }
    </style>
</head>
<body>
    <header>
        <img id="logo" src="images (2).jpg" alt="Логотип игры"> <!-- Логотип -->
        <nav>
            <img src="diamon.html.png" alt="Иконка 1" onclick="showImages('category1')"> <!-- Иконка 1 -->
            <img src="diamon.html.png" alt="Иконка 2" onclick="showImages('category2')"> <!-- Иконка 2 -->
            <img src="diamon.html.png" alt="Показать все" onclick="showImages('all')"> <!-- Иконка для показа всех скриншотов -->
        </nav>
        <button id="theme-toggle">Сменить тему</button> <!-- Кнопка переключения темы -->
    </header>
    <main>
        <h1>Добро пожаловать в игру!</h1>
        <h2>Скриншоты игры</h2>
        <img class="screenshot show" src="screenshot1.jpg" alt="Скриншот 1">
        <img class="screenshot" src="screenshot2.jpg" alt="Скриншот 2">
        <img class="screenshot" src="screenshot3.jpg" alt="Скриншот 3">
        <div class="comments-section">
            <h3>Комментарии</h3>
            <div class="comment-form">
                <textarea placeholder="Ваш комментарий..."></textarea>
                <button onclick="addComment()">Отправить</button>
            </div>
            <div class="comment">
                <strong>Пользователь1:</strong> Отличная игра!
            </div>
            <div class="comment">
                <strong>Пользователь2:</strong> Жду выхода новой версии!
            </div>
        </div>
        <div id="news">
            <h2>Новости</h2>
            <div class="news-item">
                <h3>Обновление 1.0</h3>
                <p>Мы рады сообщить о выходе первого обновления игры, которое добавляет новые уровни и персонажей!</p>
            </div>
            <div class="news-item">
                <h3>Скоро в продаже!</h3>
                <p>Наша игра будет доступна для покупки с 1 декабря. Не пропустите!</p>
            </div>
        </div>
    </main>
    <footer>
        <p>&copy; 2023 Ваша Игра. Все права защищены.</p>
    </footer>
    <script>
        // Переключение темы
        const themeToggle = document.getElementById('theme-toggle');
        themeToggle.onclick = function() {
            document.body.classList.toggle('dark-mode');
        };
        // Функция для показа изображений по категориям
        function showImages(category) {
            const screenshots = document.querySelectorAll('.screenshot');
            screenshots.forEach(img => img.classList.remove('show'));
            if (category === 'all') {
                screenshots.forEach(img => img.classList.add('show'));
            } else {
                // Здесь можно добавить логику для показа изображений по категориям
                alert('Показать изображения категории: ' + category);
            }
        }
        // Функция для добавления комментария
        function addComment() {
            const textarea = document.querySelector('.comment-form textarea');
            const commentText = textarea.value.trim();
            if (commentText) {
                const commentSection = document.querySelector('.comments-section');
                const newComment = document.createElement('div');
                newComment.classList.add('comment');
                newComment.innerHTML = `<strong>Вы:</strong> ${commentText}`;
                commentSection.appendChild(newComment);
                textarea.value = ''; // Очистить поле ввода
            } else {
                alert('Пожалуйста, введите комментарий.');
            }
        }
    
</body>
</html>
