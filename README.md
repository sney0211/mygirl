<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Para Mi Niña 💖</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"/>
  <style>
    @keyframes pulse-glow {
      0%, 100% {
        box-shadow: 0 0 20px 5px rgba(255, 182, 193, 0.6);
      }
      50% {
        box-shadow: 0 0 30px 15px rgba(255, 105, 180, 0.8);
      }
    }

    @keyframes float {
      0%, 100% {
        transform: translateY(0);
      }
      50% {
        transform: translateY(-20px);
      }
    }

    .glow-animation {
      animation: pulse-glow 3s infinite;
    }

    .hover-animate {
      transition: all 0.3s ease;
    }

    .hover-animate:hover {
      transform: translateY(-5px);
    }

    .heart {
      position: absolute;
      pointer-events: none;
      animation: float 4s ease-in-out infinite;
      opacity: 0.8;
    }
  </style>
</head>

<body class="bg-gradient-to-br from-pink-100 via-red-50 to-pink-200 min-h-screen flex items-center justify-center p-4 overflow-hidden" id="body">

  <!-- Corazones flotantes -->
  <div id="hearts-container"></div>

  <!-- Tarjeta principal -->
  <div class="max-w-sm bg-white rounded-3xl overflow-hidden border-4 border-pink-200 glow-animation hover-animate">
    <img class="w-full h-64 object-cover" src="https://blog.verdiflora.com/wp-content/uploads/2022/04/significado-del-numero-de-rosas-en-un-ramo-de-flores-a-domicilio.png" alt="Ramo de rosas" />
    
    <div class="p-6 text-center">
      <h2 class="text-3xl font-bold text-pink-600 mb-4 animate__animated animate__pulse animate__infinite">
        Para Mi Niña 💕
      </h2>

      <p class="text-gray-700 text-base leading-relaxed mb-4">
        Desde que llegaste, todo se siente más bonito. Me gusta la tranquilidad que transmites y la forma tan especial en la que haces que cada conversación valga la pena.
        No tengo prisas, solo ganas de seguir conociéndote y construir algo lindo, a nuestro ritmo.
      </p>

      <div class="flex justify-center space-x-2 mb-4">
        <span class="text-2xl">💖</span>
        <span class="text-2xl">🌸</span>
        <span class="text-2xl">🌹</span>
        <span class="text-2xl">💌</span>
      </div>

      <button onclick="showSurprise()" class="bg-pink-500 hover:bg-pink-600 text-white font-bold py-3 px-6 rounded-full transition-all transform hover:scale-105 w-full">
        Hay algo que quiero decirte 💖
      </button>
    </div>
  </div>

  <!-- Modal -->
  <div id="surpriseModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center hidden z-50 p-4">
    <div class="bg-white rounded-2xl overflow-hidden max-w-md w-full border-4 border-pink-200">
      <div class="p-6 text-center">
        <h3 class="text-2xl font-bold text-pink-600 mb-4">
          Esto es para ti, mi niña 💕
        </h3>

        <div class="text-5xl mb-4 animate__animated animate__heartBeat">💌</div>
        
        <div class="text-left space-y-4 text-gray-700 mb-6">
          <p class="italic border-l-4 border-pink-300 pl-4 py-1">
            "A veces las personas llegan sin avisar… y de alguna forma lo cambian todo."
          </p>
          
          <p>
            Quiero que sepas algo:
          </p>
          
          <ul class="list-disc list-inside space-y-2">
            <li>Me gusta cómo te expresas y la vibra tan linda que transmites.</li>
            <li>Cada vez que hablamos, me quedo con una sensación bonita.</li>
            <li>Aunque estemos aprendiendo a conocernos, eso ya significa mucho para mí.</li>
            <li>Tu presencia, incluso a la distancia, se siente cercana.</li>
          </ul>
          
          <p class="mt-4">
            No sé a dónde nos lleve el camino, pero sí sé que me gusta recorrerlo contigo, sin prisas y con sinceridad.
          </p>
        </div>
        
        <button onclick="closeModal()" class="bg-pink-500 hover:bg-pink-600 text-white font-bold py-2 px-6 rounded-full transition-all transform hover:scale-105">
          Gracias por leer 💝
        </button>
      </div>
    </div>
  </div>

  <script>
    function createHearts() {
      const container = document.getElementById('hearts-container');
      const colors = ['#ffb6c1', '#ff69b4', '#ff1493', '#db7093'];
      
      for (let i = 0; i < 15; i++) {
        const heart = document.createElement('div');
        heart.innerHTML = '💖';
        heart.className = 'heart text-2xl';
        heart.style.position = 'fixed';
        heart.style.zIndex = '30';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.top = Math.random() * 100 + 'vh';
        heart.style.animationDelay = Math.random() * 5 + 's';
        heart.style.color = colors[Math.floor(Math.random() * colors.length)];
        heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
        container.appendChild(heart);
      }
    }

    function showSurprise() {
      document.getElementById('surpriseModal').classList.remove('hidden');
      document.body.style.overflow = 'hidden';
    }

    function closeModal() {
      document.getElementById('surpriseModal').classList.add('hidden');
      document.body.style.overflow = 'auto';
    }

    document.getElementById('body').addEventListener('click', function(e) {
      if (!e.target.closest('button')) {
        const colors = ['#ffb6c1', '#ff69b4', '#ff1493', '#db7093'];
        const heart = document.createElement('div');
        heart.innerHTML = ['💖', '💕', '💗', '💓', '💘'][Math.floor(Math.random() * 5)];
        heart.className = 'heart text-2xl absolute';
        heart.style.position = 'fixed';
        heart.style.zIndex = '50';
        heart.style.left = e.clientX + 'px';
        heart.style.top = e.clientY + 'px';
        heart.style.color = colors[Math.floor(Math.random() * colors.length)];
        document.getElementById('hearts-container').appendChild(heart);
        
        setTimeout(() => heart.remove(), 4000);
      }
    });

    window.onload = createHearts;
  </script>
</body>
</html>
