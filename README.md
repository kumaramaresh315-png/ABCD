<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday Navya 🎉</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Segoe UI', sans-serif;
}
body{
    overflow:hidden;
    background:black;
    color:white;
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
}
.slide.active{
    display:flex;
}
h1{
    font-size:3rem;
    animation: glow 2s infinite alternate;
}
p{
    font-size:1.5rem;
    margin-top:20px;
}
button{
    margin-top:30px;
    padding:12px 30px;
    font-size:1.1rem;
    border:none;
    border-radius:30px;
    background:#ff4d6d;
    color:white;
    cursor:pointer;
}
button:hover{
    background:#ff1c4b;
}

@keyframes glow{
    from{ text-shadow:0 0 10px pink; }
    to{ text-shadow:0 0 30px hotpink; }
}

/* Cake */
.cake{
    width:200px;
    height:150px;
    background:#ffb703;
    border-radius:10px;
    position:relative;
    margin-top:30px;
}
.cake:before{
    content:'';
    position:absolute;
    width:100%;
    height:40px;
    background:#fb8500;
    top:50px;
}
.candle{
    width:10px;
    height:40px;
    background:white;
    position:absolute;
    top:-40px;
    left:50%;
    transform:translateX(-50%);
}
.flame{
    width:15px;
    height:15px;
    background:orange;
    border-radius:50%;
    position:absolute;
    top:-15px;
    left:-2px;
    animation:flicker 0.2s infinite alternate;
}
@keyframes flicker{
    from{transform:scale(1);}
    to{transform:scale(1.2);}
}

/* Fireworks */
.firework{
    position:absolute;
    width:5px;
    height:5px;
    background:white;
    animation: explode 1.5s infinite;
}
@keyframes explode{
    from{transform:translateY(0); opacity:1;}
    to{transform:translateY(-200px); opacity:0;}
}
</style>
</head>

<body>

<!-- Slide 1 -->
<div class="slide active">
    <h1>🎉 Happy Birthday Navya 🎉</h1>
    <p>My love, my happiness, my everything 💖</p>
    <button onclick="nextSlide()">Next ➜</button>
</div>

<!-- Slide 2 -->
<div class="slide">
    <h1>💖 15th Birthday 💖</h1>
    <p>14 January — The day my world became more beautiful ✨</p>
    <button onclick="nextSlide()">Next ➜</button>
</div>

<!-- Slide 3 -->
<div class="slide">
    <h1>🎂 Birthday Cake 🎂</h1>
    <div class="cake">
        <div class="candle">
            <div class="flame"></div>
        </div>
    </div>
    <p>Make a wish, my love 💕</p>
    <button onclick="nextSlide()">Next ➜</button>
</div>

<!-- Slide 4 -->
<div class="slide">
    <h1>💌 Special Message 💌</h1>
    <p>
        You are the reason behind my smile 😊<br>
        My strongest support 💪<br>
        And my forever love 💞
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

// Fireworks effect
for(let i=0;i<50;i++){
    let fw = document.createElement('div');
    fw.className='firework';
    fw.style.left=Math.random()*100+'%';
    fw.style.top=Math.random()*100+'%';
    fw.style.animationDelay=Math.random()*2+'s';
    document.body.appendChild(fw);
}
</script>

</body>
</html>
