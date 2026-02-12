<!DOCTYPE html>

<html>

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>For Janika ❤️</title>



<style>

body{

margin:0;

font-family:'Comic Sans MS', cursive;

overflow:hidden;

background:linear-gradient(-45deg,#ff4e50,#ff6a88,#ff9a9e,#fbc2eb);

background-size:400% 400%;

animation:gradient 12s ease infinite;

color:white;

}



@keyframes gradient{

0%{background-position:0% 50%}

50%{background-position:100% 50%}

100%{background-position:0% 50%}

}



.page{

display:none;

height:100vh;

width:100vw;

justify-content:center;

align-items:center;

flex-direction:column;

text-align:center;

padding:30px;

position:relative;

}



.active{display:flex;}



button{

padding:12px 25px;

font-size:16px;

border:none;

border-radius:30px;

cursor:pointer;

margin:10px;

transition:0.3s;

}



button:hover{transform:scale(1.1);}



\#yesBtn{background:#ff4e50;color:white;}



\#noBtn{

background:black;

color:white;

position:absolute;

transition:all 0.3s ease;

}



.card{

background:rgba(0,0,0,0.85);

padding:40px;

border-radius:20px;

max-width:850px;

height:80vh;

overflow:auto;

box-shadow:0 0 40px rgba(0,0,0,0.6);

line-height:1.7;

font-size:17px;

text-align:left;

}



\#loveMeterContainer{

position:fixed;

top:15px;

left:50%;

transform:translateX(-50%);

width:60%;

height:20px;

background:rgba(255,255,255,0.4);

border-radius:20px;

overflow:hidden;

display:none;

z-index:1000;

}



\#loveMeter{

height:100%;

width:0%;

background:#ff4e50;

transition:width 0.1s;

}



.heartTrail{

position:fixed;

pointer-events:none;

font-size:14px;

animation:fade 1s forwards;

}



@keyframes fade{

to{opacity:0; transform:translateY(-15px);}

}



.overlay{

position:fixed;

top:0;

left:0;

width:100%;

height:100%;

background:black;

display:flex;

justify-content:center;

align-items:center;

font-size:32px;

z-index:999;

flex-direction:column;

text-align:center;

}



.confetti{

position:fixed;

width:8px;

height:8px;

pointer-events:none;

animation:fall 3s linear forwards;

}



@keyframes fall{

to{transform:translateY(100vh) rotate(720deg);opacity:0;}

}



input\[type=range]{

width:100%;

}

</style>

</head>

<body>



<div id="loveMeterContainer">

<div id="loveMeter"></div>

</div>



<!-- PAGE 1 -->

<div class="page active" id="page1">

<h2>Psstt... There is something I wanted to talk to you about</h2>

<button onclick="go(2)">Click here to know</button>

</div>



<!-- PAGE 2 -->

<div class="page" id="page2">

<h2>Mini Game 1 😈</h2>

<p>Click the button 3 times to continue.</p>

<button id="tapBtn">Tap Me</button>

</div>



<!-- PAGE 3 -->

<div class="page" id="page3">

<h2>Mini Game 2 👀</h2>

<p>Catch the button if you can.</p>

<button id="runBtn">Catch Me</button>

</div>



<!-- PAGE 4 -->

<div class="page" id="page4">

<h2>Still here? 😏</h2>

<p>You are fighting through levels just for me... interesting.</p>

<button onclick="go(5)">Fine. Continue.</button>

</div>



<!-- PAGE 5 -->

<div class="page" id="page5">

<div class="card">

<p>

I am aware that this is your first relationship and you have every right to expect and demand everything...

<br><br>

Not polite.<br>

Not patient.<br>

Not tame.<br>

Not predictable.<br><br>

I want pulse.<br>

I want hunger.<br>

I want electric.<br><br>

I want you in all the ways heaven was too sacred, too powerful, too dangerous to ever teach humanity how to handle.

</p>

<button onclick="go(7)">Continue</button>

</div>

</div>



<!-- PAGE 7 SLIDER GAME -->

<div class="page" id="page7">

<h2>Prove It 😌</h2>

<p>Slide until it’s undeniable.</p>



<div style="width:70%;max-width:500px;">

<input type="range" id="loveSlider" min="0" max="100" value="0">

</div>



<p id="sliderValue">0%</p>

