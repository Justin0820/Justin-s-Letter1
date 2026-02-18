# Justin-s-Letter1
For Audrey
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>For You ❤️</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #ffd6e7 0%, #ffe5f0 50%, #fff 100%);
  font-family: 'Arial', sans-serif;
  text-align: center;
  overflow: hidden;
}

.container {
  background: white;
  padding: 50px;
  border-radius: 30px;
  box-shadow: 0 15px 50px rgba(0, 0, 0, 0.2);
  max-width: 700px;
  position: relative;
  z-index: 10;
}

h1 {
  color: #ff2e7a;
  font-size: 3em;
  margin-bottom: 10px;
  animation: pulse 2s ease-in-out infinite;
}

.subtitle {
  color: #ff6b9d;
  font-size: 1.1em;
  margin-bottom: 30px;
}

.canvas-container {
  position: relative;
  display: inline-block;
  margin: 30px 0;
}

canvas {
  filter: drop-shadow(0 5px 15px rgba(255, 46, 122, 0.3));
  display: block;
}

.letter {
  margin-top: 30px;
  font-size: 1.3em;
  line-height: 1.8;
  color: #333;
  animation: fadeIn 1.5s ease-in;
}

.letter br {
  margin-bottom: 15px;
}

/* Butterfly Animation */
.butterfly {
  position: fixed;
  width: 50px;
  height: 50px;
  animation: flutter 4s infinite;
  pointer-events: none;
}

.butterfly:nth-child(1) {
  top: 10%;
  left: 5%;
  animation: flutter 5s infinite;
}

.butterfly:nth-child(2) {
  top: 20%;
  right: 8%;
  animation: flutter 6s infinite;
}

.butterfly:nth-child(3) {
  bottom: 15%;
  left: 10%;
  animation: flutter 5.5s infinite;
}

@keyframes flutter {
  0%, 100% {
    transform: translateY(0px) translateX(0px) rotate(0deg);
    opacity: 0.8;
  }
  25% {
    transform: translateY(-30px) translateX(20px) rotate(5deg);
    opacity: 1;
  }
  50% {
    transform: translateY(-60px) translateX(0px) rotate(0deg);
    opacity: 0.9;
  }
  75% {
    transform: translateY(-30px) translateX(-20px) rotate(-5deg);
    opacity: 1;
  }
}

@keyframes pulse {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.05);
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.heart-glow {
  animation: glow 2s ease-in-out infinite;
}

@keyframes glow {
  0%, 100% {
    filter: drop-shadow(0 5px 15px rgba(255, 46, 122, 0.3));
  }
  50% {
    filter: drop-shadow(0 8px 25px rgba(255, 46, 122, 0.6));
  }
}
</style>
</head>

<body>
<!-- Butterflies -->
<svg class="butterfly" viewBox="0 0 100 100">
  <ellipse cx="30" cy="40" rx="15" ry="20" fill="#ff69b4" opacity="0.9"/>
  <ellipse cx="30" cy="60" rx="15" ry="20" fill="#ff1493" opacity="0.85"/>
  <ellipse cx="70" cy="40" rx="15" ry="20" fill="#ff69b4" opacity="0.9"/>
  <ellipse cx="70" cy="60" rx="15" ry="20" fill="#ff1493" opacity="0.85"/>
  <circle cx="50" cy="50" r="6" fill="#ffd6e7"/>
</svg>

<svg class="butterfly" viewBox="0 0 100 100">
  <ellipse cx="30" cy="40" rx="15" ry="20" fill="#ff69b4" opacity="0.9"/>
  <ellipse cx="30" cy="60" rx="15" ry="20" fill="#ff1493" opacity="0.85"/>
  <ellipse cx="70" cy="40" rx="15" ry="20" fill="#ff69b4" opacity="0.9"/>
  <ellipse cx="70" cy="60" rx="15" ry="20" fill="#ff1493" opacity="0.85"/>
  <circle cx="50" cy="50" r="6" fill="#ffd6e7"/>
</svg>

<svg class="butterfly" viewBox="0 0 100 100">
  <ellipse cx="30" cy="40" rx="15" ry="20" fill="#ff69b4" opacity="0.9"/>
  <ellipse cx="30" cy="60" rx="15" ry="20" fill="#ff1493" opacity="0.85"/>
  <ellipse cx="70" cy="40" rx="15" ry="20" fill="#ff69b4" opacity="0.9"/>
  <ellipse cx="70" cy="60" rx="15" ry="20" fill="#ff1493" opacity="0.85"/>
  <circle cx="50" cy="50" r="6" fill="#ffd6e7"/>
</svg>

<div class="container">
  <h1>❤️ For You ❤️</h1>
  <p class="subtitle">With all my love...</p>
  
  <div class="canvas-container">
    <canvas id="heart" width="400" height="350" class="heart-glow"></canvas>
  </div>

  <div class="letter">
    I'm truly sorry that I hurt your feelings.<br><br>
    You mean the world to me,<br>
    and I promise to do better.<br><br>
    I love you so much. 💕
  </div>
</div>

<script>
const canvas = document.getElementById("heart");
const ctx = canvas.getContext("2d");

// Create gradient for heart
const gradient = ctx.createLinearGradient(0, 0, 0, canvas.height);
gradient.addColorStop(0, '#ff2e7a');
gradient.addColorStop(0.5, '#ff69b4');
gradient.addColorStop(1, '#ff1493');

ctx.fillStyle = gradient;
ctx.strokeStyle = "#ff2e7a";
ctx.lineWidth = 2;

// Draw filled heart with improved curve
ctx.beginPath();

const points = [];
for (let t = 0; t < Math.PI * 2; t += 0.01) {
  let x = 16 * Math.pow(Math.sin(t), 3);
  let y = 13 * Math.cos(t) - 5 * Math.cos(2*t) - 2 * Math.cos(3*t) - Math.cos(4*t);
  x = x * 12 + 200;
  y = -y * 12 + 175;
  points.push({x, y});
  
  if (t === 0) {
    ctx.moveTo(x, y);
  } else {
    ctx.lineTo(x, y);
  }
}

ctx.closePath();
ctx.fill();
ctx.stroke();

// Add heart shine effect
ctx.fillStyle = "rgba(255, 255, 255, 0.3)";
ctx.beginPath();
ctx.arc(160, 140, 25, 0, Math.PI * 2);
ctx.fill();
</script>
</body>
</html>
