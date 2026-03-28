<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Приглашение</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel&family=Lora:ital@0;1&display=swap" rel="stylesheet">
    <style>
        :root { --main: #3b352d; }
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            font-family: 'Lora', serif; 
            color: #1a1a1a;
        }

        /* Видео на весь экран */
        .video-bg {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100%;
            z-index: -1; background: #000;
        }
        video { width: 100%; height: 100%; object-fit: cover; }

        .content { position: relative; z-index: 10; width: 100%; }

        /* Первый экран */
        .hero {
            height: 100vh; width: 100%;
            background-image: linear-gradient(to bottom, rgba(0,0,0,0.2), rgba(0,0,0,0.5)), 
                              url('https://raw.githubusercontent.com/noikhman/wedding/main/%E2%84%96999_159.JPG');
            background-size: cover; background-position: center;
            display: flex; align-items: flex-end; justify-content: center;
            padding-bottom: 10vh;
        }
        .hero h1 { 
            font-family: 'Cinzel', serif; color: #fff; 
            font-size: 2.2em; letter-spacing: 3px; 
            text-shadow: 0 2px 10px rgba(0,0,0,0.5);
        }

        /* Окно для видео при скролле */
        .spacer { height: 80vh; background: transparent; }

        /* Карточка с инфо */
        .info-wrap {
            padding: 20px 20px 100px;
            display: flex; justify-content: center;
        }
        .card {
            background: rgba(255, 255, 250, 0.7);
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            padding: 50px 25px; border-radius: 30px;
            text-align: center; width: 100%; max-width: 400px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }
        .date-box {
            background: var(--main); color: #fff;
            margin: 30px -25px; padding: 25px 10px;
        }
        .btn {
            display: inline-block; margin-top: 30px;
            padding: 15px 40px; background: var(--main);
            color: #fff; text-decoration: none;
            border-radius: 50px; text-transform: uppercase;
            font-size: 0.8em; letter-spacing: 2px;
        }
    </style>
</head>
<body>

    <audio id="music" loop preload="auto">
        <source src="https://raw.githubusercontent.com/noikhman/wedding/main/Stephen%20Sanchez%20-%20Until%20I%20Found%20You%20(Piano%20Karaoke).mp3" type="audio/mpeg">
    </audio>

    <div class="video-bg">
        <video id="video" playsinline webkit-playsinline muted loop preload="auto">
            <source src="https://raw.githubusercontent.com/noikhman/wedding/main/video5350360388351334576.mp4" type="video/mp4">
        </video>
    </div>

    <div class="content">
        <section class="hero">
            <h1>Данил & Ирина</h1>
        </section>

        <div class="spacer"></div>

        <section class="info-wrap">
            <div class="card">
                <p style="text-transform: uppercase; letter-spacing: 3px; font-size: 0.7em; margin-bottom: 20px;">Save the Date</p>
                <p style="font-style: italic; line-height: 1.7; font-size: 1.1em;">
                    Дорогие и любимые!<br>
                    Один из дней лета станет самым важным в нашей жизни.<br>
                    И мы хотим провести его вместе с вами.
                </p>
                <div class="date-box">
                    <p style="font-family: 'Cinzel', serif; font-size: 1.7em;">26 . 07 . 2026</p>
                    <p style="font-size: 0.8em;">Воскресенье • 16:30</p>
                </div>
                <p><strong>Ресторан «Престиж»</strong><br>г. Слободзея, ул. Фрунзе, 12</p>
                <a href="https://maps.google.com/?q=г.+Слободзея,+ул.+Фрунзе,+12" target="_blank" class="btn">Карта</a>
            </div>
        </section>
    </div>

    <script>
        const audio = document.getElementById('music');
        const video = document.getElementById('video');

        function startAll() {
            if (video) video.play();
            if (audio && audio.paused) {
                audio.volume = 0.5;
                audio.play();
            }
        }

        // Ждем ЛЮБОГО действия гостя
        window.addEventListener('touchstart', startAll, {once: true});
        window.addEventListener('click', startAll, {once: true});
        window.addEventListener('scroll', startAll, {once: true});

        // Пауза при сворачивании
        document.addEventListener('visibilitychange', () => {
            if (document.hidden) { audio.pause(); video.pause(); }
            else { if (audio.currentTime > 0) audio.play(); video.play(); }
        });
    </script>
</body>
</html>
