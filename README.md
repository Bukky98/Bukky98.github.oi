<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Be My Girl</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      text-align: center;
      overflow: hidden;
      color: #fff;
    }

    h1 {
      font-size: 3rem;
      margin-bottom: 20px;
      animation: fadeIn 2s ease-in-out forwards;
      opacity: 0;
    }

    p {
      font-size: 1.5rem;
      animation: fadeIn 3s ease-in-out forwards;
      opacity: 0;
    }

    button {
      padding: 15px 30px;
      font-size: 1.2rem;
      border: none;
      border-radius: 10px;
      background-color: #fff;
      color: #ff6f91;
      cursor: pointer;
      transition: transform 0.3s, background-color 0.3s;
      animation: fadeIn 4s ease-in-out forwards;
      opacity: 0;
    }

    button:hover {
      transform: scale(1.2);
      background-color: #ffe0e6;
    }

    @keyframes fadeIn {
      to { opacity: 1; }
    }

    /* Floating hearts */
    .heart {
      position: absolute;
      font-size: 2rem;
      animation: float 6s linear infinite;
      opacity: 0.8;
      color: #ff4d6d;
      pointer-events: none;
    }

    @keyframes float {
      0% { transform: translateY(100vh) scale(0.5) rotate(0deg); opacity: 0.8; }
      50% { opacity: 1; }
      100% { transform: translateY(-10vh) scale(1) rotate(360deg); opacity: 0; }
    }
  </style>
</head>
<body>
  <div>
    <h1>Hello <span id="name"></span>!</h1>
    <p>Will you be my girl?</p>
    <button onclick="alert('Yay! 💖')">Yes 💕</button>
  </div>

  <script>
    // Add her name dynamically
    const name = "Amaka";
    document.getElementById("name").textContent = name;

    // Create floating hearts
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.textContent = '❤️';
      heart.style.left = Math.random() * window.innerWidth + 'px';
      heart.style.fontSize = (15 + Math.random() * 30) + 'px';
      heart.style.animationDuration = (4 + Math.random() * 4) + 's';
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 8000);
    }

    setInterval(createHeart, 500);
  </script>
</body>
</html>
