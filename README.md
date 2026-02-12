<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sala de Escape para Pipito 💖</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #ffe6f0, #e6f7ff, #f0ffe6); /* Gradiente pastel con verde */
            color: #333;
            margin: 0;
            padding: 20px;
            text-align: center;
            overflow-x: hidden;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        h1, h2 {
            color: #d63384; /* Rosa aesthetic */
        }
        .heart {
            color: #ff6b9d;
            font-size: 2em;
        }
        .puzzle {
            display: none; /* Ocultos por defecto */
            margin: 20px 0;
        }
        .active {
            display: block;
        }
        input, button {
            padding: 10px;
            margin: 10px;
            border: 2px solid #a8dadc; /* Verde suave */
            border-radius: 10px;
            font-size: 1em;
        }
        button {
            background: #a8dadc;
            color: white;
            cursor: pointer;
            transition: background 0.3s;
        }
        button:hover {
            background: #76c893;
        }
        .success {
            color: #2d6a4f; /* Verde oscuro */
            font-weight: bold;
        }
        .error {
            color: #e63946;
        }
        /* Animación de corazones flotando */
        .floating-hearts {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
        }
        .heart-float {
            position: absolute;
            font-size: 2em;
            color: #ff6b9d;
            animation: float 5s linear infinite;
        }
        @keyframes float {
            0% { transform: translateY(100vh); opacity: 1; }
            100% { transform: translateY(-10vh); opacity: 0; }
        }
    </style>
