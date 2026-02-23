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
    cursor: none;
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
    margin: 10px;
    position: relative;
  }

  button:hover {
    transform: scale(1.2);
    background-color: #ffe0e6;
  }

  @keyframes fadeIn {
    to { opacity: 1; }
  }

  .heart {
    position: absolute;
    font-size: 20px;
    pointer-events: none;
    animation: floatUp 6s linear infinite;
    opacity: 0.8;
    color: #ff4d6d;
  }

  @keyframes floatUp {
    0% { transform: translateY(0) scale(0.5) rotate(0deg); opacity: 0.8; }
    50% { opacity: 1; }
    100% { transform: translateY(-300px) scale(1) rotate(360deg); opacity: 0; }
  }

  .runner {
    position: absolute;
    font-size: 2rem;
    transition: all 0.3s;
  }
</style>
</head>
<body>
<div>
  <h1>Hello <span id="name"></span>!</h1>
  <p>Will you be my girl?</p>
  <button id="yesBtn">Yes 💕</button>
  <button id="noBtn">No 😢</button>
</div>

<script>
  // Add her name dynamically
  const name = "Amaka";
  document.getElementById("name").textContent = name;

  // Floating hearts
  function createHeart(x, y) {
    const heart = document.createElement('div');
    heart.classList.add('heart');
    heart.textContent = '❤️';
    heart.style.left = x - 10 + 'px';
    heart.style.top = y - 10 + 'px';
    heart.style.fontSize = (15 + Math.random() * 25) + 'px';
    heart.style.animationDuration = (4 + Math.random() * 4) + 's';
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 6000);
  }

  document.addEventListener('mousemove', e => createHeart(e.clientX, e.clientY));
  setInterval(() => {
    createHeart(Math.random() * window.innerWidth, window.innerHeight + 20);
  }, 500);

  // Yes & No buttons
  const yesBtn = document.getElementById('yesBtn');
  const noBtn = document.getElementById('noBtn');

  yesBtn.addEventListener('click', () => alert("I'm so happy you said yes! 💖"));
  noBtn.addEventListener('mouseenter', () => {
    const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
    const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
    noBtn.style.left = x + 'px';
    noBtn.style.top = y + 'px';
    noBtn.style.position = 'absolute';
  });

  // Add a running emoji
  const runner = document.createElement('div');
  runner.classList.add('runner');
  runner.textContent = '🏃‍♂️';
  document.body.appendChild(runner);

  // Move the runner randomly every second
  setInterval(() => {
    const x = Math.random() * (window.innerWidth - 50);
    const y = Math.random() * (window.innerHeight - 50);
    runner.style.left = x + 'px';
    runner.style.top = y + 'px';
  }, 1000);
</script>
</body>
</html>
