<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Merry Christmas Krity 🎄❤️</title>

<style>
body{
  margin:0;
  height:100vh;
  overflow:hidden;
  font-family:'Segoe UI',sans-serif;
  background:linear-gradient(180deg,#200000,#000);
  color:white;
  text-align:center;
}

/* TEXT */
h1{
  margin-top:40px;
  font-size:3.2rem;
  animation:glow 2s infinite alternate, drop 1.5s ease;
}
h2{opacity:0;animation:fade 2s forwards 1s;}
p{max-width:650px;margin:15px auto;font-size:1.1rem;opacity:0;animation:fade 2s forwards 2s;}

/* HEART */
.heart{
  font-size:90px;
  animation:beat 1.2s infinite;
  margin:20px;
}

/* BUTTON */
button{
  padding:14px 30px;
  border:none;
  border-radius:30px;
  background:crimson;
  color:white;
  font-size:1rem;
  cursor:pointer;
  box-shadow:0 0 20px red;
}
button:hover{transform:scale(1.1);}

/* SECRET MESSAGE */
#secret{
  display:none;
  font-size:1.3rem;
  color:#ffb6c1;
  margin-top:20px;
  animation:fade 1.5s forwards;
}

/* COUNTDOWN */
#countdown{
  font-size:1.2rem;
  margin-top:10px;
  color:#ffd700;
}

/* SNOW */
.snow{
  position:absolute;
  top:-10px;
  color:white;
  animation:fall linear infinite;
}

/* FLOATING HEARTS */
.fheart{
  position:absolute;
  bottom:-20px;
  color:pink;
  animation:floatUp linear infinite;
}

/* FIREWORK */
.firework{
  position:absolute;
  font-size:30px;
  animation:explode 1s forwards;
}

/* ANIMATIONS */
@keyframes glow{from{text-shadow:0 0 10px pink;}to{text-shadow:0 0 25px red;}}
@keyframes beat{0%,100%{transform:scale(1);}50%{transform:scale(1.25);}}
@keyframes fall{to{transform:translateY(110vh);}}
@keyframes floatUp{to{transform:translateY(-120vh);opacity:0;}}
@keyframes fade{to{opacity:1;}}
@keyframes drop{from{transform:translateY(-50px);}to{transform:translateY(0);}}
@keyframes explode{to{transform:scale(3);opacity:0;}}
</style>
</head>

<body>

<h1>🎄 Merry Christmas Krity ❤️</h1>
<h2>My kucchuuu puchuuu 😘</h2>

<p>
You are damn beautiful — more than fairy lights, more than stars.
Christmas feels unreal because I get to love you.
</p>

<div class="heart">❤️</div>

<button onclick="surprise()">Tap for Surprise 🎁</button>

<div id="secret">
I don’t just wish you Merry Christmas…  
I wish us forever 🎄💖
</div>

<div id="countdown"></div>

<audio id="music" loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3">
</audio>

<script>
// Snow
setInterval(()=>{
  let s=document.createElement("div");
  s.className="snow";
  s.innerHTML="❄";
  s.style.left=Math.random()*innerWidth+"px";
  s.style.fontSize=(10+Math.random()*10)+"px";
  s.style.animationDuration=(2+Math.random()*3)+"s";
  document.body.appendChild(s);
  setTimeout(()=>s.remove(),5000);
},200);

// Floating hearts
setInterval(()=>{
  let h=document.createElement("div");
  h.className="fheart";
  h.innerHTML="❤️";
  h.style.left=Math.random()*innerWidth+"px";
  h.style.animationDuration=(3+Math.random()*3)+"s";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),6000);
},500);

// Surprise
function surprise(){
  document.getElementById("secret").style.display="block";
  document.getElementById("music").play();

  for(let i=0;i<10;i++){
    let f=document.createElement("div");
    f.className="firework";
    f.innerHTML="✨";
    f.style.left=Math.random()*innerWidth+"px";
    f.style.top=Math.random()*innerHeight+"px";
    document.body.appendChild(f);
    setTimeout(()=>f.remove(),1000);
  }
}

// Countdown
const target=new Date("Dec 25, 2025 00:00:00").getTime();
setInterval(()=>{
  let now=new Date().getTime();
  let diff=target-now;
  if(diff>0){
    let d=Math.floor(diff/(1000*60*60*24));
    let h=Math.floor((diff%(1000*60*60*24))/(1000*60*60));
    document.getElementById("countdown").innerHTML=
    "🎅 Christmas Countdown: "+d+" days "+h+" hours";
  }
},1000);
</script>

</body>
</html>
