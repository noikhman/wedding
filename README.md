<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Приглашение: Данил и Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&display=swap" rel="stylesheet">

    <style>
        :root { --main: #3b352d; }
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            font-family: 'Great Vibes', cursive; /* Единственный шрифт для всего */
            overflow-x: hidden;
        }

        /* Начальный экран */
        #loader-curtain {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: #000; z-index: 10000;
            display: flex; align-items: center; justify-content: center;
            transition: opacity 0.8s ease; cursor: pointer;
        }
        #loader-curtain::after {
            content: 'ОТКРЫТЬ';
            color: #fff; font-family: 'Great Vibes', cursive;
            letter-spacing: 2px; font-size: 1.5em; /* Шрифт Great Vibes требует большего размера */
            padding: 15px 40px;
        }

        /* Видео */
        .video-fixed {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100vh;
            z-index: 1; background: #000;
        }
        video { width: 100%; height: 100%; object-fit: cover; }

        .content-wrapper {
            position: relative;
            z-index: 100;
            width: 100%;
        }

        /* Фото-шторка */
        .hero-photo {
            width: 100%; height: 100vh;
            background-image: linear-gradient(to bottom, rgba(0,0,0,0) 40%, rgba(0,0,0,0.7) 100%), 
                              url('photo.jpg');
            background-size: cover; background-position: center;
            display: flex; align-items: flex-end; justify-content: center;
            padding-bottom: 15vh;
        }

        .hero-photo h1 { 
            color: #fff; font-size: clamp(3em, 12vw, 6em); /* Увеличен размер для cursive */
            font-weight: 400; text-align: center;
            text-shadow: 0 4px 20px rgba(0,0,0,0.9);
            font-family: 'Great Vibes', cursive;
            text-transform: none; /* Каллиграфия не любит капс */
        }

        .gap { height: 90vh; background: transparent; }

        .info-section {
            padding: 20px 15px 100px;
            display: flex; justify-content: center;
        }

        /* Прозрачная карточка */
        .glass-card {
            background: rgba(255, 255, 253, 0.45);
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            padding: 60px 25px; border-radius: 40px;
            text-align: center; width: 100%; max-width: 450px;
            box-shadow: 0 25px 50px rgba(0,0,0,0.3);
            border: none; /* Убрана граница */
        }

        /* Блок даты без полосок */
        .date-box {
            color: #000; /* Цвет текста изменен, т.к. убрали фон */
            margin: 30px 0; /* Убраны отрицательные отступы */
            padding: 0;
            background: transparent; /* Убран фон */
        }

        /* Текстовые блоки */
        .main-text {
            font-size: 1.8em; /* Увеличен размер */
            line-height: 1.4; 
            color: #000; 
            font-family: 'Great Vibes', cursive;
            margin-bottom: 25px;
            text-align: center;
        }

        .location-box {
            margin-top: 30px;
            text-align: center;
        }

        .location-box p:first-child {
            font-size: 2.2em; /* Увеличен размер */
            color: #000;
            margin-bottom: 5px;
        }

        .location-box p:last-child {
            font-size: 1.5em; /* Увеличен размер */
            color: #000;
        }

        .btn {
            display: inline-block; margin-top: 35px;
            padding: 15px 40px; background: var(--main);
            color: #fff; text-decoration: none;
            border-radius: 50px; text-transform: none; /* Без капса */
            font-size: 1.6em; /* Увеличен размер текста на кнопке */
            font-family: 'Great Vibes', cursive;
        }

        @media (min-width: 1025px) {
            .video-fixed { width: 45%; }
            .content-wrapper { width: 55%; margin-left: 45%; background: #fdfdfb; }
            .gap { display: none; }
            .glass-card { background: #fff; backdrop-filter: none; box-shadow: none; border: none; }
        }
    </style>
</head>
<body>

    <div id="loader-curtain" onclick="startAll()"></div>

    <audio id="music" loop preload="auto">
        <source src="https://raw.githubusercontent.com/noikhman/wedding/main/Stephen%20Sanchez%20-%20Until%20I%20Found%20You%20(Piano%20Karaoke).mp3" type="audio/mpeg">
    </audio>

    <div class="video-fixed">
        <video id="video" playsinline webkit-playsinline muted loop preload="auto">
            <source src="https://raw.githubusercontent.com/noikhman/wedding/main/video5350360388351334576.mp4" type="video/mp4">
        </video>
    </div>

    <div class="content-wrapper">
        <section class="hero-photo">
            <h1>Данил & Ирина</h1>
        </section>

        <div class="gap"></div>

        <section class="info-section">
            <div class="glass-card">
                <p style="font-size: 1.4em; margin-bottom: 10px; color: #333;">Save the Date</p>
                
                <h2 style="font-size: 2.8em; margin-bottom: 20px; font-weight: 400; text-align: center; white-space: nowrap;">Дорогие и любимые!</h2>
                
                <p class="main-text">
                    Один из дней лета станет самым важным в нашей жизни. <br>
                    Мы хотим провести его вместе с вами.
                </p>
                
                <div class="date-box">
                    <p style="font-size: 3em;">26.07.2026</p>
                    <p style="font-size: 1.8em; margin-top: 5px;">Воскресенье • 16:30</p>
                </div>

                <div class="location-box">
                    <p>Ресторан «Престиж»</p>
                    <p>г. Слободзея, ул. Фрунзе, 12</p>
                </div>

                <a href="https://maps.app.goo.gl/P6jM7bA4wF6P2V8s8" target="_blank" class="btn">Место проведения</a>
            </div>
        </section>
    </div>

    <script>
        const audio = document.getElementById('music');
        const video = document.getElementById('video');
        const curtain = document.getElementById('loader-curtain');

        function startAll() {
            if (curtain) {
                curtain.style.opacity = '0';
                setTimeout(() => { curtain.style.display = 'none'; }, 800);
            }
            if (video) video.play();
            if (audio) {
                audio.volume = 0.5;
                audio.play();
            }
        }
        window.addEventListener('click', startAll, {once: true});
        window.addEventListener('touchstart', startAll, {once: true});
    </script>
</body>
</html>
