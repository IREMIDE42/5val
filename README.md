# 5val
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Ugochi ❤️</title>

<style>
html, body {
  margin: 0;
  padding: 0;
  scroll-behavior: smooth;
  font-family: 'Segoe UI', sans-serif;
}

section {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  text-align: center;
  position: relative;
  overflow: hidden;
  padding: 20px;
}

.box {
  background: rgba(255,255,255,0.18);
  padding: 35px;
  border-radius: 30px;
  max-width: 520px;
  width: 100%;
  backdrop-filter: blur(10px);
}

button {
  margin-top: 20px;
  padding: 14px 32px;
  border: none;
  border-radius: 30px;
  font-size: 16px;
  cursor: pointer;
}

button:active {
  transform: scale(0.96);
}

/* Backgrounds */
#p1 { background: linear-gradient(135deg,#ff758c,#ff7eb3); }
#p2 { background: linear-gradient(135deg,#ff5f6d,#ffc371); }
#p3 { background: linear-gradient(135deg,#f857a6,#ff5858); }
#p4 { background: linear-gradient(135deg,#c471f5,#fa71cd); }
#p5 { background: linear-gradient(135deg,#ff416c,#ff4b2b); }

/* Game */
.heart {
  position: absolute;
  font-size: 26px;
  cursor: pointer;
  animation: fall 4.5s linear forwards;
}

@keyframes fall {
  from { top: -40px; opacity: 1; }
  to { top: 110vh; opacity: 0; }
}

.score {
  position: absolute;
  top: 15px;
  right: 15px;
  font-size: 18px;
}

/* Signature */
.signature {
  margin-top: 40px;
  font-style: italic;
  font-size: 18px;
}
.signature span {
  display: block;
  font-size: 22px;
  margin-top: 6px;
}
</style>
</head>

<body>

<!-- MUSIC -->
<audio id="bgMusic" loop>
  <source src="YOUR_MUSIC_HERE.mp3" type="audio/mpeg">
</audio>

<!-- PAGE 1 -->
<section id="p1">
  <div class="box">
    <h1>Hi Ugochi ❤️</h1>
    <p>
      I made this just for you.  
      Please take your time and enjoy it.
    </p>
    <button onclick="startExperience()">Begin 💕</button>
  </div>
</section>

<!-- PAGE 2 -->
<section id="p2">
  <div class="box">
    <h2>How I Feel About You</h2>
    <p>
      Loving you feels natural.  
      Being around you feels right.  
      You bring peace to my heart.
    </p>
    <button onclick="location.href='#p3'">Next ➡️</button>
  </div>
</section>

<!-- PAGE 3 -->
<section id="p3">
  <div class="box">
    <h2>Why You’re Special 🌹</h2>
    <p>
      Your smile lifts me.  
      Your presence calms me.  
      Your love completes me.
    </p>
    <button onclick="location.href='#p4'">Play a Game 💖</button>
  </div>
</section>

<!-- PAGE 4 – MINI GAME -->
<section id="p4">
  <div class="score">❤️ Score: <span id="score">0</span></div>

  <div class="box">
    <h2>Catch the Hearts 💕</h2>
    <p>
      Tap the hearts to collect love.  
      Every heart is for you, Ugochi ❤️
    </p>
    <button onclick="location.href='#p5'">Finish 💘</button>
  </div>
</section>

<!-- PAGE 5 -->
<section id="p5">
  <div class="box">
    <h1>Will You Be My Valentine? ❤️</h1>

    <button onclick="alert('You just made me the happiest man alive ❤️')">
      YES 😍
    </button>
    <button onclick="alert('You’re still my Valentine 😌❤️')">
      NO 🙈
    </button>

    <div class="signature">
      Yours sincerely,
      <span>💖 Mide</span>
    </div>
  </div>
</section>

<script>
let score = 0;

function startExperience() {
  document.getElementById("bgMusic").play();
  location.href = "#p2";
}

function createHeart() {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = "❤️";
  heart.style.left = Math.random() * 90 + "vw";
  heart.style.top = "-40px";

  heart.onclick = () => {
    score++;
    document.getElementById("score").innerText = score;
    heart.remove();
  };

  document.getElementById("p4").appendChild(heart);

  setTimeout(() => heart.remove(), 4500);
}

setInterval(() => {
  if (location.hash === "#p4") {
    createHeart();
  }
}, 700);
</script>

</body>
</html>