<div id="sliderMessage" style="margin-top:20px;font-size:22px;"></div>

</div>



<!-- PAGE 6 -->

<div class="page" id="page6">

<h1>Janika, will you be my Valentine?</h1>

<button id="yesBtn">YES ❤️</button>

<button id="noBtn">No</button>

</div>



<script>



function go(num){

document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));

document.getElementById("page"+num).classList.add('active');



if(num===2) setupGame1();

if(num===3) setupGame2();

if(num===7) setupSliderGame();

if(num===6) setupFinal();

}



/\* GAME 1 \*/

function setupGame1(){

let count=0;

const btn=document.getElementById("tapBtn");

btn.onclick=function(){

count++;

btn.innerText="Again ("+count+")";

if(count>=3) go(3);

};

}



/\* GAME 2 \*/

function setupGame2(){

let escapes=0;

const btn=document.getElementById("runBtn");

btn.onmouseover=function(){

if(escapes<5){

btn.style.position="absolute";

btn.style.left=Math.random()\*80+"%";

btn.style.top=Math.random()\*80+"%";

escapes++;

}

};

btn.onclick=function(){go(4);}

}



/\* SLIDER GAME \*/

function setupSliderGame(){

const slider=document.getElementById("loveSlider");

const valueText=document.getElementById("sliderValue");

const message=document.getElementById("sliderMessage");



slider.oninput=function(){

valueText.innerText=slider.value+"%";



if(slider.value<30) message.innerText="Hmm. Weak energy.";

else if(slider.value<60) message.innerText="Okay okay… I see effort.";

else if(slider.value<90) message.innerText="Oh? You’re serious serious.";

else if(slider.value<100) message.innerText="Careful… you're almost exposing yourself.";

else message.innerHTML="Okay fine, it’s obvious you love me ❤️<br><br><button onclick='go(6)'>Now go ask properly 😌</button>";

};

}



/\* FINAL PAGE \*/

function setupFinal(){



document.getElementById("loveMeterContainer").style.display="block";



let love=0;

let loveTriggered=false;



const noMessages=\[

"That’s a bold move for someone this cute.",

"You sure? The Yes button is feeling ignored.",

"Babbu, Sochle ek bar aur",

"Hein?",

"Are you testing my coding skills right now?",

"Oye, Janika I built a WEBSITE for this.",

"Okay fine… but the Yes button is hotter.",

"This is character development I didn’t ask for.",

"So you wana fight HUH?",

"Are you fr fr bb."

];



let noIndex=0;



document.addEventListener("mousemove",function(e){



if(love<100){

love+=0.15;

document.getElementById("loveMeter").style.width=love+"%";

}



if(love>=100 \&\& !loveTriggered){

loveTriggered=true;

let overlay=document.createElement("div");

overlay.className="overlay";

overlay.innerHTML="Okay fine, it’s obvious that you love me ❤️<br><br><button onclick='this.parentElement.remove()'>Continue</button>";

document.body.appendChild(overlay);

}



let heart=document.createElement("div");

heart.className="heartTrail";

heart.innerHTML="❤️";

heart.style.left=e.pageX+"px";

heart.style.top=e.pageY+"px";

document.body.appendChild(heart);

setTimeout(()=>heart.remove(),800);



});



const noBtn=document.getElementById("noBtn");

noBtn.onmousemove=function(){

noBtn.style.left=Math.random()\*80+"%";

noBtn.style.top=Math.random()\*80+"%";

noBtn.innerText=noMessages\[noIndex];

noIndex=(noIndex+1)%noMessages.length;

};



document.getElementById("yesBtn").onclick=function(){

let overlay=document.createElement("div");

overlay.className="overlay";

overlay.innerHTML="Ruko Zara Sabar Kro...";

document.body.appendChild(overlay);



setTimeout(()=>{

explode();

overlay.innerHTML="JANIKA ❤️<br>You are officially Raman's Valentine.<br>There was never another option 😌";

},3000);

};

}



function explode(){

for(let i=0;i<200;i++){

let c=document.createElement("div");

c.className="confetti";

c.style.left=Math.random()\*window.innerWidth+"px";

c.style.backgroundColor=\["#fff","#ff4e50","#ffd1dc"]\[Math.floor(Math.random()\*3)];

document.body.appendChild(c);

setTimeout(()=>c.remove(),3000);

}

}



</script>



</body>

</html>



