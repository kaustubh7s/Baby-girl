<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>I'm Sorry 💌</title>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;800&family=Pacifico&display=swap" rel="stylesheet">
<style>
  :root{
    --bg1:#ffe6ef;
    --bg2:#ffd6f6;
    --card:#ffffff;
    --pink:#ff6fa1;
    --hot:#ff3b7d;
    --shadow:0 20px 60px rgba(255,59,125,.25);
  }
  *{box-sizing:border-box}
  body{
    margin:0;
    min-height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    background: radial-gradient(1200px 900px at 20% -10%, var(--bg2), transparent),
                radial-gradient(1200px 900px at 120% 110%, #ffd9e3, transparent),
                linear-gradient(180deg,var(--bg1),#fff0f6 60%);
    font-family: Poppins, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial, "Noto Color Emoji", "Apple Color Emoji", sans-serif;
    overflow:hidden;
  }

  .scene{
    position:relative;
    width:min(92vw,780px);
    height:min(92vh,640px);
    display:flex;
    align-items:center;
    justify-content:center;
  }

  .sticker{
    position:absolute;
    width:min(35vw,180px);
    user-select:none;
    filter: drop-shadow(0 8px 20px rgba(0,0,0,.12));
    animation: bob 3.2s ease-in-out infinite;
    z-index:2;
  }
  .sticker.left{ left:-6%; bottom:6%; transform:rotate(-10deg); animation-delay:.2s }
  .sticker.right{ right:-4%; top:4%; transform:rotate(8deg); animation-delay:1s }
  @keyframes bob{
    0%,100%{ transform:translateY(0) rotate(var(--rot,0deg)); }
    50%{ transform:translateY(-10px) rotate(calc(var(--rot,0deg) + .5deg)); }
  }

  .card{
    position:relative;
    width:min(88vw,560px);
    aspect-ratio:4/3;
    background:var(--card);
    border-radius:28px;
    box-shadow: var(--shadow);
    display:flex;
    align-items:center;
    justify-content:center;
    padding:28px;
  }

  .envelope-wrap{
    position:relative;
    width:90%;
    max-width:520px;
    aspect-ratio:5/3.5;
    cursor:pointer;
    perspective:1200px;
  }
  .hint{
    position:absolute;
    top:-18px; left:0; right:0;
    text-align:center;
    font-size:14px;
    color:#c43b6c;
    opacity:.9;
    letter-spacing:.3px;
  }

  .envelope{
    position:relative;
    width:100%; height:100%;
    border-radius:18px;
    filter: drop-shadow(0 14px 30px rgba(255,59,125,.25));
  }
  svg{ width:100%; height:100%; display:block }

  .letter{
    position:absolute;
    left:8%;
    right:8%;
    bottom:8%;
    height:78%;
    background:#fff;
    border-radius:16px;
    box-shadow:0 12px 30px rgba(0,0,0,.12);
    transform: translateY(26%) scale(.98);
    opacity:0;
    transition: transform .9s cubic-bezier(.2,.8,.2,1), opacity .6s ease;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:22px 18px;
  }

  .note{
    text-align:center;
    line-height:1.35;
    max-width:90%;
  }
  .note h1{
    font-family: Pacifico, cursive;
    font-weight:400;
    font-size: clamp(26px, 5vw, 40px);
    margin: 2px 0 8px;
    color:#ff2c74;
    letter-spacing:.3px;
  }
  .note p{
    font-size: clamp(16px, 3.2vw, 20px);
    margin:0;
  }
  .signature{
    margin-top:10px;
    font-weight:600;
    color:#c43b6c;
    font-size: clamp(13px, 2.5vw, 16px);
  }

  .open .flap{
    transform: rotateX(178deg);
    transform-origin: 50% 0%;
    transition: transform .9s cubic-bezier(.16,.8,.16,1);
  }
  .open .letter{
    transform: translateY(-10%) scale(1);
    opacity:1;
    transition-delay:.15s;
  }

  .hearts{
    position:absolute;
    inset:0;
    pointer-events:none;
    overflow:hidden;
  }
  .heart{
    position:absolute;
    font-size: 18px;
    animation: floatUp 3.2s ease-in forwards;
    filter: drop-shadow(0 6px 10px rgba(255,59,125,.25));
  }
  @keyframes floatUp{
    0%   { transform: translateY(20px) scale(.8); opacity:0 }
    10%  { opacity:1 }
    100% { transform: translateY(-110vh) scale(1.8); opacity:0 }
  }

  .btn{
    position:absolute;
    bottom:14px; left:50%;
    transform:translateX(-50%);
    background: linear-gradient(180deg,#ff8db7,#ff5b98);
    color:white; border:none; border-radius:999px;
    padding:10px 18px; font-weight:700;
    box-shadow:0 10px 28px rgba(255,59,125,.35);
    cursor:pointer; opacity:0; pointer-events:none;
    transition: opacity .4s ease;
  }
  .show-btn .btn{ opacity:1; pointer-events:auto }

  .footer{
    position:absolute; bottom:10px; left:0; right:0;
    text-align:center; font-size:12px; opacity:.6;
  }
</style>
</head>
<body>
  <div class="scene">

    <img class="sticker left" src="sticker-LEFT.png" alt="Dudu Bubu sticker left" style="--rot:-8deg">
    <img class="sticker right" src="sticker-RIGHT.png" alt="Dudu Bubu sticker right" style="--rot:8deg">

    <div class="card">
      <div class="envelope-wrap" id="env">
        <div class="hint" id="hint">tap to open 💌</div>

        <div class="envelope" aria-label="Envelope">
          <svg viewBox="0 0 800 520" xmlns="http://www.w3.org/2000/svg">
            <rect x="40" y="60" width="720" height="380" rx="26" fill="#fff3f8" stroke="#ff9bc1" stroke-width="4"/>
            <path d="M60 80 H740 V410 H60 Z" fill="url(#lip)" opacity=".8"/>
            <rect x="70" y="100" width="680" height="300" rx="18" fill="#ffffff" opacity=".65"/>
            <g class="flap" style="transform-origin:400px 100px">
              <path d="M40 60 L400 320 L760 60 Z" fill="#ffc1d9" stroke="#ff9bc1" stroke-width="4"/>
              <path d="M70 60 L400 300 L730 60 Z" fill="#ffd4e5" opacity=".65"/>
            </g>
            <path d="M40 440 L400 220 L760 440 Z" fill="#ffd3e6" stroke="#ff9bc1" stroke-width="4"/>
            <defs>
              <linearGradient id="lip" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0" stop-color="#ffd8e8"/>
                <stop offset="1" stop-color="#ffd1e3" stop-opacity=".5"/>
              </linearGradient>
            </defs>
          </svg>
        </div>

        <div class="letter" id="letter" role="dialog" aria-live="polite">
          <div class="note">
            <h1>Mine Duduuuuuuuu babyyyyyyyy girl 💖</h1>
            <p id="typeTarget"></p>
            <div class="signature">— always yours 💖</div>
          </div>
        </div>

        <div class="hearts" id="hearts"></div>
        <button class="btn" id="btnAgain">replay magic ✨</button>
      </div>
    </div>

    <div class="footer">made with love (and panic) 💗</div>
  </div>

<script>
  const apology = "I'm sooooo sorryyyyyy Mine Cute Duduuuuuuuuu Baby girl💋💕❤️💗😚💞🎀💓";

  const env = document.getElementById('env');
  const typeTarget = document.getElementById('typeTarget');
  const hearts = document.getElementById('hearts');
  const hint = document.getElementById('hint');
  const btnAgain = document.getElementById('btnAgain');

  let opened = false;
  let typingTimer;

  function typeWriter(text, el, speed=45){
    clearTimeout(typingTimer);
    el.textContent = "";
    let i=0;
    (function tick(){
      if(i <= text.length){
        el.textContent = text.slice(0, i++);
        typingTimer = setTimeout(tick, speed);
      }
    })();
  }

  function burstHearts(count=22){
    const symbols = ["💗","💓","💞","💖","💕","❤️","💘","💝","😚","🥰","✨"];
    const w = hearts.clientWidth;
    for(let i=0;i<count;i++){
      const span = document.createElement('span');
      span.className = 'heart';
      span.textContent = symbols[Math.floor(Math.random()*symbols.length)];
      span.style.left = Math.random()*w + 'px';
      span.style.fontSize = (16 + Math.random()*22) + 'px';
      span.style.animationDuration = (2.6 + Math.random()*1.6) + 's';
      span.style.animationDelay = (Math.random()*0.6) + 's';
      hearts.appendChild(span);
      setTimeout(()=> span.remove(), 4000);
    }
  }

  function openEnvelope() {
    if(opened) return;
    opened = true;
    env.classList.add('open');
    hint.style.opacity = 0;
    setTimeout(()=> {
      typeWriter(apology, typeTarget);
      burstHearts(28);
      env.classList.add('show-btn');
    }, 350);
  }

  env.addEventListener('click', openEnvelope);
  btnAgain.addEventListener('click', () => {
    opened = false;
    env.classList.remove('open','show-btn');
    typeTarget.textContent = "";
    hint.style.opacity = 1;
    setTimeout(openEnvelope, 220);
  });

  setTimeout(()=> burstHearts(10), 600);
</script>
</body>
</html>
 
