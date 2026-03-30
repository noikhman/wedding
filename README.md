<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Приглашение: Данил и Ирина</title>
    
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
            background-color: var(--bg); 
            font-family: 'Montserrat', sans-serif; 
            color: var(--main);
            overflow-x: hidden;
        }

        /* ЗАТЕМНЕНИЕ ПРИ ВХОДЕ */
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
            letter-spacing: 4px; font-size: 0.75em; opacity: 0.7;
            border: 1px solid rgba(255,255,255,0.3); padding: 15px 30px;
        }

        /* ФОТО СВЕРХУ (ПЕРЕКРЫВАЕТ ВСЁ) */
        .hero-photo {
            position: relative;
            height: 100vh; width: 100%;
            z-index: 100; /* Самый высокий слой */
            background-image: linear-gradient(to bottom, rgba(0,0,0,0.1), rgba(0,0,0,0.5)), 
                              url('%E2%84%96999_159.JPG');
            background-size: cover; background-position: center;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .hero-photo h1 { 
            font-family: 'Playfair Display', serif; 
            color: #fff; font-size: 2.8em; font-weight: 400;
            letter-spacing: 2px; text-align: center;
            animation: fadeInUp 2s ease forwards;
        }
        
        .hero-photo p {
            color: #fff; font-family: 'Montserrat', sans-serif;
            text-transform: uppercase; letter-spacing: 5px; font-size: 0.8em;
            margin-top: 15px; opacity: 0.9;
        }

        /* ВИДЕО СНИЗУ (ФОНОВОЕ) */
        .video-container {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100vh;
            z-index: 1; /* Самый нижний слой */
            background: #000;
        }
        video { width: 100%; height: 100%; object-fit: cover; }

        /* КОНТЕНТ ПОСЛЕ СКРОЛЛА */
        .content-wrap {
            position: relative;
            z-index: 100; /* Тоже сверху, как и фото */
            background: var(--bg);
            margin-top: 80vh; /* Создает промежуток, чтобы было видно видео */
            padding: 80px 20px;
            display: flex; flex-direction: column; align-items: center;
        }

        .card {
            background: #fff;
            padding: 60px 30px; border-radius: 2px;
            text-align: center; width: 100%; max-width: 500px;
            box-shadow: 0 15px 45px rgba(0,0,0,0.05);
            border: 1px solid #f0efeb;
        }

        .card h2 {
            font-family: 'Playfair Display', serif;
            font-size: 1.8em; font-style: italic; margin-bottom: 30px;
        }

        .date-box { 
            border-top: 1px solid #e0ddd5; border-bottom: 1px solid #e0ddd5;
            margin: 40px 0; padding: 30px 0; 
        }
        .date-box p:first-child {
            font-family: 'Cinzel', serif; font-size: 2.2em; color: var(--gold);
        }

        .btn {
            display: inline-block; margin-top: 40px;
            padding: 18px 40px; background: var(--main);
            color: #fff; text-decoration: none;
            border-radius: 0; text-transform: uppercase;
            font-size: 0.7em; letter-spacing: 3px;
            transition: 0.3s;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* ДЛЯ ПК */
        @media (min-width: 1025px) {
            .hero-photo h1 { font-size: 4em; }
            .content-wrap { margin-top: 90vh; padding: 120px 20px; }
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
        <p>Приглашение на свадьбу</p>
    </section>

    <div class="content-wrap">
        <div class="card">
            <h2>Дорогие и любимые!</h2>
            <p style="line-height: 2; font-size: 1.1em; font-weight: 300;">
                Один из дней этого лета станет самым важным в нашей жизни. 
                Мы хотим разделить это счастье с вами и приглашаем вас на наше торжество.
            </p>
            
            <div class="date-box">
                <p>26 . 07 . 2026</p>
                <p style="text-transform: uppercase; font-size: 0.8em; letter-spacing: 2px; margin-top: 10px;">Воскресенье • 16:30</p>
            </div>

            <div style="margin-bottom: 30px;">
                <p style="font-family: 'Playfair Display', serif; font-size: 1.4em; color: var(--gold);">Ресторан «Престиж»</p>
                <p style="margin-top: 8px; font-size: 0.9em;">г. Слободзея, ул. Фрунзе, 12</p>
            </div>

            <a href="http://googleusercontent.com/maps.google.com/8" target="_blank" class="btn">Место проведения</a>
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
                audio.play();
            }
        }

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
