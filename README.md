<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Saturno de Amor</title>
<style>
body{
  margin:0;
  overflow:hidden;
  background: radial-gradient(circle at center, #0b0f2a, #000000);
  font-family: Arial, sans-serif;
}

/* Estrellas */
.star{
  position:absolute;
  width:2px;
  height:2px;
  background:white;
  animation: twinkle 2s infinite alternate;
}

@keyframes twinkle{
  from{opacity:0.2;}
  to{opacity:1;}
}

/* Saturno */
.saturn{
  position:absolute;
  top:50%;
  left:50%;
  transform:translate(-50%,-50%);
  width:200px;
  height:200px;
  background: radial-gradient(circle, #d9a066, #b86b3d);
  border-radius:50%;
  box-shadow:0 0 40px rgba(255,150,100,0.6);
}

/* Anillo de palabras */
.ring{
  position:absolute;
  top:50%;
  left:50%;
  transform:translate(-50%,-50%) rotateX(65deg);
  width:350px;
  height:350px;
  border-radius:50%;
  animation: rotateRing 20s linear infinite;
}

@keyframes rotateRing{
  from{transform:translate(-50%,-50%) rotateX(65deg) rotate(0deg);}
  to{transform:translate(-50%,-50%) rotateX(65deg) rotate(360deg);}
}

.love{
  position:absolute;
  color:#ff6ec7;
  font-size:14px;
  white-space:nowrap;
}

/* Corazones flotando */
.heart{
  position:absolute;
  color:#ff4da6;
  font-size:20px;
  animation: floatUp 6s linear infinite;
}

@keyframes floatUp{
  from{transform:translateY(100vh); opacity:1;}
  to{transform:translateY(-10vh); opacity:0;}
}
</style>
</head>
<body>

<div class="saturn"></div>
<div class="ring" id="ring"></div>

<script>

/* Crear estrellas */
for(let i=0;i<120;i++){
  let star=document.createElement("div");
  star.className="star";
  star.style.top=Math.random()*100+"vh";
  star.style.left=Math.random()*100+"vw";
  star.style.animationDuration=(Math.random()*3+1)+"s";
  document.body.appendChild(star);
}

/* Palabras de amor */
let words=["Te amo","Mi princesa","Mi luz","Mi sol","Mi niña","Te quiero mucho","Eres mi todo","Mi corazón","Mi vida","Mi universo"];
let ring=document.getElementById("ring");

for(let i=0;i<60;i++){
  let love=document.createElement("div");
  love.className="love";
  love.innerText=words[i%words.length];
  
  let angle=i*(360/60);
  let radius=150;
  
  love.style.top=50 + radius*Math.sin(angle*Math.PI/180)+"%";
  love.style.left=50 + radius*Math.cos(angle*Math.PI/180)+"%
