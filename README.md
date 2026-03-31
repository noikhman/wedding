<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Приглашение: Данил и Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300&family=Montserrat:wght@200;300&family=Cinzel&display=swap" rel="stylesheet">

    <style>
        :root { --main: #3b352d; }
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            font-family: 'Cormorant Garamond', serif; 
            overflow-x: hidden;
        }

        /* Начальный экран (активация звука) */
        #loader-curtain {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: #000; z-index: 10000;
            display: flex; align-items: center; justify-content: center;
            transition: opacity 1s ease; cursor: pointer;
        }
        #loader-curtain::after {
            content: 'ОТКРЫТЬ';
            color: #fff; font-family: 'Cinzel', serif;
            letter-spacing: 5px; font-size: 0.8em;
            border: 1px solid rgba(255,255,255,0.2); padding: 12px 35px;
        }

        /* Видео фон */
        .video-fixed {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100vh;
            z-index: 1; background: #000;
        }
        video { width: 100%; height: 100%; object-fit: cover; }

        /* Контейнер контента */
        .content-wrapper {
            position: relative;
            z-index: 100;
            width: 100%;
        }

        /* Фото-шторка (Первый экран) */
        .hero-photo {
            width: 100%; 
            height: 100vh; /* Высота на весь экран */
            background-image: linear-gradient(to bottom, rgba(0,0,0,0) 60%, rgba(0,0,0,0.5) 100%), 
                              url('photo.jpg');
            background-size: cover; 
            background-position: center;
            display: flex; 
            align-items: flex-end; 
            justify-content: center;
            padding-bottom: 12vh;
        }

        .hero-photo h1 { 
            color: #fff; font-size: clamp(2em, 8vw, 4em); 
            font-weight: 300; letter-spacing: 2px; text-align: center;
            font-style: italic; text-decoration: none;
            white-space: nowrap;
            text-shadow: 0 2px 15px rgba(0,0,0,0.5);
        }

        /* Просвет для видео при скролле */
        .gap { height: 85vh; background: transparent; }

        /* Полупрозрачная карточка */
        .info-section {
            padding: 40px 15px 120px;
            display: flex; justify-content: center;
        }

        .glass-card {
            background: rgba(255, 255, 253, 0.45);
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            padding: 60px 25px; border-radius: 40px;
            text-align: center; width: 100%; max-width: 450px;
            box-shadow: 0 25px 50px rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.25);
        }

        .date-box {
            background: var(--main); color: #fff;
            margin: 40px -25px; padding: 30px 10px;
        }

        .btn {
            display: inline-block; margin-top: 40px;
            padding: 18px 45px; background: var(--main);
            color: #fff; text-decoration: none;
            border-radius: 50px; text-transform: uppercase;
            font-size: 0.75em; letter-spacing: 3px; font-family: 'Montserrat', sans-serif;
        }

        /* Адаптация под ПК */
        @media (min-width: 1025px) {
            .video-fixed { width: 45%; }
            .content-wrapper { width: 55%; margin-left: 45%; background: #fdfdfb; }
            .hero-photo { height: 100vh; }
            .gap { display: none; }
            .glass-card { background: #fff; backdrop-filter: none; box-shadow: none; border: none; }
        }
    </style>
</head>
<body>

    <div id="loader-curtain" onclick="startAll()"></div>

    <audio id="music" loop preload="auto">
        <source src="https://raw.githubusercontent.com/noikhman/wedding/main/StephenSanchez-UntilIFoundYou(PianoKaraoke).mp3" type="audio/mpeg">
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
                <p style="text-transform: uppercase; letter-spacing: 4px; font-size: 0.7em; margin-bottom: 20px; font-family: 'Montserrat';">Save the Date</p>
                <h2 style="font-size: 2.2em; font-weight: 300; font-style: italic; margin-bottom: 25px;">Дорогие и любимые!</h2>
                <p style="font-size: 1.4em; line-height: 1.6; color: #1a1a1a; font-weight: 300; font-style: italic;">
                    Один из дней лета станет самым важным в нашей жизни. 
                    Мы хотим провести его вместе с вами.
                </p>
                
                <div class="date-box">
                    <p style="font-family: 'Cinzel', serif; font-size: 1.8em; letter-spacing: 4px;">26.07.2026</p>
                    <p style="font-family: 'Montserrat'; font-size: 0.7em; text-transform: uppercase; margin-top: 10px; letter-spacing: 3px;">Воскресенье • 16:30</p>
                </div>

                <div style="margin-top: 30px;">
                    <p style="font-size: 1.8em; font-weight: 400; color: #000;">Ресторан «Престиж»</p>
                    <p style="font-family: 'Montserrat'; font-size: 0.85em; margin-top: 5px; color: #555;">г. Слободзея, ул. Фрунзе, 12</p>
                </div>

                <a href="https://maps.google.com" target="_blank" class="btn">Место проведения</a>
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
        window.addEventListener('click', startAll, {once: true});
        window.addEventListener('touchstart', startAll, {once: true});
    </script>
</body>
</html>
