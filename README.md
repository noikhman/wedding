<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Данил & Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@200;300;400;500&display=swap" rel="stylesheet">

    <style>
        :root { --main: #3b352d; --bg: #fdfdfb; }
        * { margin: 0; padding: 0; box-sizing: border-box; text-decoration: none !important; -webkit-tap-highlight-color: transparent; }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            font-family: 'Montserrat', sans-serif; 
            overflow-x: hidden;
            color: #1a1a1a;
        }

        /* Экран входа (убирает системные задержки звука) */
        #loader-curtain {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: #000; z-index: 10000;
            display: flex; align-items: center; justify-content: center;
            transition: opacity 1s ease; cursor: pointer;
        }
        #loader-curtain::after {
            content: 'ОТКРЫТЬ ПРИГЛАШЕНИЕ';
            color: #fff; letter-spacing: 5px; font-size: 0.7em; font-weight: 300;
            border: 1px solid rgba(255,255,255,0.2); padding: 15px 30px;
        }

        /* Базовая структура */
        .main-container { width: 100%; position: relative; }

        /* ВИДЕО ФОН */
        .video-wrapper {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100vh;
            z-index: 5; background: #000;
        }
        video { width: 100%; height: 100%; object-fit: cover; }

        /* ФОТО (ПЕРЕКРЫВАЕТ ВСЁ) */
        .hero-photo {
            position: relative;
            width: 100%; height: 100vh;
            z-index: 100; /* Выше видео */
            background-image: linear-gradient(to bottom, rgba(0,0,0,0) 70%, rgba(0,0,0,0.5) 100%), 
                              url('https://raw.githubusercontent.com/noikhman/wedding/main/%E2%84%96999_159.JPG');
            background-size: cover; background-position: center;
            display: flex; align-items: flex-end; justify-content: center;
            padding-bottom: 15vh;
        }

        .hero-photo h1 { 
            color: #fff; font-size: clamp(1.5em, 7vw, 2.8em); 
            font-weight: 300; letter-spacing: 6px; text-transform: uppercase;
            text-align: center; white-space: nowrap;
        }

        /* Просвет для скролла */
        .spacer { height: 90vh; background: transparent; position: relative; z-index: 10; }

        /* ИНФО-БЛОК */
        .content-section {
            position: relative; z-index: 110;
            display: flex; justify-content: center;
            padding: 40px 15px 100px;
            background: transparent;
        }

        .glass-card {
            background: rgba(255, 255, 252, 0.45);
            backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px);
            padding: 60px 30px; border-radius: 30px;
            text-align: center; width: 100%; max-width: 450px;
            box-shadow: 0 30px 60px rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.2);
        }

        .glass-card h2 {
            font-size: 1.6em; font-weight: 400; letter-spacing: 2px;
            margin-bottom: 30px; text-transform: uppercase;
        }

        .date-box {
            background: var(--main); color: #fff;
            margin: 40px -30px; padding: 35px 10px;
        }
        .date-box p:first-child {
            font-size: 2em; letter-spacing: 5px; font-weight: 200;
        }

        .btn {
            display: inline-block; margin-top: 45px;
            padding: 18px 45px; background: var(--main);
            color: #fff !important; border-radius: 50px; 
            text-transform: uppercase; font-size: 0.7em; 
            letter-spacing: 3px; transition: 0.4s;
        }

        /* --- ПК ВЕРСИЯ --- */
        @media (min-width: 1025px) {
            .video-wrapper { width: 50%; left: 0; }
            .hero-photo { width: 50%; margin-left: 50%; height: 100vh; position: sticky; top: 0; }
            .spacer { display: none; }
            .content-section { 
                width: 50%; margin-left: 50%; 
                background: var(--bg); padding: 100px 50px; 
            }
            .glass-card { 
                background: #fff; backdrop-filter: none; 
                box-shadow: none; border: none; max-width: 500px; 
            }
        }
    </style>
</head>
<body>

    <div id="loader-curtain" onclick="startAll()"></div>

    <audio id="music" loop preload="auto">
        <source src="https://noikhman.github.io/wedding/Stephen%20Sanchez%20-%20Until%20I%20Found%20You%20(Piano%20Karaoke).mp3" type="audio/mpeg">
    </audio>

    <div class="main-container">
        <div class="video-wrapper">
            <video id="video" playsinline webkit-playsinline muted loop preload="auto">
                <source src="https://noikhman.github.io/wedding/video5350360388351334576.mp4" type="video/mp4">
            </video>
        </div>

        <div class="content-wrapper">
            <section class="hero-photo">
                <h1>Данил & Ирина</h1>
            </section>

            <div class="spacer"></div>

            <section class="content-section">
                <div class="glass-card">
                    <h2>Дорогие и любимые!</h2>
                    <p style="font-weight: 300; line-height: 1.8; font-size: 1.1em;">
                        Один из дней лета станет самым важным в нашей жизни. 
                        Мы хотим провести его вместе с вами.
                    </p>
                    
                    <div class="date-box">
                        <p>26.07.2026</p>
                        <p style="font-size: 0.75em; margin-top: 10px; letter-spacing: 3px;">ВОСКРЕСЕНЬЕ • 16:30</p>
                    </div>

                    <div style="margin-top: 30px;">
                        <p style="font-size: 1.4em; font-weight: 500; letter-spacing: 1px;">РЕСТОРАН «ПРЕСТИЖ»</p>
                        <p style="font-size: 0.9em; margin-top: 10px; font-weight: 300;">г. Слободзея, ул. Фрунзе, 12</p>
                    </div>

                    <a href="https://www.google.com/maps/search/?api=1&query=Ресторан+Престиж+Слободзея" target="_blank" class="btn">Место проведения</a>
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
