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
            /* background-image: url('\\192.168.2.90\kb6\студент\61f17c1a9a4f444bf5ec553b58a45d70.png'); */ /* Укажите путь к Вашему изображению */
            background-image: url('images/background.png'); /* Replaced absolute with relative path */
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
        /* Стили для темной темы */
        body.dark-mode header {
            background-color: rgba(0, 0, 0, 0.9);
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
            display: flex; /* Added */
            justify-content: center; /* Added */
        }
        nav img {
            width: 50px;
            margin: 0 10px;
            cursor: pointer;
            transition: transform 0.3s;
            opacity: 0.7; /* Slightly dimmed */
        }
        nav img:hover {
            transform: scale(1.1);
            opacity: 1; /* Fully visible on hover */
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
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
        }
        h2 {
            margin-bottom: 15px;
        }
        /* Correctly hide and show screenshots */
        .screenshot {
            width: 100%; /* Make screenshots responsive */
            max-width: 500px; /* Set a maximum width */
            margin-bottom: 10px;
            border-radius: 5px;
            display: none; /* Initially hide all screenshots */
        }
        .screenshot.show {
            display: block; /* Show screenshots when they have the 'show' class */
        }
        @media (max-width: 768px) {
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
            .screenshot {
                width: 80%; /* Адаптивная ширина скриншотов */
                max-width: none;  /* Remove max-width on small screens */
            }
        }
        #news {
            margin-top: 30px;
            width: 100%;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
        }
        /* Стили для темной темы */
        body.dark-mode #news {
            background-color: rgba(0, 0, 0, 0.8);
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
            background-color:#008000;;
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
            position: absolute; /* Абсолютное позиционирование */
            top: 15px; /* Отступ сверху */
            right: 20px; /* Отступ справа */
        }
        /* Added to style the news image */
        .news-image {
            width: 100%;
            max-width: 300px;
            height: auto;
            border-radius: 5px;
            margin-bottom: 10px;
        }
     button {
    transition: background 0.3s ease-in-out;
}
button:hover {
    background: #ff6600;
    color: white;
}
@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
.modal {
    animation: fadeIn 0.5s ease-in-out;
}
    </style>
<head>
<body>
        <img id="logo" src="images (2).jpg" alt="Логотип игры">
   <nav>
            <img src="icon-menu.png.jpg" alt="Иконка 1" onclick="showImages('category1')">
            <img src="icon-menu.png.jpg" alt="Иконка 2" onclick="showImages('category2')">
            <img src="icon-menu.png.jpg" alt="Показать все" onclick="showImages('all')">
   <nav>
        <button id="theme-toggle">Сменить тему</button>
    <header>
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
<body>
     <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Комментарии</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            position: relative; /* Позволяет использовать абсолютное позиционирование для дочерних элементов */
        }
    </style>
    <div class="news-item">
        <h3>Обновление игры</h3>
        <p>Выпущено новое обновление с улучшениями и исправлениями.</p>
        <div class="comments-section">
            <h4>Комментарии:</h4>
            <h4>Комментарии:</h4>
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
        <h5>Турнир по игре</h5>
        <p>Объявляем о начале турнира с ценными призами! Регистрация открыта до 20.12.2025</p>
        <div class="comments-section">
            <h4>Комментарии:</h4>
            <div class="comment">
                <p>Участвую!</p>
            </div>
            <div class="comment-form">
                <textarea id="commentText2" placeholder="Оставить комментарий"></textarea>
                <button onclick="addComment(2)">Отправить</button>
            </div>
        </div>
    </div>
    <script>
        function addComment(newsId) {
            // Получаем текст комментария в зависимости от ID новости
            const commentText = document.getElementById(`commentText${newsId}`).value;
            if (commentText.trim() === "") {
                alert("Введите комментарий!");
                return;
            }
            // Создаем новый элемент для комментария
            const newComment = document.createElement('div');
            newComment.classList.add('comment');
            newComment.innerHTML = `<p>${commentText}</p>`;
            // Находим секцию комментариев для соответствующей новости
            const commentsSection = document.querySelector(`.news-item:nth-child(${newsId}) .comments-section`);
            commentsSection.insertBefore(newComment, commentsSection.querySelector('.comment-form'));
            // Очищаем текстовое поле
            document.getElementById(`commentText${newsId}`).value = "";
        }
    <script>
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
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Информация</title>
</head>
<body>
    <h7>Информация</h7>
    <p>Это страница с дополнительной информацией. Здесь вы можете узнать больше о нашем проекте.</p>
    <p><a href="2part">глянуть</a></p>
</body>




