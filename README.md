
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
            color: #050505;
            transition: background-color 0.3s, color 0.3s;
            background-image: url('photo_5370915183163208021_x.jpg'); /* Путь к изображению */
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            box-shadow: none;
        }
        /* Стили для темной темы */
        body.dark-mode {
            background-color: #050505;
            color: #f4f4f4;
            box-shadow: none;
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
        h1, h2 {
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
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
            border:1px solid rgba(255, 255, 255, 0.2);
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
        /* Модальное окно */
        .modal {
            display: none; 
            position: fixed; 
            z-index: 1; 
            left: 0;
            top: 0;
            width: 100%; 
            height: 100%; 
            overflow: auto; 
            background-color: rgba(0,0,0,0.4) ; 
            padding-top: 60px;
        }
        .modal-content {
            background-color:#008000	;
            margin: 5% auto; 
            padding: 20px;
            border: 1px solid #888;
            width: 80%; 
             box-shadow: none;
        }
        .close {
            color: #006400;
            float: right;
            font-size: 38px;
            font-weight: bold;
        }
        .close:hover,
        .close:focus {
            color: black;
            color: #0099ef;
            text-decoration: underline;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <header>
        <img id="logo" src="images (2).jpg" alt="Логотип игры" onclick="openModal()">
        <nav>
            <img src="aaaaaaaaaaaaaaaaaaaaaaaaaaaaaa-Photoroom.png" alt="Иконка 1" onclick="showImages('category1')">
            <img src="aaaaaaaaaaaaaaaaaaaaaaaaaaaaaa-Photoroom.png" alt="Иконка 2" onclick="showImages('category2')">
            <img src="aaaaaaaaaaaaaaaaaaaaaaaaaaaaaa-Photoroom.png" alt="Показать все" onclick="showImages('all')">
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
    <div id="commentList1">
        <div class="comment">
            <p>Отличная обнова! Спасибо разработчикам!</p>
        </div>
        <div class="comment">
            <p>Есть небольшие баги, но в целом хорошо.</p>
        </div>
        <div class="comment">
            <p>Спааать хочу</p>
        </div>
    </div>
    <div class="comment-form">
        <textarea id="commentText1" placeholder="Оставить комментарий"></textarea>
        <button onclick="addComment(1)">Отправить</button>
    </div>
</div>
</div>
<div class="news-item">
    <h3>Турнир по игре</h3>
    <p>Объявляем о начале турнира с ценными призами! Регистрация открыта до конца месяца.</p>
    <div class="comments-section">
        <h3>Комментарии:</h3>
        <div id="commentList2">
            <div class="comment">
                <p>Не могу дождаться турнира! Участвую!</p>
            </div>
        </div>
        <div class="comment-form">
            <textarea id="commentText2" placeholder="Оставить комментарий"></textarea>
            <button onclick="addComment(2)">Отправить</button>
        </div>
    </div>
    <script>
     function addComment(section) {
    let commentText;
    if (section === 1) {
        commentText = document.getElementById('commentText1').value;
        document.getElementById('commentText1').value = ''; // Очистить текстовое поле
    } else {
        commentText = document.getElementById('commentText2').value;
        document.getElementById('commentText2').value = ''; // Очистить текстовое поле
    }
    const commentList = document.getElementById(`commentList${section}`);
    const newComment = document.createElement('div');
    newComment.className = 'comment';
    newComment.innerHTML = `<p>${commentText}</p>`;
    commentList.appendChild(newComment);
}
</div>
        </section>
    </main>
    <!-- Модальное окно -->
    <div id="myModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal()">&times;</span>
            <h2>Благодарим за посещение сайта!</h2>
            <p>Надеюсь,что вам понравится игра</p>
        </div>
    </div>
    <script>
        // Переключение темы
        document.getElementById('theme-toggle').onclick = function() {
            document.body.classList.toggle('dark-mode');
        };
        // Модальное окно
        function openModal() {
            document.getElementById("myModal").style.display = "block";
        }
        function closeModal() {
            document.getElementById("myModal").style.display = "none";
        }
        // Добавление комментариев
        function addComment(newsId) {
            const commentText = document.getElementById(`commentText${newsId}`).value;
            if (commentText) {
                const commentSection = document.querySelector(`.news-item:nth-child(${newsId}) .comments-section`);
                const newComment = document.createElement('div');
                newComment.classList.add('comment');
                newComment.innerHTML = `<p>${commentText}</p>`;
                commentSection.appendChild(newComment);
                document.getElementById(`commentText${newsId}`).value = ''; // Очистить текстовое поле
            }
        }
        // Показать изображения в зависимости от категории
        function showImages(category) {
            const screenshots = document.querySelectorAll('.screenshot');
            screenshots.forEach(screenshot => {
                if (category === 'all' || screenshot.classList.contains(category)) {
                    screenshot.classList.add('show');
                } else {
                    screenshot.classList.remove('show');
                }
            });
        }
    </script>
    <title>Информация</title> 
<body>
    <h1>Информация</h1>
    <p>Это страница с дополнительной информацией. Здесь вы можете узнать больше о нашем проекте.</p>
    <p><a href="2part" style="color: #7FFF00; font-size: 20px;"> ----> глянуть</a></p>
</body>

