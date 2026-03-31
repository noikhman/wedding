<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Приглашение: Данил и Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300&family=Montserrat:wght@400;600&family=Cinzel:wght@400;700&display=swap" rel="stylesheet">

    <style>
        :root { --main: #3b352d; }
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            font-family: 'Cinzel', serif; 
            overflow-x: hidden;
        }

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
            background-image: linear-gradient(to bottom, rgba(0,0,0,0) 50%, rgba(0,0,0,0.6) 100%), 
                              url('photo.jpg');
            background-size: cover; background-position: center;
            display: flex; align-items: flex-end; justify-content: center;
            padding-bottom: 12vh;
        }

        .hero-photo h1 { 
            color: #fff; font-size: clamp(1.8em, 7vw, 3.5em); 
            font-weight: 400; letter-spacing: 3px; text-align: center;
            text-decoration: none; border: none; /* Убрано всё лишнее */
            text-shadow: 0 4px 20px rgba(0,0,0,0.8);
        }

        .gap { height: 90vh; background: transparent; }

        .info-section {
            padding: 40px 15px 120px;
            display: flex; justify-content: center;
        }

        .glass-card {
            background: rgba(255, 255, 253, 0.85); /* Сделал плотнее, чтобы текст читался лучше */
            backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px);
            padding: 60px 25px; border-radius: 40px;
            text-align: center; width: 100%; max-width: 450px;
            box-shadow: 0 25px 50px rgba(0,0,0,0.4);
        }

        .date-box {
            background: var(--main); color: #fff;
            margin: 40px -25px; padding: 30px 10px;
        }

        /* Стиль для адреса, чтобы не сливался */
        .location-box {
            margin-top: 30px;
            padding: 15px;
            background: rgba(255,255,255,0.5);
            border-radius: 15px;
        }

        .location-box p:first-child {
            font-size: 1.5em; font-weight: 700; color: #000;
            margin-bottom: 5px;
        }

        .location-box p:last-child {
            font-family: 'Montserrat', sans-serif;
            font-size: 0.9em; color: #222; font-weight: 600; /* Жирнее и темнее */
            letter-spacing: 1px;
        }

        .btn {
            display: inline-block; margin-top: 40px;
            padding: 18px 45px; background: var(--main);
            color: #fff; text-decoration: none;
            border-radius: 50px; text-transform: uppercase;
            font-size: 0.75em; letter-spacing: 3px; font-family: 'Montserrat', sans-serif;
            font-weight: 600;
        }

        @media (min-width: 1025px) {
            .video-fixed { width: 45%; }
            .content-wrapper { width: 55%; margin-left: 45%; background: #fdfdfb; }
            .hero-photo { height: 100vh; }
            .gap { display: none; }
            .glass-card { background: #fff; backdrop-filter: none; box-shadow: none; }
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
            <h1>ДАНИЛ & ИРИНА</h1>
        </section>

        <div class="gap"></div>

        <section class="info-section">
            <div class="glass-card">
                <p style="text-transform: uppercase; letter-spacing: 5px; font-size: 0.75em; margin-bottom: 25px; font-family: 'Montserrat'; font-weight: 600; color: var(--main);">Save the Date</p>
                <h2 style="font-size: 2em; margin-bottom: 25px; font-weight: 400;">ДОРОГИЕ И ЛЮБИМЫЕ!</h2>
                <p style="font-size: 1.2em; line-height: 1.6; color: #1a1a1a; font-family: 'Cormorant Garamond', serif; font-style: italic; font-weight: 400;">
                    Один из дней лета станет самым важным в нашей жизни. <br>
                    Мы хотим провести его вместе с вами.
                </p>
                
                <div class="date-box">
                    <p style="font-size: 1.8em; letter-spacing: 4px; font-weight: 400;">26.07.2026</p>
                    <p style="font-family: 'Montserrat'; font-size: 0.75em; text-transform: uppercase; margin-top: 10px; letter-spacing: 3px; font-weight: 400;">Воскресенье • 16:30</p>
                </div>

                <div class="location-box">
                    <p>РЕСТОРАН «ПРЕСТИЖ»</p>
                    <p>г. Слободзея, ул. Фрунзе, 12</p>
                </div>

                <a href="https://www.google.com/maps/search/?api=1&query=Ресторан+Престиж+Слободзея" target="_blank" class="btn">Место проведения</a>
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
        // Поддержка клика в любом месте для запуска
        window.addEventListener('click', startAll, {once: true});
    </script>
</body>
</html>
