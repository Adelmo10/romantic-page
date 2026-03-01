<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Happy 1st Month, Reann</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:wght@400;600;700&display=swap" rel="stylesheet" />
<style>
:root {
  --bg-1:#07040c; --bg-2:#14091f; --bg-3:#261137;
  --text:#f8f1ff; --soft:#e9d3ff; --accent:#ffc9ea;
  --glass:rgba(41,16,59,0.7); --glow:rgba(255,188,228,0.5);
}

* {box-sizing:border-box;margin:0;padding:0;}
html, body {width:100%; min-height:100%;}
body {
  font-family:"Playfair Display", serif; color:var(--text);
  background:
    radial-gradient(circle at 15% 20%, rgba(141,74,188,0.2), transparent 34%),
    radial-gradient(circle at 80% 85%, rgba(246,143,206,0.13), transparent 36%),
    linear-gradient(130deg, var(--bg-1), var(--bg-2), var(--bg-3));
  overflow:hidden; position:relative;
}

.bg-stars,.bg-hearts {position:fixed; inset:0; pointer-events:none;}
.bg-stars {z-index:0; overflow:hidden;}
.star {
  position:absolute; width:2px; height:2px; border-radius:50%;
  background:rgba(255,255,255,0.92);
  box-shadow:0 0 8px rgba(255,255,255,0.75); opacity:0.35;
  animation:twinkle ease-in-out infinite;
}
@keyframes twinkle {
  0%,100%{opacity:0.18; transform:scale(0.85);}
  50%{opacity:1; transform:scale(1.45);}
}

.youtube-bg {
  position:fixed; width:2px; height:2px; opacity:0;
  pointer-events:none; left:-9999px; top:-9999px;
}

.mute-btn {
  position:fixed; top:14px; right:14px; z-index:12;
  border:1px solid rgba(255,209,239,0.58);
  background:linear-gradient(120deg, rgba(255,140,210,0.22), rgba(171,111,255,0.18));
  color:#fff; border-radius:999px; padding:9px 14px;
  font-size:0.8rem; letter-spacing:0.03em; cursor:pointer;
  backdrop-filter:blur(4px); box-shadow:0 0 16px rgba(255,176,227,0.32);
  transition:transform 0.25s ease, box-shadow 0.25s ease; font-family:inherit;
}
.mute-btn:hover {transform:translateY(-1px); box-shadow:0 0 24px rgba(255,176,227,0.45);}

