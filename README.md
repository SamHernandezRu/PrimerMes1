<!DOCTYPE index.html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Daniela 💖</title>
    <style>
        body {
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: 'Arial', sans-serif;
            color: #fff;
            text-align: center;
            overflow: hidden;
            position: relative;
        }
        .container {
            background: rgba(255, 255, 255, 0.2);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
            z-index: 2;
            position: relative;
        }
        h1 {
            font-size: 4rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            animation: heartbeat 1.5s infinite;
            margin: 0;
        }
        p {
            font-size: 1.5rem;
            margin-top: 20px;
            font-style: italic;
        }
        .emoji {
            font-size: 2rem;
            margin: 10px;
        }
        .hearts, .flowers, .lights {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }
        .heart, .flower, .light {
            position: absolute;
            color: #ff6b6b;
            font-size: 2rem;
            animation: float 5s infinite ease-in-out;
        }
        .flower {
            color: #ffd700;
            font-size: 1.5rem;
        }
        .light {
            color: #fff;
            font-size: 1rem;
            opacity: 0.7;
        }
        @keyframes heartbeat {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.1);
            }
        }
        @keyframes float {
            0% {
                transform: translateY(0) rotate(0);
                opacity: 0;
            }
            50% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }
        .side-decoration {
            position: absolute;
            top: 0;
            width: 20%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            font-size: 2rem;
            color: rgba(255, 255, 255, 0.5);
        }
        .left {
            left: 0;
        }
        .right {
            right: 0;
        }
        .image-container {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            gap: 10px;
        }
        .image-container img {
            width: 150px; /* Tamaño más pequeño */
            height: auto;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
        }
        .audio-controls {
            position: fixed;
            bottom: 20px;
            right: 20px;
            display: flex;
            gap: 10px;
        }
        .audio-controls button {
            background: #ff6b6b;
            color: white;
            border: none;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            font-size: 1.2rem;
            cursor: pointer;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
            transition: background 0.3s ease;
        }
        .audio-controls button:hover {
            background: #ff4757;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>💖 Te amo, Daniela 💖</h1>
        <p>"Eres mi sol en los días grises y mi estrella en las noches oscuras."</p>
        <p>"Cada latido de mi corazón lleva tu nombre."</p>
        <p>"Eres la razón por la que creo en el amor."</p>
        <div class="emoji">💌🌹💕✨🥰</div>

        <div class="image-container">
            <img src="MiNoviecita.jpeg" alt="Mi Noviecita">
            <img src="MiNoviecitaa.jpeg" alt="Mi Noviecitaa">
        </div>
    </div>

    <div class="hearts"></div>
    <div class="flowers"></div>
    <div class="lights"></div>

    <div class="side-decoration left">
        <div>🌹</div>
        <div>💖</div>
        <div>✨</div>
        <div>🌸</div>
        <div>💕</div>
    </div>

    <div class="side-decoration right">
        <div>💕</div>
        <div>🌸</div>
        <div>✨</div>
        <div>💖</div>
        <div>🌹</div>
    </div>

    <audio id="musica" loop>
        <source src="La novela.mp3" type="audio/mpeg">
        Tu navegador no soporta la reproducción de audio.
    </audio>

    <div class="audio-controls">
        <button onclick="reproducirMusica()">▶️</button>
        <button onclick="pausarMusica()">⏸️</button>
    </div>

    <script>
        const frases = [
            "Eres mi todo, Daniela.",
            "Contigo, el amor es infinito.",
            "Eres la mejor parte de mi día.",
            "Mi corazón late por ti.",
            "Eres mi sueño hecho realidad.",
            "Eres la luz que ilumina mi vida.",
            "Cada día a tu lado es un regalo.",
            "Eres mi razón de ser.",
            "Eres mi eterna inspiración.",
            "Eres la dueña de mi corazón."
        ];

        let indice = 0;
        const elementoFrase = document.querySelector('p');

        setInterval(() => {
            elementoFrase.textContent = frases[indice];
            indice = (indice + 1) % frases.length;
        }, 3000);

        const heartsContainer = document.querySelector('.hearts');

        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '💖';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 3 + 2 + 's';
            heartsContainer.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        const flowersContainer = document.querySelector('.flowers');

        function createFlower() {
            const flower = document.createElement('div');
            flower.classList.add('flower');
            flower.innerHTML = '🌸';
            flower.style.left = Math.random() * 100 + 'vw';
            flower.style.animationDuration = Math.random() * 4 + 3 + 's';
            flowersContainer.appendChild(flower);

            setTimeout(() => {
                flower.remove();
            }, 7000);
        }

        const lightsContainer = document.querySelector('.lights');

        function createLight() {
            const light = document.createElement('div');
            light.classList.add('light');
            light.innerHTML = '✨';
            light.style.left = Math.random() * 100 + 'vw';
            light.style.animationDuration = Math.random() * 2 + 1 + 's';
            lightsContainer.appendChild(light);

            setTimeout(() => {
                light.remove();
            }, 3000);
        }

        setInterval(createHeart, 300);
        setInterval(createFlower, 500);
        setInterval(createLight, 200);

        const musica = document.getElementById('musica');

        function reproducirMusica() {
            musica.play();
        }

        function pausarMusica() {
            musica.pause();
        }
    </script>
</body>
</html>
