<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI Nexus</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
<style>

:root{
  --bg:#05070d;
  --accent:#5ffbf1;
  --accent2:#8a7dff;
  --text:#e6f7ff;
}

*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

body{
  font-family:Inter, sans-serif;
  background:#000000;
  color:var(--text);
  overflow-x:hidden;
}

canvas{
  position:fixed;
  top:0;
  left:0;
  z-index:-1;
}

canvas{
  position:fixed;
  top:0;
  left:0;
  z-index:-1;
}

header{
  padding:40px 10%;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.logo{
  font-family:Orbitron;
  font-size:22px;
  letter-spacing:3px;
  color:var(--accent);
}

nav a{
  margin-left:30px;
  text-decoration:none;
  color:#b7c9ff;
  transition:.3s;
}

nav a:hover{
  color:var(--accent);
}

.hero{
  height:70vh;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
  padding:0 20px;
}

.hero h1{
  font-family:Orbitron;
  font-size:56px;
  letter-spacing:4px;
  background:linear-gradient(90deg,var(--accent),var(--accent2));
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}

.hero p{
  margin-top:20px;
  max-width:600px;
  line-height:1.7;
  color:#aab6ff;
}

.glow-btn{
  margin-top:35px;
  padding:14px 34px;
  border-radius:30px;
  border:1px solid var(--accent);
  background:transparent;
  color:var(--accent);
  font-size:16px;
  cursor:pointer;
  transition:.35s;
}

.glow-btn:hover{
  box-shadow:0 0 25px var(--accent);
  transform:translateY(-2px);
}

.section{
  padding:120px 10%;
}

.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(240px,1fr));
  gap:40px;
}

.card{
  padding:30px;
  border-radius:18px;
  background:rgba(255,255,255,0.03);
  backdrop-filter:blur(12px);
  border:1px solid rgba(255,255,255,0.05);
  transition:.4s;
}

.card:hover{
  transform:translateY(-6px);
  box-shadow:0 0 30px rgba(95,251,241,0.15);
}

.card h3{
  font-family:Orbitron;
  margin-bottom:12px;
  color:var(--accent);
}

footer{
  text-align:center;
  padding:60px 20px;
  font-size:14px;
  color:#6b7cff;
}

</style>
</head>
<body>

<canvas id="matrix"></canvas>

<header>
<div class="logo">AI NEXUS</div>
<nav>
<a href="#">Home</a>
<a href="#">Research</a>
<a href="#">Systems</a>
<a href="#">Contact</a>
</nav>
</header>

<section class="hero">
<h1>INTELLIGENCE
BEYOND HUMAN</h1>
<p>
A digital frontier exploring artificial cognition, machine creativity, and
synthetic intelligence. This node documents experiments, ideas, and
emerging architectures shaping the next epoch of intelligence.
</p>
<button class="glow-btn">Enter The Network</button>
</section>

<section class="section">
<div class="grid">

<div class="card">
<h3>Neural Systems</h3>
<p>Architectures exploring emergent intelligence, multi‑agent cognition, and self‑evolving models.</p>
</div>

<div class="card">
<h3>Machine Creativity</h3>
<p>Generative systems producing art, language, code, and new forms of digital expression.</p>
</div>

<div class="card">
<h3>Autonomous Agents</h3>
<p>Experiments with persistent AI entities capable of reasoning, planning, and discovery.</p>
</div>

<div class="card">
<h3>Future Research</h3>
<p>Exploring alignment, artificial consciousness, and the evolution of intelligence.</p>
</div>

</div>
</section>

<footer>
© 2026 AI Nexus — Synthetic Intelligence Interface
</footer>

<script>

const canvas = document.getElementById("matrix");
const ctx = canvas.getContext("2d");

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

const letters = "アァカサタナハマヤャラワ0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";
const fontSize = 16;
const columns = canvas.width / fontSize;

const drops = [];
for(let i = 0; i < columns; i++){
  drops[i] = Math.random()*canvas.height;
}

function draw(){
  ctx.fillStyle = "rgba(0,0,0,0.05)";
  ctx.fillRect(0,0,canvas.width,canvas.height);

  ctx.fillStyle = "#00ff41";
  ctx.font = fontSize + "px monospace";

  for(let i=0;i<drops.length;i++){
    const text = letters.charAt(Math.floor(Math.random()*letters.length));
    ctx.fillText(text, i*fontSize, drops[i]*fontSize);

    if(drops[i]*fontSize > canvas.height && Math.random() > 0.975){
      drops[i] = 0;
    }

    drops[i]++;
  }
}

setInterval(draw, 33);

window.addEventListener("resize",()=>{
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
});

</script>

</body>
</html>
