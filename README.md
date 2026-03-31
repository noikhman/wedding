**<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Данил & Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@1,400&family=Lora:wght@400;500&family=Cinzel&display=swap" rel="stylesheet">

    <style>
        :root { --main: #3b352d; }
        /* Убираем все полоски и подчеркивания */
        * { 
            margin: 0; padding: 0; box-sizing: border-box; 
            -webkit-tap-highlight-color: transparent; 
            text-decoration: none !important; 
            border: none !important;
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
            /* Новое название файла */
            background-image: linear-gradient(to bottom, rgba(0,0,0,0) 60%, rgba(0,0,0,0.5) 100%), 
                              url('photo.jpg');
            background-size: cover; background-position: center;
            display: flex; align-items: flex-end; justify-content: center;
            padding-bottom: 15vh;
        }

        /* ИМЕНА: Lora, в одну строку */
        .hero-photo h1 { 
            font-family: 'Lora', serif; font-style: normal;
            color: #fff; font-size: clamp(1.6em, 7.5vw, 3.5em); 
            font-weight: 400; letter-spacing: 1px; text-align: center;
            white-space: nowrap;
            text-shadow: 0 2px 15px rgba(0,0,0,0.6);
        }

        .gap { height: 85vh; background: transparent; }

        .info-section {
            padding: 40px 15px 120px;
            display: flex; justify-content: center;
        }

        .glass-card {
            background: rgba(255, 255, 253, 0.45);
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            padding: 60px 20px; border-radius: 40px;
            text-align: center; width: 100%; max-width: 450px;
            box-shadow: 0 25px 50px rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.25) !important;
            color: #1a1a1a;
        }

        /* ПРИВЕТСТВИЕ: Lora, в одну строку на мобильных */
        .glass-card h2 {
            font-family: 'Lora', serif; font-style: normal;
            font-size: clamp(1.1em, 5.8vw, 2em); 
            font-weight: 400; margin-bottom: 25px;
            white-space: nowrap;
        }

        .glass-card p {
            font-family: 'Cormorant Garamond', serif; font-style: italic;
            font-weight: 400; font-size: 1.5em; line-height: 1.3;
        }

        .date-box {
            background: var(--main); color: #fff;
            margin: 40px -20px; padding: 30px 10px;
            font-style: normal;
        }

        /* РЕСТОРАН: В одну строку */
        .venue-name {
            font-family: 'Cormorant Garamond', serif; font-style: italic;
            font-weight: 400; font-size: clamp(1.3em, 6.5vw, 2.2em); 
            white-space: nowrap; margin-bottom: 5px;
        }

        .btn {
            display: inline-block; margin-top: 40px;
            padding: 18px 45px; background: var(--main);
            color: #fff !important; border-radius: 50px; 
            text-transform: uppercase; font-size: 0.75em; 
            letter-spacing: 3px; font-family: sans-serif; font-style: normal;
        }

        @media (min-width: 1025px) {
            .video-fixed { width: 45%; }
            .content-wrapper { width: 55%; margin-left: 45%; background: #fdfdfb; }
            .gap { display: none; }
            .glass-card { background: #fff; backdrop-filter: none; box-shadow: none; border: none !important; }
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
                <p style="text-transform: uppercase; letter-spacing: 4px; font-size: 0.8em; margin-bottom: 20px; font-style: normal;">Save the Date</p>
                
                <h2>Дорогие и любимые!</h2>
                
                <p>
                    Один из дней лета станет самым важным в нашей жизни. 
                    Мы хотим провести его вместе с вами.
                </p>
                
                <div class="date-box">
                    <p style="font-family: 'Cinzel', serif; font-size: 1.8em; letter-spacing: 4px;">26.07.2026</p>
                    <p style="font-size: 0.8em; text-transform: uppercase; margin-top: 10px; letter-spacing: 3px; font-style: normal;">Воскресенье • 16:30</p>
                </div>

                <div style="margin-top: 30px;">
                    <p class="venue-name">Ресторан «Престиж»</p>
                    <p style="font-size: 1.1em; font-family: 'Cormorant Garamond';">г. Слободзея, ул. Фрунзе, 12</p>
                </div>

                <a href="https://maps.app.goo.gl/3" target="_blank" class="btn">Место проведения</a>
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
**
