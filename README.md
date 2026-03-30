<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Данил & Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300&family=Montserrat:wght@200;300&family=Cinzel&display=swap" rel="stylesheet">

    <style>
        :root { --main: #3b352d; --gold: #b89a67; }
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            font-family: 'Cormorant Garamond', serif; 
            overflow-x: hidden;
        }

        /* Черный экран активации */
        #loader-curtain {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: #000; z-index: 9999;
            display: flex; align-items: center; justify-content: center;
            transition: opacity 1.2s ease; cursor: pointer;
        }
        #loader-curtain::after {
            content: 'ОТКРЫТЬ';
            color: #fff; font-family: 'Cinzel', serif;
            letter-spacing: 5px; font-size: 0.7em;
            border: 1px solid rgba(255,255,255,0.2); padding: 12px 35px;
        }

        /* СЛОЙ 1: ВИДЕО (ЗАФИКСИРОВАНО ВНИЗУ) */
        .video-bg {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100vh;
            z-index: 10; background: #000;
        }
        video { width: 100%; height: 100%; object-fit: cover; }

        /* СЛОЙ 2: ВЕСЬ СКРОЛЛ-КОНТЕНТ (ПОВЕРХ ВИДЕО) */
        .page-content {
            position: relative;
            z-index: 20; /* Выше видео */
            width: 100%;
        }

        /* ГЛАВНОЕ ФОТО (ПЕРЕКРЫВАЕТ ВСЁ) */
        .hero-section {
            width: 100%; height: 100vh;
            background-image: linear-gradient(to bottom, rgba(0,0,0,0) 60%, rgba(0,0,0,0.6) 100%), 
                              url('https://raw.githubusercontent.com/noikhman/wedding/main/%E2%84%96999_159.JPG');
            background-size: cover; background-position: center;
            display: flex; align-items: flex-end; justify-content: center;
            padding-bottom: 10vh;
            box-shadow: 0 20px 40px rgba(0,0,0,0.5);
        }

        .hero-section h1 { 
            font-family: 'Cormorant Garamond', serif; 
            color: #fff; font-size: clamp(2.5em, 10vw, 4.5em); 
            font-weight: 300; letter-spacing: 2px; text-align: center;
            text-shadow: 0 2px 15px rgba(0,0,0,0.5);
            font-style: italic;
        }

        /* Просвет для видео на мобильных */
        .spacer { height: 85vh; background: transparent; }

        /* КАРТОЧКА (ПОЛУПРОЗРАЧНАЯ) */
        .info-card-container {
            padding: 40px 15px 150px;
            display: flex; justify-content: center;
            position: relative;
        }

        .glass-card {
            background: rgba(255, 255, 253, 0.45); /* Прозрачность */
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            padding: 70px 25px; border-radius: 50px;
            text-align: center; width: 100%; max-width: 420px;
            box-shadow: 0 30px 60px rgba(0,0,0,0.2);
            border: 1px solid rgba(255,255,255,0.3);
        }

        .glass-card h2 {
            font-size: 2.2em; font-weight: 300; font-style: italic;
            margin-bottom: 30px; color: #1a1a1a;
        }

        .date-box {
            background: var(--main); color: #fff;
            margin: 45px -25px; padding: 35px 10px;
        }
        .date-box p:first-child {
            font-family: 'Cinzel', serif; font-size: 1.8em; letter-spacing: 4px;
        }

        .btn {
            display: inline-block; margin-top: 45px;
            padding: 16px 40px; background: var(--main);
            color: #fff; text-decoration: none;
            border-radius: 50px; text-transform: uppercase;
            font-size: 0.75em; letter-spacing: 3px; font-family: 'Montserrat', sans-serif;
            transition: 0.4s;
        }

        /* АДАПТАЦИЯ ПОД ПК */
        @media (min-width: 1025px) {
            .video-bg { width: 50%; left: 0; } /* Видео слева */
            .page-content { width: 50%; margin-left: 50%; background: #fdfdfb; } /* Контент справа */
            .hero-section { height: 100vh; }
            .spacer { display: none; }
            .glass-card { background: #fff; backdrop-filter: none; border: none; box-shadow: none; }
            .info-card-container { padding: 100px 40px; background: #fdfdfb; }
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

    <div class="page-content">
        
        <section class="hero-section">
            <h1>Данил & Ирина</h1>
        </section>

        <div class="spacer"></div>

        <section class="info-card-container">
            <div class="glass-card">
                <h2>Дорогие и любимые!</h2>
                <p style="font-size: 1.4em; line-height: 1.6; color: #1a1a1a; font-weight: 300;">
                    Один из дней лета станет самым важным в нашей жизни. 
                    Мы хотим провести его вместе с вами.
                </p>
                
                <div class="date-box">
                    <p>26.07.2026</p>
                    <p style="font-family: 'Montserrat', sans-serif; font-size: 0.7em; text-transform: uppercase; margin-top: 10px; letter-spacing: 3px;">Воскресенье • 16:30</p>
                </div>

                <div style="margin-top: 30px;">
                    <p style="font-size: 1.8em; font-weight: 400; color: #000;">Ресторан «Престиж»</p>
                    <p style="font-family: 'Montserrat', sans-serif; font-size: 0.85em; margin-top: 8px; color: #555;">г. Слободзея, ул. Фрунзе, 12</p>
                </div>

                <a href="https://maps.google.com/?q=46.7323,29.7067" target="_blank" class="btn">Место проведения</a>
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
                setTimeout(() => { curtain.style.display = 'none'; }, 1200);
            }
            if (video) video.play();
            if (audio) {
                audio.volume = 0.4;
                audio.play();
            }
        }

        // Триггеры для мобильных
        ['touchstart', 'click'].forEach(evt => {
            window.addEventListener(evt, startAll, {once: true});
        });
    </script>
</body>
</html>
