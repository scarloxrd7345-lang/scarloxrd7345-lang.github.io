<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Para el amor de mi vida ❤️</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            height: 100vh;
            height: 100dvh;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Georgia', serif;

            /* Fondo rosa pastel */
            background: linear-gradient(
                135deg,
                #ffe6ee,
                #ffc9dc,
                #ffe0eb,
                #ffd1e1
            );
        }

        /* Corazones y rosas que caen */
        .falling {
            position: fixed;
            top: -60px;
            z-index: 1;
            pointer-events: none;
            user-select: none;
            animation: caer linear forwards;
        }

        @keyframes caer {
            0% {
                transform: translateY(-10vh) rotate(0deg);
                opacity: 0;
            }

            10% {
                opacity: 1;
            }

            90% {
                opacity: 0.9;
            }

            100% {
                transform: translateY(115vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Contenedor del mensaje */
        .tarjeta {
            position: relative;
            z-index: 2;
            width: 88%;
            max-width: 430px;
            padding: 40px 24px;
            text-align: center;

            background: rgba(255, 255, 255, 0.48);
            border: 2px solid rgba(255, 255, 255, 0.85);
            border-radius: 30px;

            box-shadow:
                0 10px 40px rgba(219, 91, 139, 0.18),
                0 0 25px rgba(255, 255, 255, 0.5);

            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);

            animation: aparecer 1.5s ease;
        }

        @keyframes aparecer {
            from {
                opacity: 0;
                transform: scale(0.8);
            }

            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        /* Corazón decorativo */
        .corazon {
            font-size: 55px;
            display: inline-block;
            margin-bottom: 15px;
            animation: latido 1.4s infinite;
        }

        @keyframes latido {
            0%, 100% {
                transform: scale(1);
            }

            50% {
                transform: scale(1.18);
            }
        }

        /* Mensaje principal */
        h1 {
            color: #c43d70;
            font-size: clamp(28px, 7vw, 40px);
            line-height: 1.35;
            text-shadow: 1px 2px 8px rgba(196, 61, 112, 0.12);
        }

        .decoracion {
            color: #d95786;
            font-size: 26px;
            margin: 22px 0;
            letter-spacing: 8px;
        }

        .mensaje {
            color: #a83e68;
            font-size: 18px;
            line-height: 1.7;
            font-style: italic;
        }

        .firma {
            margin-top: 25px;
            font-size: 21px;
            color: #c43d70;
        }

        /* Brillitos decorativos */
        .brillo {
            position: fixed;
            color: white;
            font-size: 20px;
            animation: brillar 2s infinite alternate;
            pointer-events: none;
        }

        @keyframes brillar {
            from {
                opacity: 0.3;
                transform: scale(0.7);
            }

            to {
                opacity: 1;
                transform: scale(1.3);
            }
        }
    </style>
</head>

<body>

    <!-- Decoración de fondo -->
    <div class="brillo" style="top: 12%; left: 12%;">✧</div>
    <div class="brillo" style="top: 20%; right: 15%; animation-delay: 1s;">✦</div>
    <div class="brillo" style="bottom: 15%; left: 18%; animation-delay: 0.5s;">✧</div>
    <div class="brillo" style="bottom: 20%; right: 12%; animation-delay: 1.3s;">✦</div>

    <!-- Tarjeta romántica -->
    <div class="tarjeta">

        <div class="corazon">❤️</div>

        <h1>
            Gracias por ser<br>
            el amor de mi vida
        </h1>

        <div class="decoracion">
            🌹 ♡ 🌹
        </div>

        <p class="mensaje">
            De todas las cosas bonitas<br>
            que me dio la vida,<br>
            vos sos mi favorita. 💗
        </p>

        <div class="firma">
            Para vos, mi amor ♡
        </div>

    </div>

    <script>
        // Corazones y rosas cayendo continuamente
        const elementos = ["❤️", "💗", "💕", "🌹", "💖", "🥀", "💞"];

        function crearElemento() {
            const elemento = document.createElement("div");

            elemento.classList.add("falling");

            elemento.textContent =
                elementos[Math.floor(Math.random() * elementos.length)];

            // Posición aleatoria
            elemento.style.left = Math.random() * 100 + "vw";

            // Tamaño aleatorio
            elemento.style.fontSize =
                (18 + Math.random() * 22) + "px";

            // Velocidad de caída
            const duracion = 5 + Math.random() * 6;
            elemento.style.animationDuration = duracion + "s";

            document.body.appendChild(elemento);

            // Eliminar al terminar para no sobrecargar el celular
            setTimeout(() => {
                elemento.remove();
            }, duracion * 1000);
        }

        // Crear elementos cada 300 milisegundos
        setInterval(crearElemento, 300);

        // Crear algunos desde el principio
        for (let i = 0; i < 15; i++) {
            setTimeout(crearElemento, i * 180);
        }
    </script>

</body>
</html>
