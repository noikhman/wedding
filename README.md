<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Данил & Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@1,400&family=Lora:ital,wght@0,400;0,500;1,400&family=Cinzel&display=swap" rel="stylesheet">

    <style>
        :root { --main: #3b352d; }
        
        /* УДАЛЕНИЕ ВСЕХ ПОЛОСОК И КОНТУРОВ */
        * { 
            margin: 0; padding: 0; box-sizing: border-box; 
            -webkit-tap-highlight-color: transparent; 
            text-decoration: none !important; 
            border: none !important;
            outline: none !important;
        }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            overflow-x: hidden;
            font-family: 'Cormorant Garamond', serif;
            font-style: italic;
        }

        #loader-curtain {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: #000; z-index: 10000;
            display: flex; align-items: center; justify-content: center;
            transition: opacity 1s ease; cursor: pointer;
        }
        #loader-curtain::after {
            content: 'ОТКРЫТЬ';
            color: #fff; font-family: 'Cinzel', serif; font-style: normal;
            letter-spacing: 5px; font-size: 0.8em;
            border: 1px solid rgba(255,255,255,0.2) !important; padding: 12px 35px;
        }

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

        .hero-photo {
            width: 100%; height: 100vh;
            background-image: linear-gradient(to bottom, rgba(0,0,0,0) 60%, rgba(0,0,0,0.5) 100%), 
                              url('photo.jpg');
            background-size: cover; background-position: center;
            display: flex; align-items: flex-end; justify-content: center;
            padding-bottom: 12vh;
        }

        .hero-photo h1 { 
            font-family: 'Lora', serif; font-style: normal;
            color: #fff; font-size: clamp(1.8em, 8vw, 4em); 
            font-weight: 400; letter-spacing: 2px; text-align: center;
            white-space: nowrap;
            text-shadow: 0 4px 20px rgba(0,0,0,0.7);
        }

        .gap { height: 85vh; background: transparent; }

        .info-section {
            padding: 40px 15px 120px;
            display: flex; justify-content: center;
        }

        .glass-card {
            background: rgba(255, 255, 253, 0.5);
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            padding: 60px 20px; border-radius: 40px;
            text-align: center; width: 100%; max-width: 500px;
            box-shadow: 0 25px 50px rgba(0,0,0,0.3);
            color: #1a1a1a;
        }

        .glass-card h2, .venue-title {
            font-family: 'Lora', serif; font-style: normal;
            font-weight: 400; white-space: nowrap;
            text-align: center; width: 100%;
        }

        .glass-card h2 {
            font-size: clamp(1.1em, 5.5vw, 1.8em); 
            margin-bottom: 25px;
        }

        .glass-card p {
            font-family: 'Cormorant Garamond', serif; font-style: italic;
            font-weight: 400; font-size: clamp(1.3em, 5.5vw, 1.6em); 
            line-height: 1.4;
        }

        /* ОДИНАКОВЫЙ РАЗМЕР ДЛЯ ДАТЫ, ДНЯ И ВРЕМЕНИ */
        .date-box {
            background: var(--main); color: #fff;
            margin: 40px -20px; padding: 40px 10px;
            font-style: normal;
        }
        .date-text {
            font-family: 'Cinzel', serif; 
            font-size: clamp(1.8em, 8vw, 2.5em); /* Одинаковый размер */
            letter-spacing: 3px;
            line-height: 1.2;
            display: block;
        }

        .venue-title {
            font-size: clamp(1.4em, 7vw, 2.2em); 
            margin-bottom: 10px;
        }
        .venue-address {
            font-family: 'Cormorant Garamond', serif; 
            font-style: italic;
            font-size: clamp(1.2em, 5.5vw, 1.4em);
            color: #333;
        }

        /* ИСПРАВЛЕННАЯ ССЫЛКА КНОПКИ */
        .btn {
            display: inline-block; margin-top: 45px;
            padding: 20px 50px; background: var(--main);
            color: #fff !important; border-radius: 60px; 
            text-transform: uppercase; font-size: 0.8em; 
            letter-spacing: 3px; font-family: sans-serif; font-style: normal;
            cursor: pointer;
        }

        @media (min-width: 1025px) {
            .video-fixed { width: 40%; }
            .content-wrapper { width: 60%; margin-left: 40%; background: #fdfdfb; }
            .hero-photo { height: 100vh; }
            .gap { display: none; }
            .glass-card { 
                background: transparent; backdrop-filter: none; box-shadow: none; 
                max-width: 650px; padding: 100px 40px;
            }
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
                <p style="text-transform: uppercase; letter-spacing: 5px; font-size: 0.7em; margin-bottom: 30px; font-style: normal;">Save the Date</p>
                
                <h2>Дорогие и любимы!</h2>
                
                <p>
                    Один из дней лета станет самым важным в нашей жизни. 
                    Мы хотим провести его вместе с вами.
                </p>
                
                <div class="date-box">
                    <span class="date-text">26.07.2026</span>
                    <span class="date-text" style="font-size: clamp(1.4em, 6vw, 2em); margin-top: 10px;">Воскресенье</span>
                    <span class="date-text" style="font-size: clamp(1.4em, 6vw, 2em);">16:30</span>
                </div>

                <div style="margin-top: 40px;">
                    <p class="venue-title">Ресторан «Престиж»</p>
                    <p class="venue-address">г. Слободзея, ул. Фрунзе, 12</p>
                </div>

                <a href="https://maps.app.goo.gl/9eMWfcTeJakhhC7i6" target="_blank" class="btn">Место проведения</a>
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
            if (audio) { audio.volume = 0.4; audio.play(); }
        }
        window.addEventListener('click', startAll, {once: true});
        window.addEventListener('touchstart', startAll, {once: true});
    </script>
</body>
</html>
