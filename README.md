<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Данил & Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Montserrat:wght@300;400;500&family=Cinzel&display=swap" rel="stylesheet">

    <style>
        :root { --main: #3b352d; }
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            font-family: 'Montserrat', sans-serif; 
            overflow-x: hidden;
        }

        /* Черная шторка для запуска на iPhone */
        #loader-curtain {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: #000; z-index: 9999;
            display: flex; align-items: center; justify-content: center;
            transition: opacity 1s ease; cursor: pointer;
        }
        #loader-curtain::after {
            content: 'ОТКРЫТЬ ПРИГЛАШЕНИЕ';
            color: #fff; font-family: 'Cinzel', serif;
            letter-spacing: 4px; font-size: 0.8em;
            border: 1px solid rgba(255,255,255,0.3); padding: 15px 30px;
        }

        /* Видео (нижний слой) */
        .video-bg {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100vh;
            z-index: 1; background: #000;
        }
        video { width: 100%; height: 100%; object-fit: cover; }

        /* Контейнер скролла */
        .main-scroll {
            position: relative;
            z-index: 100;
            width: 100%;
        }

        /* ФОТО СВЕРХУ (ПОЛНОЕ ПЕРЕКРЫТИЕ) */
        .hero-photo {
            width: 100%; height: 100vh;
            background-image: linear-gradient(to bottom, rgba(0,0,0,0.1), rgba(0,0,0,0.4)), 
                              url('https://raw.githubusercontent.com/noikhman/wedding/main/%E2%84%96999_159.JPG');
            background-size: cover; background-position: center;
            display: flex; 
            align-items: flex-end; /* Опускаем надпись вниз */
            justify-content: center;
            padding-bottom: 15vh; /* Расстояние имен от низа экрана */
            position: relative;
            z-index: 500; /* Гарантируем, что фото над видео */
            box-shadow: 0 15px 40px rgba(0,0,0,0.6);
        }

        .hero-photo h1 { 
            font-family: 'Playfair Display', serif; 
            color: #fff; font-size: clamp(2.4em, 8vw, 4em); 
            font-weight: 400; letter-spacing: 2px; text-align: center;
            text-shadow: 0 4px 20px rgba(0,0,0,0.8);
        }

        /* Место для видео при скролле */
        .video-gap { height: 85vh; background: transparent; }

        /* ИНФОРМАЦИЯ (ПОЛУПРОЗРАЧНАЯ КАРТОЧКА) */
        .info-section {
            padding: 40px 20px 120px;
            display: flex; justify-content: center;
            position: relative; z-index: 600;
        }

        .glass-card {
            background: rgba(255, 255, 252, 0.45); /* Тот самый полупрозрачный */
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            padding: 60px 30px; border-radius: 40px;
            text-align: center; width: 100%; max-width: 450px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.25);
        }

        .glass-card h2 {
            font-family: 'Playfair Display', serif; font-size: 1.8em;
            margin-bottom: 25px; font-style: italic; color: #1a1a1a;
        }

        .date-strip {
            background: var(--main); color: #fff;
            margin: 40px -30px; padding: 30px 10px;
        }
        .date-strip p {
            font-family: 'Cinzel', serif; font-size: 2em; letter-spacing: 3px;
        }

        .btn {
            display: inline-block; margin-top: 40px;
            padding: 18px 45px; background: var(--main);
            color: #fff; text-decoration: none;
            border-radius: 50px; text-transform: uppercase;
            font-size: 0.8em; letter-spacing: 2px; font-weight: 500;
        }

        @media (min-width: 1025px) {
            .glass-card { background: #fff; backdrop-filter: none; max-width: 500px; }
            .info-section { background: #fdfdfb; }
            .video-gap { display: none; }
        }
    </style>
</head>
<body>

    <div id="loader-curtain" onclick="startAll()"></div>

    <audio id="music" loop preload="auto">
        <source src="https://noikhman.github.io/wedding/Stephen%20Sanchez%20-%20Until%20I%20Found%20You%20(Piano%20Karaoke).mp3" type="audio/mpeg">
    </audio>

    <div class="video-bg">
        <video id="video" playsinline webkit-playsinline muted loop preload="auto">
            <source src="https://noikhman.github.io/wedding/video5350360388351334576.mp4" type="video/mp4">
        </video>
    </div>

    <div class="main-scroll">
        
        <section class="hero-photo">
            <h1>Данил & Ирина</h1>
        </section>

        <div class="video-gap"></div>

        <section class="info-section">
            <div class="glass-card">
                <h2>Дорогие и любимые!</h2>
                <p style="line-height: 1.8; font-size: 1.1em; color: #000; font-style: italic;">
                    Один из дней лета станет самым важным в нашей жизни.<br>
                    И мы хотим провести его вместе с вами.
                </p>
                
                <div class="date-strip">
                    <p>26 . 07 . 2026</p>
                    <p style="font-size: 0.8em; text-transform: uppercase; margin-top: 8px; letter-spacing: 2px;">Воскресенье • 16:30</p>
                </div>

                <div style="margin: 30px 0;">
                    <p style="font-family: 'Playfair Display', serif; font-size: 1.5em; font-weight: 700; color: #000;">Ресторан «Престиж»</p>
                    <p style="margin-top: 5px; font-weight: 500; color: #000;">г. Слободзея, ул. Фрунзе, 12</p>
                </div>

                <a href="https://maps.app.goo.gl/uX7Mv5V8V8D2" target="_blank" class="btn">Место проведения</a>
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
                setTimeout(() => { curtain.style.display = 'none'; }, 1000);
            }
            if (video) video.play();
            if (audio) {
                audio.volume = 0.4;
                audio.play();
            }
        }

        ['touchstart', 'click'].forEach(evt => {
            window.addEventListener(evt, startAll, {once: true});
        });
    </script>
</body>
</html>
