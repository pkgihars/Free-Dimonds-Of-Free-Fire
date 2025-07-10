<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Free Fire Diamonds Generator</title>
  <style>
    body {
      background: #111;
      color: #fff;
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 40px;
    }
    .container {
      background: #222;
      border-radius: 10px;
      padding: 30px;
      max-width: 400px;
      margin: auto;
      box-shadow: 0 0 10px #00ffcc;
    }
    input, select, button {
      width: 100%;
      padding: 12px;
      margin: 10px 0;
      border-radius: 5px;
      border: none;
    }
    button {
      background: #00ffcc;
      color: #000;
      font-weight: bold;
      cursor: pointer;
    }
    .loading {
      display: none;
      margin-top: 20px;
    }
    .progress-bar {
      width: 0%;
      height: 20px;
      background: #00ffcc;
      border-radius: 5px;
      transition: 1s;
    }
    .final-message {
      display: none;
      margin-top: 30px;
      font-size: 24px;
      color: #ff4444;
      font-weight: bold;
      animation: shake 0.5s infinite;
    }

    @keyframes shake {
      0% { transform: translateX(0); }
      25% { transform: translateX(-4px); }
      50% { transform: translateX(4px); }
      75% { transform: translateX(-4px); }
      100% { transform: translateX(0); }
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>🎮 Free Fire Diamonds Generator</h2>
    <input type="text" id="username" placeholder="Enter your Free Fire username" />
    <select id="amount">
      <option value="100">100 Diamonds</option>
      <option value="500">500 Diamonds</option>
      <option value="1000">1000 Diamonds</option>
      <option value="Unlimited">Unlimited 😎</option>
    </select>
    <button onclick="startFakeGenerator()">Generate Diamonds</button>

    <div class="loading" id="loadingBox">
      <p>Connecting to Garena servers...</p>
      <div class="progress-bar" id="progressBar"></div>
    </div>

    <div class="final-message" id="finalMsg">
      😂🖕 Kya lega looola? 🖕🖕
    </div>
  </div>

  <script>
    function startFakeGenerator() {
      const username = document.getElementById("username").value;
      if (!username) {
        alert("Please enter a username!");
        return;
      }

      document.getElementById("loadingBox").style.display = "block";
      const bar = document.getElementById("progressBar");
      bar.style.width = "0%";

      let progress = 0;
      const interval = setInterval(() => {
        progress += Math.random() * 20;
        if (progress >= 100) {
          progress = 100;
          clearInterval(interval);
          setTimeout(() => {
            document.getElementById("loadingBox").style.display = "none";
            document.getElementById("finalMsg").style.display = "block";
          }, 1000);
        }
        bar.style.width = progress + "%";
      }, 500);
    }
  </script>
</body>
</html>
