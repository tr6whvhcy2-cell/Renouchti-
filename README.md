<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Renouchti ❤️</title>

<style>
body{
margin:0;
font-family: Arial, sans-serif;
background: linear-gradient(135deg,#ff4d6d,#ff99ac);
color:white;
text-align:center;
overflow:hidden;
}

.section{
display:none;
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
padding:20px;
}

.active{
display:flex;
}

h1{
font-size:38px;
margin-bottom:10px;
}

button{
padding:12px 25px;
font-size:18px;
border:none;
border-radius:30px;
cursor:pointer;
margin-top:20px;
transition:0.3s;
}

.next{
background:white;
color:#ff4d6d;
}

.yes{
background:#00ff88;
color:black;
}

.no{
background:#ff3333;
color:white;
position:absolute;
}

#typed{
font-size:22px;
max-width:450px;
min-height:60px;
}

.counter{
font-size:20px;
margin-top:15px;
}

.stars{
position:fixed;
width:100%;
height:100%;
background:url('https://i.imgur.com/9a6KQpP.png');
animation: moveStars 60s linear infinite;
z-index:-1;
}

@keyframes moveStars{
from{background-position:0 0;}
to{background-position:10000px 5000px;}
}
</style>
</head>

<body>

<div class="stars"></div>

<!-- الصفحة 1 -->
<div class="section active" id="page1">
<h1>Renouchti ❤️</h1>
<p>رحلة بدات يوم 22 مارس 2022...</p>
<div class="counter" id="loveCounter"></div>
<button class="next" onclick="nextPage(2)">كمّلي</button>
</div>

<!-- الصفحة 2 -->
<div class="section" id="page2">
<h2 id="typed"></h2>
<button class="next" onclick="nextPage(3)">باقي حاجة</button>
</div>

<!-- الصفحة 3 -->
<div class="section" id="page3">
<h2>هل تقبلي تبقى معايا ديما؟ 💍</h2>
<button class="yes" onclick="yesAnswer()">نعم ❤️</button>
<button class="no" id="noBtn">لا 😅</button>
</div>

<script>
function nextPage(page){
document.querySelectorAll(".section").forEach(sec=>sec.classList.remove("active"));
document.getElementById("page"+page).classList.add("active");
}

let message = "من 22 مارس 2022 و حياتي تبدلت... وجودك نعمة، و كل يوم معاك يزيدني يقين بلي اخترت الصح ❤️";
let i = 0;
let speed = 50;

function typeWriter(){
if(i < message.length){
document.getElementById("typed").innerHTML += message.charAt(i);
i++;
setTimeout(typeWriter, speed);
}
}
typeWriter();

function yesAnswer(){
alert("هذا أجمل قرار ❤️");
}

let noBtn = document.getElementById("noBtn");
noBtn.addEventListener("mouseover", function(){
noBtn.style.top = Math.random()*80 + "%";
noBtn.style.left = Math.random()*80 + "%";
});

function updateCounter(){
let startDate = new Date("March 22, 2022 00:00:00").getTime();
let now = new Date().getTime();
let diff = now - startDate;

let days = Math.floor(diff / (1000*60*60*24));
let hours = Math.floor((diff % (1000*60*60*24)) / (1000*60*60));
let minutes = Math.floor((diff % (1000*60*60)) / (1000*60));
let seconds = Math.floor((diff % (1000*60)) / 1000);

document.getElementById("loveCounter").innerHTML =
"مرّ علينا: " + days + " يوم " +
hours + " ساعة " +
minutes + " دقيقة " +
seconds + " ثانية ❤️";
}

setInterval(updateCounter,1000);
</script>

</body>
</html>
