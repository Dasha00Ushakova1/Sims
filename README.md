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
        /* Added to style the news image */
        .news-image {
            width: 100%;
            max-width: 300px;
            height: auto;
            border-radius: 5px;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <header>
        <img id="logo" src="images (2).jpg" alt="Логотип игры">
        <nav>
            <img src="icon-menu.png.jpg" alt="Иконка 1" onclick="showImages('category1')">
            <img src="icon-menu.png.jpg" alt="Иконка 2" onclick="showImages('category2')">
            <img src="icon-menu.png.jpg" alt="Показать все" onclick="showImages('all')">
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
                <h3>Обновление 1.0</h3>
                <p>Вышло новое обновление с улучшениями графики и новыми уровнями!</p>
                <div class="comments-section">
                 <h4>Комментарии:</h4>
                    <div class="comment">игрок1: шикарное обновление!</div>
                    <div class="comment">игрок2: очень понравилось!</div>
                </div>
                <form class="comment-form" onsubmit="addComment(event)">
                    <input type="text" id="comment-name" placeholder="Ваше имя" required>
                    <textarea id="comment-text" placeholder="Ваш комментарий" required></textarea>
                    <button type="submit">Отправить</button>
                </form>
                </div>
                    <h5>О нашей игре</h5>
<p>Это увлекательная компьютерная игра в жанре RPG с открытым миром...</p>
<img src="фооооооон.jpg" alt="Изображение из игры">
<iframe width="350" height="200" src="https://www.google.com/search?sca_esv=715d5d5656887f13&sxsrf=AHTn8zr7xhVj8QY-hSFSYT8T9Hl_UU9sNg:1741629581499&q=%D0%BB%D1%8E%D0%B1%D0%BE%D0%B5+%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%BE%D0%B5+%D0%B2%D0%B8%D0%B4%D0%B5%D0%BE+%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D0%BE%D0%B5+%D0%BC%D0%BE%D0%B6%D0%BD%D0%BE+%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D1%8C+%D0%B4%D0%BB%D1%8F+%D1%81%D0%B0%D0%B9%D1%82%D0%B0+%D0%BF%D1%80%D0%BE+Sims&udm=7&fbs=ABzOT_DL2zxtWSwAPDvmPsBiplySanC2Fp1BA92E3BjBhFI5ooTADZI2jNIWY1aS9xSWvLrxGlhQYDV4so0NhhPHXzt-lT2wW0HN8TyVIyvLc5K6OQKleU8ECe0IYI89qz66QbEU9S7nQfuT3phfENd9gLjFxvlA7jLK_6AKSS6JdPc25fKMId-PxCteik5uPa6BjigvCy5ZzoJUDPw1gj0a_Xmg3Oionm7MBk7FoZ0v2f00h0oJqHI0HNZmNhF7sxtPMZnxauFJ&sa=X&ved=2ahUKEwjxl6Tki4CMAxWXHXcKHR3IECsQtKgLegQIFxAB&biw=1920&bih=879&dpr=1#fpstate=ive&vld=cid:5c78e054,vid:A6L4srRINcU,st:0"></iframe>
    <!-- Модальное окно -->
    <div id="myModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal()">&times;</span>
            <p>Добро пожаловать на сайт нашей игры!</p>
        </div>
    </div>
    <script>
        function showImages(category) {
            const screenshots = document.querySelectorAll('.screenshot');
            screenshots.forEach(img => img.classList.remove('show')); // Hide all
            if (category === 'all') {
                screenshots.forEach(img => img.classList.add('show'));
            } else if (category === 'category1') {
                const category1Screenshots = document.querySelectorAll('.category1');
                category1Screenshots.forEach(img => img.classList.add('show'));
            } else if (category === 'category2') {
                const category2Screenshots = document.querySelectorAll('.category2');
                category2Screenshots.forEach(img => img.classList.add('show'));
            }
        }
        document.getElementById('theme-toggle').addEventListener('click', function() {
            document.body.classList.toggle('dark-mode');
        });
        document.getElementById('logo').addEventListener('click', function() {
            document.getElementById('myModal').style.display = "block";
        });
        function closeModal() {
            document.getElementById('myModal').style.display = "none";
        }
        window.onclick = function(event) {
            let modal = document.getElementById('myModal');
            if (event.target == modal) {
                modal.style.display = "none";
            }
        }
        // Функция для добавления комментария
function addComment(event) {
    event.preventDefault(); // Предотвращаем стандартное поведение формы
    // Получаем значения имени и текста комментария
    const name = document.getElementById('comment-name').value;
    const text = document.getElementById('comment-text').value;
    // Создаем объект комментария
    const comment = {
        name: name,
        text: text
    };
    // Получаем существующие комментарии из локального хранилища
    const comments = JSON.parse(localStorage.getItem('comments')) || [];
    // Добавляем новый комментарий в массив
    comments.push(comment);
    // Сохраняем обновленный массив комментариев в локальное хранилище
    localStorage.setItem('comments', JSON.stringify(comments));
    // Очищаем поля ввода
    document.getElementById('comment-name').value = '';
    document.getElementById('comment-text').value = '';
    // Обновляем отображение комментариев
    displayComments();
}

function displayComments() {
    const commentsSection = document.querySelector('.comments-section');
    commentsSection.innerHTML = '<h4>Комментарии:</h4>'; // Сбрасываем содержимое
    const comments = JSON.parse(localStorage.getItem('comments')) || [];
    comments.forEach(comment => {
        const commentDiv = document.createElement('div');
        commentDiv.classList.add('comment');
        commentDiv.textContent = `${comment.name}: ${comment.text}`;
        commentsSection.appendChild(commentDiv);
    });
}
window.onload = displayComments;

</body>
</html>
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
<div class="gallery">
    <img src="img1.jpg" class="thumbnail">
    <img src="img2.jpg" class="thumbnail">
</div>
<img id="full-image" class="hidden">

<script>
    document.querySelectorAll('.thumbnail').forEach(img => {
        img.addEventListener('click', function() {
            document.getElementById('full-image').src = this.src;
            document.getElementById('full-image').classList.remove('hidden');
        });
    });
</script>

<style>
    .gallery { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
    .thumbnail { width: 100px; cursor: pointer; }
    #full-image { width: 500px; display: block; }
    .hidden { display: none; }
</style>
