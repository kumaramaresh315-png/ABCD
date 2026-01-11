#<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday Navya ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins', sans-serif;
}
body{
    background:radial-gradient(circle, #1a1a2e, #000);
    color:white;
    overflow:hidden;
}
.slide{
    width:100%;
    height:100vh;
    display:none;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    text-align:center;
    padding:20px;
    animation:fade 1.2s;
}
.slide.active{
    display:flex;
}
h1{
    font-size:3rem;
    text-shadow:0 0 20px pink;
}
p{
    font-size:1.4rem;
    margin-top:20px;
    max-width:700px;
}
button{
    margin-top:30px;
    padding:12px 35px;
    border:none;
    border-radius:30px;
    background:#ff4d6d;
    color:white;
    font-size:1.1rem;
    cursor:pointer;
}
button:hover{
    background:#ff1c4b;
}
@keyframes fade{
    from{opacity:0; transform:scale(0.9);}
    to{opacity:1; transform:scale(1);}
}

/* Cake */
.cake{
    width:220px;
    height:150px;
    background:#ffb703;
    border-radius:12px;
    position:relative;
    margin-top:30px;
}
.layer{
    position:absolute;
    width:100%;
    height:40px;
    background:#fb8500;
    top:50px;
}
.candle{
    width:12px;
    height:45px;
    background:white;
    position:absolute;
    top:-45px;
    left:50%;
    transform:translateX(-50%);
}
.flame{
    width:18px;
    height:18px;
    background:orange;
    border-radius:50%;
    position:absolute;
    top:-18px;
    left:-3px;
    animation:flicker 0.2s infinite alternate;
}
@keyframes flicker{
    from{transform:scale(1);}
    to{transform:scale(1.2);}
}

/* Countdown */
#countdown{
    font-size:2rem;
    margin-top:25px;
    color:#ffd166;
}

/* Fireworks */
.firework{
    position:absolute;
    width:4px;
    height:4px;
    background:white;
    animation: explode 2s infinite;
}
@keyframes explode{
    from{transform:translateY(0); opacity:1;}
    to{transform:translateY(-250px); opacity:0;}
}
</style>
</head>

<body>

<!-- Background Music -->
<audio autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mp3">
</audio>

<!-- Slide 1 -->
<div class="slide active">
    <h1>🎉 Happy Birthday Navya 🎉</h1>
    <p>To the most beautiful girl in my world 💖</p>
    <button onclick="nextSlide()">Next ➜</button>
</div>

<!-- Slide 2 -->
<div class="slide">
    <h1>💝 Countdown Begins 💝</h1>
    <p>Waiting for your special day ✨</p>
    <div id="countdown"></div>
    <button onclick="nextSlide()">Next ➜</button>
</div>

<!-- Slide 3 -->
<div class="slide">
    <h1>🎂 Birthday Cake 🎂</h1>
    <div class="cake">
        <div class="layer"></div>
        <div class="candle">
            <div class="flame"></div>
        </div>
    </div>
    <p>Make a wish my love 💕</p>
    <button onclick="nextSlide()">Next ➜</button>
</div>

<!-- Slide 4 -->
<div class="slide">
    <h1>💌 From My Heart 💌</h1>
    <p>
        You make my life brighter 🌟<br>
        My days happier 😊<br>
        And my future beautiful 💞
    </p>
    <button onclick="nextSlide()">Next ➜</button>
</div>

<!-- Slide 5 -->
<div class="slide">
    <h1>🎆 I Love You Navya 🎆</h1>
    <p>Forever & Always ❤️</p>
</div>

<script>
let slides = document.querySelectorAll('.slide');
let index = 0;

function nextSlide(){
    slides[index].classList.remove('active');
    index++;
    if(index >= slides.length){
        index = slides.length - 1;
    }
    slides[index].classList.add('active');
}

/* Countdown */
const targetDate = new Date("January 14, 2026 00:00:00").getTime();
setInterval(()=>{
    let now = new Date().getTime();
    let distance = targetDate - now;

    let days = Math.floor(distance / (1000*60*60*24));
    let hours = Math.floor((distance % (1000*60*60*24))/(1000*60*60));
    let minutes = Math.floor((distance % (1000*60*60))/(1000*60));
    let seconds = Math.floor((distance % (1000*60))/1000);

    document.getElementById("countdown").innerHTML =
    `${days}d ${hours}h ${minutes}m ${seconds}s`;
},1000);

/* Fireworks */
for(let i=0;i<70;i++){
    let fw=document.createElement("div");
    fw.className="firework";
    fw.style.left=Math.random()*100+"%";
    fw.style.top=Math.random()*100+"%";
    fw.style.animationDelay=Math.random()*3+"s";
    document.body.appendChild(fw);
}
</script>

</body>
</html>
