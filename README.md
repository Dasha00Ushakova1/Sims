<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сайт Игры</title>
    <style>

        body {
               background-image: url('icon-menu.png.jpg'); /* Укажите путь к Вашему изображению */
               background-size: cover; /* Растягиваем изображение на весь экран */
               background-position: center; /* Центрируем изображение */
               background-attachment: fixed; /* Фон остается фиксированным при прокрутке */
              
        }
        header {
            text-align: center;
            padding: 20px;
            background-color: rgba(0, 0, 0, 0.8);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
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

        /* Dark Mode Styles */
        body.dark-mode {
            background-color: #333;
            color: #f4f4f4;
        }

        body.dark-mode header {
            background-color: rgba(0, 0, 0, 0.9);
        }

        body.dark-mode main {
            background-color: rgba(0, 0, 0, 0.9);
        }

        body.dark-mode #news {
            background-color: rgba(0, 0, 0, 0.8);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        body.dark-mode .news-item {
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        
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
    <script>
        function showImages(category) {
            // Скрыть все скриншоты
            const screenshots = document.querySelectorAll('.screenshot');
            screenshots.forEach(img => img.classList.remove('show'));

            // Показать скриншоты в зависимости от категории
            if (category === 'all') {
                screenshots.forEach(img => img.classList.add('show')); // Показать все скриншоты
            } else if (category === 'category1') {
                screenshots[0].classList.add('show'); // Показать первый скриншот
            } else if (category === 'category2') {
                screenshots[1].classList.add('show'); // Показать второй скриншот
                screenshots[2].classList.add('show'); // Показать третий скриншот
            }
        }
    </script>
</head>
<body>
    <header>
        <img id="logo" src="images (2).jpg" alt="Логотип игры"> <!-- Логотип -->
        <nav>
            <img src="diamon.html.png" alt="Иконка 1" onclick="showImages('category1')"> <!-- Иконка 1 -->
            <img src="diamon.html.png" alt="Иконка 2" onclick="showImages('category2')"> <!-- Иконка 2 -->
            <img src="diamon.html.png" alt="Показать все" onclick="showImages('all')"> <!-- Иконка для показа всех
скриншотов -->

        </nav>
    </header>
    <main>
        <h1>Добро пожаловать в игру!</h1>
        <h2>Скриншоты игры</h2>
        <img class="screenshot" src="images (1).jpg" alt="Скриншот 1"> <!-- Скриншот 1 -->
        <img class="the-sims-5-chego-ozhidat-5.jpg" alt="Скриншот 2"> <!-- Скриншот 2 -->
        <img class="screenshot" src="C:\Users\Студент\Downloads\images (1).jpg" alt="Скриншот 3"> <!-- Скриншот 3 -->
    </main>
</body>
</html>
