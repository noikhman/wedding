<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Данил & Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Lora:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">

    <style>
        :root { --main: #3b352d; }
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            font-family: 'Lora', serif; 
            color: #1a1a1a;
            overflow-x: hidden;
        }

        /* Кнопка активации для iPhone */
        #loader-curtain {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100%;
            background-color: #000;
            z-index: 1000;
            display: flex; align-items: center; justify-content: center;
            transition: opacity 1.2s ease, visibility 1.2s;
            cursor: pointer;
        }
        #loader-curtain::after {
            content: 'ОТКРЫТЬ ПРИГЛАШЕНИЕ';
            color: white; font-family: 'Cinzel', serif;
            letter-spacing: 3px; font-size: 0.9em; opacity: 0.8;
            border: 1px solid rgba(255,255,255,0.3);
            padding: 15px 25px;
        }

        .main-wrapper { display: flex; flex-direction: column; width: 100%; }

        .video-section {
            width: 100%; height: 100vh;
            background: #000;
            position: fixed; top: 0; left: 0;
            z-index: 1;
        }
        video { width: 100%; height: 100%; object-fit: cover; display: block; }

        .content-section { position: relative; z-index: 10; width: 100%; }

        .hero-photo {
            height: 100vh; width: 100%;
            /* ВНИМАНИЕ: Здесь расширение .JPG заглавными буквами, как у вас в файлах */
            background-image: linear-gradient(to bottom, rgba(0,0,0,0.1), rgba(0,0,0,0.4)), 
                              url('main_photo.JPG');
            background-size: cover; background-position: center;
            display: flex; align-items: flex-end; justify-content: center;
            padding-bottom: 12vh;
        }
        .hero-photo h1 { 
            font-family: 'Cinzel', serif; color: #fff; 
            font-size: 2.5em; letter-spacing: 4px; 
            text-shadow: 0 2px 15px rgba(0,0,0,0.7);
            text-align: center;
        }

        .scroll-gap { height: 85vh; background: transparent; }

        .info-card-wrap {
            padding: 40px 20px 120px;
            display: flex; justify-content: center;
        }
        .card {
            background: rgba(255, 255, 252, 0.5);
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            padding: 60px 30px; border-radius: 40px;
            text-align: center; width: 100%; max-width: 450px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
            border: 1px solid rgba(255,255,255,0.3);
        }
        .date-box { background: var(--main); color: #fff; margin: 35px -30px; padding: 30px 10px; }
        .btn {
            display: inline-block; margin-top: 35px;
            padding: 16px 45px; background: var(--main);
            color: #fff; text-decoration: none;
            border-radius: 50px; text-transform: uppercase;
            font-size: 0.85em; letter-spacing: 2px; font-family: 'Cinzel', serif;
        }

        @media (min-width: 1025px) {
            .main-wrapper { flex-direction: row; }
            .video-section { position: sticky; width: 40%; height: 100vh; flex-shrink: 0; }
            .content-section { width: 60%; z-index: 10; background: #fdfdfb; }
            .hero-photo { height: 100vh; padding-bottom: 8vh; }
            .scroll-gap { display: none; }
            .info-card-wrap { background: #fdfdfb; padding: 100px 40px; }
            .card { background: #fff; backdrop-filter: none; box-shadow: none; border: none; max-width: 500px; }
        }
    </style>
</head>
<body>

    <div id="loader-curtain" onclick="startAll()"></div>

    <audio id="music" loop preload="auto">
        <source src="wedding_music.MP3" type="audio/mpeg">
    </audio>

    <div class="main-wrapper">
        <div class="video-section">
            <video id="video" playsinline webkit-playsinline muted loop preload="auto">
                <source src="wedding_video.MP4" type="video/mp4">
            </video>
        </div>

        <div class="content-section">
            <section class="hero-photo">
                <h1>Данил & Ирина</h1>
            </section>
            <div class="scroll-gap"></div>
            <section class="info-card-wrap">
                <div class="card">
                    <p style="text-transform: uppercase; letter-spacing: 4px; font-size: 0.8em; margin-bottom: 25px; color: var(--main); font-weight: bold;">Save the Date</p>
                    <p style="font-style: italic; line-height: 1.8; font-size: 1.3em; color: #000;">
                        Дорогие и любимые!<br>Один из дней лета станет самым важным в нашей жизни.<br>И мы хотим провести его вместе с вами.
                    </p>
                    <div class="date-box">
                        <p style="font-family: 'Cinzel', serif; font-size: 2.2em; letter-spacing: 4px;">26 . 07 . 2026</p>
                        <p style="text-transform: uppercase; font-size: 0.9em; margin-top: 5px;">Воскресенье • 16:30</p>
                    </div>
                    <div style="margin: 40px 0;">
                        <p style="font-size: 1.3em; font-weight: bold; color: #000;">Ресторан «Престиж»</p>
                        <p style="color: #000; margin-top: 5px; font-weight: 500;">г. Слободзея, ул. Фрунзе, 12</p>
                    </div>
                    <a href="https://maps.app.goo.gl/3" target="_blank" class="btn">Открыть карту</a>
                </div>
            </section>
        </div>
    </div>

    <script>
        const audio = document.getElementById('music');
        const video = document.getElementById('video');
        const curtain = document.getElementById('loader-curtain');

        function startAll() {
            if (curtain) {
                curtain.style.opacity = '0';
                setTimeout(() => { curtain.style.visibility = 'hidden'; }, 1200);
            }
            if (video) video.play();
            if (audio && audio.paused) {
                audio.volume = 0.5;
                audio.play();
            }
        }

        // Слушаем любое касание экрана
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
