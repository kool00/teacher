<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Ma'am 🎉</title>

<style>
  body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, #ffdde1, #ee9ca7);
    overflow: hidden;
    position: relative;
  }

  .screen {
    display: none;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 20px;
    gap: 15px;
    opacity: 0;
    transform: scale(0.9);
    transition: all 0.6s ease;
    position: relative;
    z-index: 2;
    text-align: center;
    max-width: 700px;
  }

  .active { display: flex; opacity: 1; transform: scale(1); }

  h1 { font-size: 1.8rem; color: #c2185b; }
  p { font-size: 1rem; color: #444; line-height: 1.6; }

  button {
    padding: 10px 20px;
    border: none;
    border-radius: 12px;
    background: #d81b60;
    color: white;
    cursor: pointer;
    font-size: 1rem;
    transition: 0.3s;
  }

  button:hover {
    transform: scale(1.1);
    box-shadow: 0 0 15px rgba(216,27,96,0.6);
  }

  img {
    width: 200px;
    border-radius: 15px;
    box-shadow: 0 0 15px rgba(0,0,0,0.2);
  }

  /* Floating Emojis */
  .floating {
    position: fixed;
    bottom: -20px;
    font-size: 22px;
    animation: floatUp 6s linear infinite;
    z-index: 1;
    opacity: 0.8;
    pointer-events: none;
  }

  @keyframes floatUp {
    from { transform: translateY(0) scale(1); opacity: 1; }
    to { transform: translateY(-110vh) scale(1.6); opacity: 0; }
  }

  /* Fireworks */
  canvas {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    z-index: 0;
    pointer-events: none;
  }

  .memories-img, .memories-video {
    width: 80%;
    max-width: 400px;
    border-radius: 15px;
    box-shadow: 0 0 15px rgba(0,0,0,0.2);
  }

</style>
</head>

<body>

<canvas id="fireworks"></canvas>

<!-- PAGE 1 -->
<div id="screen1" class="screen active">
  <h1>🎉 Happy Birthday Ma’am 🎉</h1>
  <p>Today we celebrate not just your birthday,
  but the beautiful impact you have had on Class 11B.</p>
  <button onclick="showScreen('journey')">Next</button>
</div>

<!-- PAGE 2 -->
<div id="screenJourney" class="screen">
  <h1>📖 Our Journey With You</h1>
  <p>
    From the very first day you walked into our classroom,
    we felt this year would be special.

    Through your guidance, discipline, and encouragement,
    you shaped us into better students and better individuals.
  </p>
  <button onclick="showScreen('memories')">Next</button>
</div>

<!-- PAGE 3 -->
<div id="screenMemories" class="screen">
  <h1>📸 Beautiful Memories</h1>
  <div id="memContainer"></div>
  <button onclick="prevMemory()">Previous</button>
  <button onclick="nextMemory()">Next</button>
</div>

<!-- PAGE 4 -->
<div id="screenThanks" class="screen">
  <h1>❤️ Thank You Ma’am ❤️</h1>
  <p>
    Thank you for being our Class Teacher and Chemistry guide.
    Your patience, strength, and dedication inspire us every day.
  </p>
  <button onclick="showScreen('request')">Next</button>
</div>

<!-- PAGE 5 -->
<div id="screenRequest" class="screen">
  <h1>🎁 One Small Birthday Request 🎁</h1>
  <p>
    On your special day,
    we humbly request one full PE period
    as your birthday gift to Class 11B 😇
    plzz plzzz mam , dont say no!!
  </p>
  <button onclick="showScreen('final')">Final</button>
</div>

<!-- PAGE 6 -->
<div id="screenFinal" class="screen">
  <h1>🌸 Happy Birthday Once Again 🌸</h1>
  <p>
    We may forget formulas,
    but we will never forget your guidance.

    — Made with 💖 by Class 11B
  </p>
</div>

<script>
function showScreen(next) {
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  const map = {
    journey: 'screenJourney',
    memories: 'screenMemories',
    request: 'screenRequest',
    final: 'screenFinal'
  };
  if(next === 'thanks') {
    document.getElementById('screenThanks').classList.add('active');
  } else {
    document.getElementById(map[next]).classList.add('active');
  }
}

/* Floating Emojis */
function startFloatingEmojis() {
  const emojis = ["🥳","💖","🌸","✨","🎉"];
  setInterval(() => {
    const emoji = document.createElement("div");
    emoji.classList.add("floating");
    emoji.innerHTML = emojis[Math.floor(Math.random() * emojis.length)];
    emoji.style.left = Math.random() * 100 + "vw";
    emoji.style.fontSize = (Math.random() * 20 + 15) + "px";
    emoji.style.animationDuration = (Math.random() * 3 + 4) + "s";
    document.body.appendChild(emoji);
    setTimeout(() => emoji.remove(), 6000);
  }, 500);
}
startFloatingEmojis();

/* Fireworks */
const canvas = document.getElementById("fireworks");
const ctx = canvas.getContext("2d");
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
let particles = [];

function random(min,max){return Math.random()*(max-min)+min;}

function createFirework(){
  const x=random(0,canvas.width), y=canvas.height;
  const color=`hsl(${random(0,360)},100%,60%)`;
  for(let i=0;i<50;i++){
    particles.push({x,y,r:random(1,3),dx:random(-4,4),dy:random(-10,-4),life:random(60,120),color});
  }
}

function draw(){
  ctx.clearRect(0,0,canvas.width,canvas.height);
  particles.forEach((p,i)=>{
    ctx.beginPath();
    ctx.arc(p.x,p.y,p.r,0,2*Math.PI);
    ctx.fillStyle=p.color;
    ctx.fill();
    p.x+=p.dx; p.y+=p.dy; p.dy+=0.15; p.life--;
    if(p.life<=0) particles.splice(i,1);
  });
  requestAnimationFrame(draw);
}

setInterval(createFirework,500);
draw();

/* Memories */
let memIndex=0;
const memories=['photo1.jpg','photo2.jpg','photo3.jpg'];

const memContainer=document.getElementById('memContainer');

function showMemory(i){
  memContainer.innerHTML='';
  const img=document.createElement('img');
  img.src=memories[i];
  img.classList.add('memories-img');
  memContainer.appendChild(img);
}
showMemory(memIndex);

function nextMemory(){
  if(memIndex < memories.length-1){
    memIndex++;
    showMemory(memIndex);
  } else {
    showScreen('thanks');
  }
}

function prevMemory(){
  if(memIndex>0){
    memIndex--;
    showMemory(memIndex);
  }
}
</script>

</body>
</html>