.screen {position:relative; z-index:2; min-height:100svh; width:100%; display:grid; place-items:center; padding:70px 18px 58px;}
.center-wrap {width:min(920px,96vw); text-align:center; animation:fadeUp 1.2s ease both;}
.title {font-size:clamp(2.1rem,6.1vw,4.25rem); line-height:1.14; text-shadow:0 0 18px rgba(255,190,232,0.36); animation:glowPulse 4.2s ease-in-out infinite; margin-bottom:26px;}
.typed {width:min(710px,100%); margin:0 auto; white-space:pre-line; font-size:clamp(1rem,2.55vw,1.3rem); line-height:1.85; min-height:270px; color:#fef9ff; text-shadow:0 0 10px rgba(255,209,240,0.16); opacity:0; animation:fadeIn 1.1s ease 0.45s forwards;}
.typed.cursor::after {content:"|"; margin-left:4px; color:var(--soft); animation:blink 1s steps(1) infinite;}

.cta {margin-top:16px; opacity:0; transform:translateY(10px); animation:fadeUp 1s ease 1.5s forwards;}

.heart-btn {
  border:1px solid rgba(255,213,241,0.62); border-radius:999px;
  padding:14px 30px; background:linear-gradient(120deg, rgba(255,145,210,0.24), rgba(176,111,255,0.2));
  color:#fff; font-family:inherit; font-size:1rem; letter-spacing:0.04em; cursor:pointer;
  box-shadow:0 0 18px rgba(255,173,225,0.35), inset 0 0 20px rgba(255,216,243,0.14);
  transition: transform 0.28s ease, box-shadow 0.28s ease;
  animation: pulseBtn 2.2s ease-in-out infinite;
}
.heart-btn:hover {transform:translateY(-2px) scale(1.06); box-shadow:0 0 32px rgba(255,182,229,0.7), inset 0 0 24px rgba(255,216,243,0.2);}
@keyframes pulseBtn {0%,100%{transform:scale(1); box-shadow:0 0 18px rgba(255,173,225,0.35), inset 0 0 20px rgba(255,216,243,0.14);}50%{transform:scale(1.08); box-shadow:0 0 28px rgba(255,182,229,0.55), inset 0 0 22px rgba(255,216,243,0.18);}}

.song-line {position:fixed; bottom:14px; left:50%; transform:translateX(-50%); z-index:4; color:rgba(250,236,255,0.78); font-size:0.9rem; letter-spacing:0.03em; text-align:center; width:calc(100%-30px); text-shadow:0 0 10px rgba(255,208,241,0.22); animation:fadeIn 1.5s ease 1.1s both;}

.overlay {position:fixed; inset:0; z-index:8; display:grid; place-items:center; padding:20px; background:rgba(5,3,8,0.14); opacity:0; visibility:hidden; transition:opacity 0.65s ease, background 0.65s ease, visibility 0.65s ease;}
.overlay.show {opacity:1; visibility:visible; background:rgba(5,3,8,0.82);}
.final-box {width:min(670px,94vw); background:linear-gradient(130deg, rgba(32,12,48,0.82), var(--glass)); border:1px solid rgba(255,211,239,0.38); border-radius:24px; padding:clamp(24px,5vw,40px); text-align:center; backdrop-filter:blur(6px); box-shadow:0 0 40px rgba(255,180,227,0.28), inset 0 0 22px rgba(255,215,241,0.1); transform:translateY(16px) scale(0.97); opacity:0; transition: transform 0.55s ease, opacity 0.55s ease;}
.overlay.show .final-box {transform:translateY(0) scale(1); opacity:1;}
.final-msg {font-family:"Great Vibes", cursive; font-size:clamp(1.85rem,5.7vw,3.1rem); line-height:1.33; white-space:pre-line; color:#ffe9f9; text-shadow:0 0 18px rgba(255,189,230,0.58);}
.bg-hearts {z-index:9; overflow:hidden;}
.heart {position:absolute; bottom:-36px; font-size:clamp(16px,2.35vw,27px); color:rgba(255,183,225,0.9); text-shadow:0 0 10px rgba(255,197,233,0.82); opacity:0; animation:rise linear forwards;}
@keyframes rise {0%{transform:translateY(0) scale(0.82) rotate(0deg); opacity:0;}14%{opacity:0.95;}100%{transform:translateY(-112vh) scale(1.34) rotate(18deg); opacity:0;}}

@keyframes blink {50%{opacity:0;}}
@keyframes fadeIn {from{opacity:0;}to{opacity:1;}}
@keyframes fadeUp {from{opacity:0; transform:translateY(15px);} to{opacity:1; transform:translateY(0);}}
@keyframes glowPulse {0%,100%{text-shadow:0 0 16px rgba(255,186,230,0.28);}50%{text-shadow:0 0 34px rgba(255,189,231,0.58);}}

@media(max-width:640px){
  body{overflow-y:auto;}
  .screen{padding:84px 14px 66px;}
  .typed{min-height:315px; line-height:1.8;}
  .heart-btn{padding:13px 24px;}
  .mute-btn{top:10px; right:10px; padding:8px 12px; font-size:0.76rem;}
  .song-line{font-size:0.82rem;}
}
</style>
</head>
<body>
<iframe id="ytPlayer" class="youtube-bg"
src="https://www.youtube.com/embed/sCBIUH2_Jrw?autoplay=1&mute=1&loop=1&playlist=sCBIUH2_Jrw&controls=0&disablekb=1&fs=0&iv_load_policy=3&modestbranding=1&rel=0&playsinline=1&enablejsapi=1"
title="Background music" allow="autoplay; encrypted-media" referrerpolicy="strict-origin-when-cross-origin"></iframe>

<div class="bg-stars" id="stars"></div>
<div class="bg-hearts" id="hearts"></div>
<button id="muteBtn" class="mute-btn" aria-label="Toggle music">Unmute</button>

<main class="screen">
<section class="center-wrap">
<h1 class="title">Happy 1st Month, Reann ❤️</h1>
<p id="typedMessage" class="typed cursor"></p>
<div class="cta">
<button id="openHeart" class="heart-btn">Open My Heart 🤍</button>
</div>
</section>
</main>
<p class="song-line">Playing: I Know - TJ Monterde ♫</p>

<section id="overlay" class="overlay" aria-hidden="true">
<div class="final-box">
<p class="final-msg">I don't know what the future holds...
but I know I want you in it.
Not just for today.
Not just for a while.
But for all my tomorrows, Reann.</p>
</div>
</section>

<script>
// نجوم
const starsWrap=document.getElementById("stars");const starCount=150;
for(let i=0;i<starCount;i++){const s=document.createElement("span");s.className="star";s.style.left=`${Math.random()*100}%`;s.style.top=`${Math.random()*100}%`;s.style.animationDuration=`${2.8+Math.random()*3.3}s`;s.style.animationDelay=`${Math.random()*4}s`;s.style.transform=`scale(${0.6+Math.random()*1.25})`;starsWrap.appendChild(s);}

// كتابة الرسالة
const typingText=`Reann,
From the moment you came into my life,
everything started to feel right.
This month with you has meant more to me
than words can ever explain.

You are my calm,
my favorite notification,
and my heart's safest place.`;
const typedMessage=document.getElementById("typedMessage");
let pointer=0;
function runTyping(){if(pointer<=typingText.length){typedMessage.textContent=typingText.slice(0,pointer);const current=typingText[pointer];pointer+=1;const delay=current=="\n"?240:38;setTimeout(runTyping,delay);}else{typedMessage.classList.remove("cursor");}}
setTimeout(runTyping,820);

// قلوب
const overlay=document.getElementById("overlay");
const openHeartBtn=document.getElementById("openHeart");
const heartsLayer=document.getElementById("hearts");
let heartsTimer=null;
function spawnHeart(){const h=document.createElement("span");h.className="heart";h.textContent=Math.random()>0.5?"❤":"♡";h.style.left=`${Math.random()*100}vw`;h.style.animationDuration=`${4.2+Math.random()*3.4}s`;heartsLayer.appendChild(h);setTimeout(()=>h.remove(),8000);}
openHeartBtn.addEventListener("click",()=>{overlay.classList.add("show");overlay.setAttribute("aria-hidden","false");if(!heartsTimer){for(let i=0;i<14;i++){setTimeout(spawnHeart,i*130);}heartsTimer=setInterval(spawnHeart,260);}});
overlay.addEventListener("click",(event)=>{if(event.target===overlay){overlay.classList.remove("show");overlay.setAttribute("aria-hidden","true");clearInterval(heartsTimer);heartsTimer=null;}});

// يوتيوب
const ytPlayer=document.getElementById("ytPlayer");
const muteBtn=document.getElementById("muteBtn");
let userInteracted=false;let musicMuted=true;
function sendYT(command,args=[]){if(!ytPlayer||!ytPlayer.contentWindow)return;ytPlayer.contentWindow.postMessage(JSON.stringify({event:"command",func:command,args}),"*");}
async function applyPlaybackState(){sendYT("setVolume",[18]); if(musicMuted){sendYT("mute");}else{sendYT("unMute");} sendYT("playVideo");}
setTimeout(applyPlaybackState,900); setTimeout(applyPlaybackState,2200);
async function activateOnFirstInteraction(){if(userInteracted)return; userInteracted=true; musicMuted=false; muteBtn.textContent="Mute"; applyPlaybackState();}
["click","touchstart","keydown"].forEach(evt=>{document.addEventListener(evt,activateOnFirstInteraction,{once:true,passive:true});});
muteBtn.addEventListener("click",()=>{musicMuted=!musicMuted; muteBtn.textContent=musicMuted?"Unmute":"Mute"; applyPlaybackState();});
</script>
</body>
</html>
