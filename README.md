<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Данил & Ирина</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300&family=Montserrat:wght@200;300;400&family=Cinzel&display=swap" rel="stylesheet">

    <style>
        :root { --main: #3b352d; }
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            font-family: 'Montserrat', sans-serif; 
            overflow-x: hidden;
        }

        /* Кнопка активации для iPhone */
        #loader-curtain {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: #000; z-index: 10000;
            display: flex; align-items: center; justify-content: center;
            transition: opacity 1.2s ease, visibility 1.2s;
            cursor: pointer;
        }
        #loader-curtain::after {
            content: 'ОТКРЫТЬ ПРИГЛАШЕНИЕ';
            color: #fff; font-family: 'Cinzel', serif;
            letter-spacing: 4px; font-size: 0.8em; opacity: 0.8;
            border: 1px solid rgba(255,255,255,0.3); padding: 15px 30px;
        }

        /* Общая обертка */
        .wrapper { width: 100%; display: flex; flex-direction: column; }

        /* ВИДЕО (ЗАФИКСИРОВАНО ВНИЗУ) */
        .video-fixed {
            position: fixed; top: 0; left: 0;
            width: 100%; height: 100vh;
            z-index: 10; background: #000;
        }
        video { width: 100%; height: 100%; object-fit: cover; }

        /* СКРОЛЛ-КОНТЕНТ (ПОВЕРХ ВИДЕО) */
        .page-scrolling {
            position: relative;
            z-index: 20; /* Выше видео */
            width: 100%;
        }

        /* ГЛАВНОЕ ФОТО (ПЕРЕКРЫВАЕТ ВСЁ НА 100%) */
        .hero-section {
            width: 100%; 
            height: 100vh; /* ГАРАНТИРУЕМ, ЧТО ЗАНИМАЕТ ВЕСЬ ЭКРАН */
            background-image: linear-gradient(to bottom, rgba(0,0,0,0) 65%, rgba(0,0,0,0.6) 100%), 
                              url('photo.jpg'); /* Название фото строго маленькими буквами */
            background-size: cover; 
            background-position: center top; /* Чтобы головы не обрезались */
            display: flex; 
            align-items: flex-end; /* Опускаем надпись вниз */
            justify-content: center;
            padding-bottom: 12vh; /* Смещение имен ниже середины */
            box-shadow: 0 15px 40px rgba(0,0,0,0.5);
        }

        /* ТЕКСТ: ДАНИЛ & ИРИНА В ОДНУ СТРОКУ, БЕЗ ПОДЧЕРКИВАНИЯ */
        .hero-section h1 { 
            font-family: 'Cormorant Garamond', serif; 
            color: #fff; 
            font-size: clamp(1.8em, 6vw, 3.2em); /* Размер подбирается автоматически */
            font-weight: 300; 
            letter-spacing: 2px; 
            text-align: center;
            font-style: italic;
            text-transform: uppercase;
            text-decoration: none; /* УБРАЛИ ПОДЧЕРКИВАНИЕ */
            text-shadow: 0 3px 15px rgba(0,0,0,0.6);
            white-space: nowrap; /* ГАРАНТИРУЕМ ОДНУ СТРОКУ */
        }

        /* Просвет для видео на мобильных */
        .spacer { height: 85vh; background: transparent; }

        /* КАРТОЧКА (ПОЛУПРОЗРАЧНАЯ, СТЕКЛО) */
        .info-card-container {
            padding: 40px 15px 120px;
            display: flex; justify-content: center;
            background: transparent;
        }

        .glass-card {
            background: rgba(255, 255, 253, 0.45);
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            padding: 60px 25px; border-radius: 40px;
            text-align: center; width: 100%; max-width: 420px;
            box-shadow: 0 25px 60px rgba(0,0,0,0.25);
            border: 1px solid rgba(255,255,255,0.3);
        }

        .glass-card h2 {
            font-family: 'Cormorant Garamond', serif; font-size: 2em; 
            font-weight: 300; font-style: italic;
            margin-bottom: 25px; color: #1a1a1a;
        }

        .date-box {
            background: var(--main); color: #fff;
            margin: 40px -25px; padding: 30px 10px;
        }
        .date-box p:first-child {
            font-family: 'Cinzel', serif; font-size: 1.8em; letter-spacing: 4px;
        }

        .btn {
            display: inline-block; margin-top: 40px;
            padding: 18px 45px; background: var(--main);
            color: #fff; text-decoration: none;
            border-radius: 50px; text-transform: uppercase;
            font-size: 0.75em; letter-spacing: 3px; font-weight: 400;
        }

        /* АДАПТАЦИЯ ПОД ПК */
        @media (min-width: 1025px) {
            .wrapper { flex-direction: row; height: 100vh; }
            .video-fixed { position: sticky; width: 45%; flex-shrink: 0; left: 0; height: 100%; }
            .page-scrolling { position: static; width: 55%; margin-left: auto; background: #fdfdfb; }
            .hero-section { height: 100vh; position: sticky; top: 0; }
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

    <div class="wrapper">
        <div class="video-fixed">
            <video id="video" playsinline webkit-playsinline muted loop preload="auto">
                <source src="https://noikhman.github.io/wedding/video5350360388351334576.mp4" type="video/mp4">
            </video>
        </div>

        <div class="page-scrolling">
            
            <section class="hero-section">
                <h1>Данил & Ирина</h1>
            </section>

            <div class="spacer"></div>

            <section class="info-card-container">
                <div class="glass-card">
                    <h2>Дорогие и любимые!</h2>
                    <p style="font-size: 1.3em; line-height: 1.6; color: #1a1a1a; font-weight: 300;">
                        Один из дней лета станет самым важным в нашей жизни. 
                        Мы хотим провести его вместе с вами.
                    </p>
                    
                    <div class="date-box">
                        <p>26.07.2026</p>
                        <p style="font-size: 0.7em; text-transform: uppercase; margin-top: 10px; letter-spacing: 3px; font-weight: 200;">Воскресенье • 16:30</p>
                    </div>

                    <div style="margin-top: 30px;">
                        <p style="font-size: 1.7em; font-weight: 400; color: #000;">Ресторан «Престиж»</p>
                        <p style="font-size: 0.85em; margin-top: 8px; color: #555; font-weight: 300;">г. Слободзея, ул. Фрунзе, 12</p>
                    </div>

                    <a href="https://maps.google.com/?q=46.7323,29.7067" target="_blank" class="btn">Место проведения</a>
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