</head>
<body>
    <div class="floating-hearts">
        <div class="heart-float" style="left: 10%; animation-delay: 0s;">💖</div>
        <div class="heart-float" style="left: 30%; animation-delay: 1s;">🌸</div>
        <div class="heart-float" style="left: 50%; animation-delay: 2s;">💚</div>
        <div class="heart-float" style="left: 70%; animation-delay: 3s;">🍣</div>
        <div class="heart-float" style="left: 90%; animation-delay: 4s;">🎨</div>
    </div>
    <div class="container">
        <h1>Me costo un huevo pero te hice una pagina web para vos <span class="heart">💖</span></h1>
        <p>Resolvé los acertijos basados en nosotros :)</p>
        
        <!-- Puzzle 1: Cómo nos conocimos -->
        <div id="puzzle1" class="puzzle active">
            <h2>Habitación 1: La Fiesta Juana</h2>
            <p>¿Sobre qué se trataba el chiste malo que te conté en lo de Juana?</p>
            <input type="text" id="answer1" placeholder="Tu respuesta">
            <button onclick="checkPuzzle1()">Verificar</button>
            <p id="feedback1"></p>
        </div>
        
        <!-- Puzzle 2: Fechas importantes -->
        <div id="puzzle2" class="puzzle">
            <h2>Habitación 2: Fechas importantes</h2>
            <p>¿Cuál es la fecha en que empezamos a hablar? (Incluí el día, mes y año)</p>
            <input type="text" id="answer2" placeholder="Ej. 15 de enero del 2022">
            <p>¿Y la fecha en que nos pusimos de novios?</p>
            <input type="text" id="answer2b" placeholder="Ej. 10 de mayo del 2023">
            <button onclick="checkPuzzle2()">Verificar</button>
            <p id="feedback2"></p>
        </div>
        
        <!-- Puzzle 3: Lugares y momentos -->
        <div id="puzzle3" class="puzzle">
            <h2>Habitación 3: canciones</h2>
            <p> nombre y artista de la cancion que te recomende en lo de juana </p>
            <input type="text" id="answer3" placeholder="Canción completa">
            <button onclick="checkPuzzle3()">Verificar</button>
            <p id="feedback3"></p>
        </div>
        
        <!-- Puzzle 4: Primer apodo -->
        <div id="puzzle4" class="puzzle">
            <h2>Habitación 4: tiernito</h2>
            <p>¿Cuál fue el primer apodo que tuve?</p>
            <input type="text" id="answer4" placeholder="Apodo">
            <button onclick="checkPuzzle4()">Verificar</button>
            <p id="feedback4"></p>
        </div>
        
        <!-- Puzzle 5: Primer beso -->
        <div id="puzzle5" class="puzzle">
            <h2>Habitación 5: donde moriste </h2>
            <p>¿Dónde te di mi primer beso?</p>
            <input type="text" id="answer5" placeholder="Lugar">
            <button onclick="checkPuzzle5()">Verificar</button>
            <p id="feedback5"></p>
        </div>
        
        <!-- Puzzle 6: Dibujo especial -->
        <div id="puzzle6" class="puzzle">
            <h2>Habitación 6: Dibujo Especial</h2>
            <p>¿Qué fue lo primero que le dibujé?</p>
            <input type="text" id="answer6" placeholder="Dibujo">
            <button onclick="checkPuzzle6()">Verificar</button>
            <p id="feedback6"></p>
        </div>
        
        <!-- Puzzle 7: Primera cita -->
        <div id="puzzle7" class="puzzle">
            <h2>Habitación 7: Primera Cita</h2>
            <p>¿Qué tomamos en nuestra primera cita/juntada?</p>
            <input type="text" id="answer7" placeholder="Bebida o lugar">
            <button onclick="checkPuzzle7()">Verificar</button>
            <p id="feedback7"></p>
        </div>
        
        <!-- Puzzle 8: Primera película en el cine (nuevo) -->
        <div id="puzzle8" class="puzzle">
            <h2>Habitación 8: Primera Película en el Cine</h2>
            <p>¿Cuál fue la primera película que vimos en el cine?</p>
            <input type="text" id="answer8" placeholder="Película">
            <button onclick="checkPuzzle8()">Verificar</button>
            <p id="feedback8"></p>
        </div>
        
        <!-- Mensaje final -->
        <div id="final" class="puzzle">
            <h2>¡Has escapado! <span class="heart">💖</span></h2>
            <p>Feliz San Valentín gordito. Por otro San Valentín juntos. Quiero decirte que me encanta y decido elegirte. Me gusta cuando nos reímos sin razón, cuando nos entendemos sin hablar, y también cuando aprendemos a escucharnos mejor. Constantemente siento que aprendo con vos algo nuevo y eso me encanta. Hacer esto me trajo mucha nostalgia. Le dedique mucho tiempo y amor espero que te haya gustado Te amo.</p>
            <p>Feliz San Valentin pipito 🌸🍣🎨</p>
        </div>
    </div>

    <script>
        // Función para mostrar siguiente puzzle
        function showNext(currentId, nextId) {
            document.getElementById(currentId).classList.remove('active');
            document.getElementById(nextId).classList.add('active');
        }

        // Puzzle 1: Chiste sobre paraguas
        function checkPuzzle1() {
            const answer = document.getElementById('answer1').value.toLowerCase();
            const feedback = document.getElementById('feedback1');
            if (answer.includes('paraguas')) {
                feedback.innerHTML = '<span class="success">¡Correcto! Ese chiste te hizo reír muucho. Siguiente habitación...</span>';
                setTimeout(() => showNext('puzzle1', 'puzzle2'), 2000);
            } else {
                feedback.innerHTML = '<span class="error">¡Casi! Pensa en algo relacionado con lluvia o mojarse. Inténtalo de nuevo.</span>';
            }
        }

        // Puzzle 2: Fechas
        function checkPuzzle2() {
            const answer2 = document.getElementById('answer2').value.toLowerCase();
            const answer2b = document.getElementById('answer2b').value.toLowerCase();
            const feedback = document.getElementById('feedback2');
            if (answer2.includes('7') && answer2.includes('diciembre') && answer2.includes('2023') &&
                answer2b.includes('24') && answer2b.includes('marzo') && answer2b.includes('2024')) {
                feedback.innerHTML = '<span class="success">crackkkk. Siguiente habitación...</span>';
                setTimeout(() => showNext('puzzle2', 'puzzle3'), 2000);
            } else {
                feedback.innerHTML = '<span class="error">¡Oops! Revisa las fechas..</span>';
            }
        }

        // Puzzle 3: Canción
        function checkPuzzle3() {
            const answer = document.getElementById('answer3').value.toLowerCase();
            const feedback = document.getElementById('feedback3');
            if (answer.includes('tus vueltas') && answer.includes('milo j')) {
                feedback.innerHTML = '<span class="success">¡Sí! Es esa brooo. Siguiente habitación...</span>';
                setTimeout(() => showNext('puzzle3', 'puzzle4'), 2000);
            } else {
                feedback.innerHTML = '<span class="error">¡Cerca! Empieza con "Tus" y es de Milo J.</span>';
            }
        }

        // Puzzle 4: Primer apodo
        function checkPuzzle4() {
            const answer = document.getElementById('answer4').value.toLowerCase();
            const feedback = document.getElementById('feedback4');
            if (answer.includes('amarillitos')) {
                feedback.innerHTML = '<span class="success">¡Correcto! naranjuuu. Siguiente habitación...</span>';
                setTimeout(() => showNext('puzzle4', 'puzzle5'), 2000);
            } else {
                feedback.innerHTML = '<span class="error">¡Inténtalo! Pensa en algo relacionado con mis ojos.</span>';
            }
        }

        // Puzzle 5: Primer beso
        function checkPuzzle5() {
            const answer = document.getElementById('answer5').value.toLowerCase();
            const feedback = document.getElementById('feedback5');
            if (answer.includes('plaza') && answer.includes('barrio chino')) {
                feedback.innerHTML = '<span class="success">¡Sí! Ese momento fue mágico. Siguiente habitación...</span>';
                setTimeout(() => showNext('puzzle5', 'puzzle6'), 2000);
            } else {
                feedback.innerHTML = '<span class="error">¡Cerca! Es un lugar especial cerca de un barrio famoso.</span>';
            }
        }

        // Puzzle 6: Dibujo especial
        function checkPuzzle6() {
            const answer = document.getElementById('answer6').value.toLowerCase();
            const feedback = document.getElementById('feedback6');
            if (answer.includes('akira')) {
                feedback.innerHTML = '<span class="success">¡Perfecto! Ese dibujo te lo hice xq lo soñe jaja. Siguiente habitación...</span>';
                setTimeout(() => showNext('puzzle6', 'puzzle7'), 2000);
            } else {
                feedback.innerHTML = '<span class="error">¡Inténtalo! una gorda que amo...</span>';
            }
        }

        // Puzzle 7: Primera cita
        function checkPuzzle7() {
            const answer = document.getElementById('answer7').value.toLowerCase();
            const feedback = document.getElementById('feedback7');
            if (answer.includes('starbucks')) {
                feedback.innerHTML = '<span class="success">¡Sí! Ese café fue el comienzo perfecto. Siguiente habitación...</span>';
                setTimeout(() => showNext('puzzle7', 'puzzle8'), 2000);
            } else {
                feedback.innerHTML = '<span class="error">¡Cerca! Pensa en una cadena de cafés famosa.</span>';
            }
        }

        // Puzzle 8: Primera película en el cine (nuevo)
        function checkPuzzle8() {
            const answer = document.getElementById('answer8').value.toLowerCase();
            const feedback = document.getElementById('feedback8');
            if (answer.includes('kung fu panda')) {
                feedback.innerHTML = '<span class="success">¡Sí! Esa película fue inolvidable. ¡Al mensaje final!</span>';
                setTimeout(() => showNext('puzzle8', 'final'), 2000);
            } else {
                feedback.innerHTML = '<span class="error">¡Cerca! Pensa en una película animada con animales guerreros.</span>';
            }
        }
    </script>
</body>
</html>
