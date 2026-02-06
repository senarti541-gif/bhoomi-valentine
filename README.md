<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>BHOOMI ❤️ VALENTINE</title>

<style>
*{box-sizing:border-box}
body{
margin:0;
font-family:Arial, sans-serif;
background:linear-gradient(135deg,#ff9a9e,#fad0c4);
height:100vh;
display:flex;
justify-content:center;
align-items:center;
overflow:hidden;
text-align:center;
}

.box{
background:white;
padding:25px;
border-radius:20px;
width:330px;
box-shadow:0 15px 30px rgba(0,0,0,.25);
}

.hidden{display:none}

button{
padding:12px 20px;
margin:10px;
border:none;
border-radius:12px;
font-size:16px;
font-weight:bold;
cursor:pointer;
}

.yes{background:#ff4d6d;color:white}
.no{background:#ccc}

.card{
background:#ffe6ea;
margin:10px 0;
padding:12px;
border-radius:12px;
font-weight:bold;
cursor:pointer;
}

img{
width:130px;
border-radius:15px;
margin:10px;
}

.heart{
position:absolute;
bottom:-20px;
font-size:20px;
animation:floatUp 6s linear infinite;
}

@keyframes floatUp{
0%{transform:translateY(0);opacity:1}
100%{transform:translateY(-120vh);opacity:0}
}
</style>
</head>

<body>

<!-- STEP 0 -->
<div class="box" id="step0">
<h2><b>TAP TO START 💖</b></h2>
<button class="yes" onclick="start()">START ❤️</button>
</div>

<!-- STEP 1 -->
<div class="box hidden" id="step1">
<h2><b>BHOOMI, WILL YOU BE MY VALENTINE?</b></h2>
<button id="yesBtn" class="yes" onclick="nextStep(2)">YES ❤️</button>
<button class="no" onclick="noClick()">NO 😜</button>
<p id="funny"></p>
</div>

<!-- STEP 2 -->
<div class="box hidden" id="step2">
<h2><b>SURPRISE GIFT 🎁</b></h2>
<div class="card" onclick="openGift()">CLICK TO OPEN 🎁</div>

<div id="giftBox" class="hidden">
<div class="card">🌹 ROSE</div>
<div class="card">🍫 CHOCOLATE</div>
<div class="card">🧸 TEDDY</div>
<img src="us.jpg">
<p><b>ALL THESE GIFTS ARE ONLY FOR YOU, BHOOMI ❤️</b></p>
</div>

<button class="yes" onclick="nextStep(3)">NEXT ❤️</button>
</div>

<!-- STEP 3 -->
<div class="box hidden" id="step3">
<h2><b>WHAT DO YOU WANT TO DO WITH ME THIS VALENTINE’S DAY?</b></h2>
<div class="card">ROMANTIC DINNER 🍽️</div>
<div class="card">MOVIE DATE 🎬</div>
<div class="card">LONG DRIVE 🚗</div>
<div class="card">COFFEE & TALKS ☕</div>
<div class="card">JUST YOU & ME ❤️</div>
<button class="yes" onclick="nextStep(4)">NEXT 💕</button>
</div>

<!-- STEP 4 -->
<div class="box hidden" id="step4">
<h2><b>FOR YOU, BHOOMI 💌</b></h2>
<p><b>
BHOOMI, YOU ARE NOT JUST MY VALENTINE,<br>
YOU ARE MY COMFORT, MY SMILE, MY PEACE.<br>
EVERY DAY WITH YOU FEELS LIKE A CELEBRATION.<br>
I DON’T WANT JUST A DAY, I WANT A LIFETIME WITH YOU ❤️
</b></p>
<button class="yes" onclick="nextStep(5)">LAST SURPRISE 😘</button>
</div>

<!-- STEP 5 -->
<div class="box hidden" id="step5">
<h2><b>FROM US — TO FOREVER 💑</b></h2>
<img src="us.jpg">
</div>

<audio id="music" loop>
<source src="perfect.mp3" type="audio/mpeg">
</audio>

<script>
let msgs=[
"ARE YOU SURE? MY HEART IS CRACKING 😜",
"WARNING: NO BUTTON IS DANGEROUS 💔",
"YES IS LOOKING CUTER EVERY CLICK 😌",
"DON’T BE SO STRONG, JUST TAP YES 🥺",
"SYSTEM ERROR: ONLY YES ACCEPTED ❤️"
];

let yesSize=16;

function noClick(){
document.getElementById("funny").innerText=
msgs[Math.floor(Math.random()*msgs.length)];
yesSize+=4;
document.getElementById("yesBtn").style.fontSize=yesSize+"px";
}

function nextStep(n){
for(let i=0;i<=5;i++){
let el=document.getElementById("step"+i);
if(el)el.classList.add("hidden");
}
document.getElementById("step"+n).classList.remove("hidden");
}

function start(){
document.getElementById("music").play();
nextStep(1);
setInterval(()=>{
let h=document.createElement("div");
h.className="heart";
h.innerHTML="❤️";
h.style.left=Math.random()*100+"vw";
h.style.fontSize=20+Math.random()*20+"px";
document.body.appendChild(h);
setTimeout(()=>h.remove(),6000);
},400);
}

function openGift(){
document.getElementById("giftBox").classList.remove("hidden");
}
</script>

</body>
</html>
