<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Monthsary ❤️</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Georgia', serif;
      background: url('484987706_508250888809575_4401444892575187998_n.jpg') no-repeat center center fixed;
      background-size: cover;
      height: 100vh;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
    }

    body::before {
      content: "";
      position: absolute;
      top: 0; left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.4);
      z-index: 0;
    }

    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1;
      width: 90%;
      max-width: 1000px;
    }

    .message-box {
      flex: 1;
      color: white;
      text-align: center;
      padding: 20px;
    }

    h1 {
      font-size: 2em;
      text-shadow: 1px 1px 3px black;
    }

    .romantic-link {
      background-color: #ff6b81;
      color: white;
      padding: 10px 20px;
      border-radius: 10px;
      text-decoration: none;
      font-size: 1em;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
      transition: 0.3s;
    }

    .romantic-link:hover {
      background-color: #ff4757;
      transform: scale(1.05);
    }

    .message {
      display: none;
      margin-top: 20px;
      padding: 15px;
      background: rgba(255, 255, 255, 0.2);
      border-radius: 12px;
      text-shadow: 1px 1px 2px black;
    }

    .slideshow {
      flex: 0 0 250px;
      height: 300px;
      margin-left: 20px;
      overflow: hidden;
      border-radius: 15px;
      box-shadow: 0 0 10px rgba(0,0,0,0.4);
      position: relative;
    }

    .slideshow img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      position: absolute;
      opacity: 0;
      transition: opacity 1s ease-in-out;
    }

    .slideshow img.active {
      opacity: 1;
    }

    .floating-heart {
      position: fixed;
      color: #ff4d6d;
      font-size: 16px;
      animation: floatUp 4s linear infinite;
      pointer-events: none;
      z-index: 2;
    }

    @keyframes floatUp {
      0% { transform: translateY(0) scale(1); opacity: 1; }
      100% { transform: translateY(-800px) scale(1.5); opacity: 0; }
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="message-box">
      <h1 id="personalMessage">Happy Anniversary!! ❤️</h1>
      <a href="#" class="romantic-link" onclick="showMessage()">Click for a surprise 💌</a>
      <div class="message" id="secretMessage">
        Hi langga, thank you for being the reason I smile every day. With you, I've found my best friend and my forever. 💖<br>
        I love you endlessly. 💕
      </div>
    </div>

    <div class="slideshow">
      <img src="480055143_1164811608987269_6534223973745693298_n.jpg" class="active">
      <img src="483920947_997350878557580_7180882754568707243_n.jpg">
      <img src="484987706_508250888809575_4401444892575187998_n.jpg">
    </div>
  </div>

  <script>
    function showMessage() {
      const msg = document.getElementById("secretMessage");
      msg.style.display = "block"; 
      for (let i = 0; i < 20; i++) createHeart();
    }

    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("floating-heart");
      heart.textContent = "💗";
      heart.style.left = Math.random() * 100 + "vw"; 
      heart.style.top = "100vh"; 
      heart.style.fontSize = Math.random() * 15 + 10 + "px"; 
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 4000);
    }

    // Handle URL parameters for personalization
    const urlParams = new URLSearchParams(window.location.search);
    const name = urlParams.get('name');  // Example: name=Langga
    if (name) {
      document.getElementById('personalMessage').textContent = `Happy Anniversary, ${name}!! ❤️`;
    }

    let slideIndex = 0;
    const slides = document.querySelectorAll(".slideshow img");
    setInterval(() => {
      slides[slideIndex].classList.remove("active");
      slideIndex = (slideIndex + 1) % slides.length;
      slides[slideIndex].classList.add("active");
    }, 3000);
  </script>

</body>
</html>
