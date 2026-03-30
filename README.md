<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Данил & Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Montserrat:wght@300;400&family=Cinzel&display=swap" rel="stylesheet">

    <style>
        :root { 
            --main: #3b352d; 
            --gold: #c5a059;
            --bg: #fdfdfb;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            font-family: 'Montserrat', sans-serif; 
            color: #1a1a1a;
            overflow-x: hidden;
        }

        /* ЗАТЕМНЕНИЕ ПРИ ВХОДЕ (ДЛЯ IPHONE) */
        #loader-curtain {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100%;
            background-color: #000;
            z-index: 2000;
            display: flex; align-items: center; justify-content: center;
            transition: opacity 1.5s ease, visibility 1.5s;
            cursor: pointer;
        }
        #loader-curtain::after {
            content: 'ОТКРЫТЬ ПРИГЛАШЕНИЕ';
            color: #fff; font-family: 'Cinzel', serif;
            letter-spacing: 4px; font-size: 0.8em; opacity: 0.7;
            border: 1px solid rgba(255,255,255,0.3); padding: 15px 30px;
        }

        /* ФОТО СВЕРХУ (ПЕРЕКРЫВАЕТ ВСЁ) */
        .hero-photo {
            position: relative;
            height: 100vh; width: 100%;
            z-index: 100; /* Высокий слой */
            background-image: linear-gradient(to bottom, rgba(0,0,0,0.1), rgba(0,0,0,0.5)), 
                              url('%E2%84%96999_159.JPG');
            background-size: cover; background-position: center;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .hero-photo h1 { 
            font-family: 'Playfair Display', serif; 
            color: #fff; font-size: 3em; font-weight: 400;
            letter-spacing: 2px; text-align: center;
            animation: fadeInUp 2s ease forwards;
        }
        
        /* ВИДЕО СНИЗУ (ФОНОВОЕ) */
        .video-container {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100vh;
            z-index: 1; /* Нижний слой */
            background: #000;
        }
        video { width: 100%; height: 100%; object-fit: cover; }

        /* КОНТЕНТ ПОСЛЕ СКРОЛЛА */
        .content-wrap {
            position: relative;
            z-index: 100; /* Сверху, как и фото */
            background: transparent;
            margin-top: 80vh; /* Промежуток для видео */
            padding: 80px 20px 120px;
            display: flex; flex-direction: column; align-items: center;
        }

        /* ВЕРНУЛИ ДИЗАЙН КАРТОЧКИ (СТЕКЛО) */
        .card {
            background: rgba(255, 255, 252, 0.45);
            backdrop-filter: blur(12px); -webkit-backdrop-filter: blur(12px);
            padding: 60px 30px; border-radius: 40px;
            text-align: center; width: 100%; max-width: 450px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.25);
        }

        .card h2 {
            font-family: 'Playfair Display', serif;
            font-size: 1.8em; font-style: italic; margin-bottom: 30px;
            color: #000;
        }

        .date-box { 
            background: var(--main); color: #fff;
            margin: 40px -30px; padding: 30px 10px;
        }
        .date-box p:first-child {
            font-family: 'Cinzel', serif; font-size: 2.2em;
            letter-spacing: 3px;
        }

        .btn {
            display: inline-block; margin-top: 40px;
            padding: 18px 45px; background: var(--main);
            color: #fff; text-decoration: none;
            border-radius: 50px; text-transform: uppercase;
            font-size: 0.8em; letter-spacing: 2px;
            transition: 0.3s;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* ДЛЯ ПК */
        @media (min-width: 1025px) {
            .hero-photo h1 { font-size: 4.5em; }
            .content-wrap { margin-top: 90vh; }
            .card {
                background: #fff; /* На ПК карточка плотная */
                backdrop-filter: none; box-shadow: none; border: none;
                max-width: 500px;
            }
        }
    </style>
</head>
<body>

    <div id="loader-curtain" onclick="startAll()"></div>

    <audio id="music" loop preload="auto">
        <source src="Stephen%20Sanchez%20-%20Until%20I%20Found%20You%20(Piano%20Karaoke).mp3" type="audio/mpeg">
    </audio>

    <div class="video-container">
        <video id="video" playsinline webkit-playsinline muted loop preload="auto">
            <source src="video5350360388351334576.mp4" type="video/mp4">
        </video>
    </div>

    <section class="hero-photo">
        <h1>Данил & Ирина</h1>
    </section>

    <div class="content-wrap">
        <div class="card">
            <h2>Дорогие и любимые!</h2>
            <p style="line-height: 1.8; font-size: 1.15em; font-weight: 300; color: #000; font-style: italic;">
                Один из дней лета станет самым важным в нашей жизни.<br>
                И мы хотим провести его вместе с вами.
            </p>
            
            <div class="date-box">
                <p>26 . 07 . 2026</p>
                <p style="text-transform: uppercase; font-size: 0.9em; letter-spacing: 2px; margin-top: 10px;">Воскресенье • 16:30</p>
            </div>

            <div style="margin-bottom: 30px;">
                <p style="font-family: 'Playfair Display', serif; font-size: 1.5em; color: #000; font-weight: 700;">Ресторан «Престиж»</p>
                <p style="margin-top: 8px; font-size: 1em; color: #000; font-weight: 500;">г. Слободзея, ул. Фрунзе, 12</p>
            </div>

            <a href="https://maps.app.goo.gl/dsVRbwvtxUHcUdaE7" target="_blank" class="btn">Открыть карту</a>
        </div>
    </div>

    <script>
        const audio = document.getElementById('music');
        const video = document.getElementById('video');
        const curtain = document.getElementById('loader-curtain');

        function startAll() {
            if (curtain) {
                curtain.style.opacity = '0';
                setTimeout(() => { curtain.style.visibility = 'hidden'; }, 1500);
            }
            if (video) video.play();
            if (audio && audio.paused) {
                audio.volume = 0.4;
                audio.play().catch(e => console.log("Safari blocking sound"));
            }
        }

        // Поддержка касаний для мобильных
        ['touchstart', 'click', 'scroll'].forEach(evt => {
            window.addEventListener(evt, startAll, {once: true});
        });

        document.addEventListener('visibilitychange', () => {
            if (document.hidden) { audio.pause(); video.pause(); }
            else { if (audio.currentTime > 0) audio.play(); video.play(); }
        });
    </script>
</body>
</html>
