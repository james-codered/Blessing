<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1">
<title>A Little Surprise for Blessing</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,500;1,600&family=Marck+Script&family=Nunito:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --cream:#fbf6f0;
    --blush:#f7e3e6;
    --rose:#e3a8ae;
    --deep-rose:#b5646f;
    --wine:#5c3540;
    --gold:#c9a15a;
    --gold-soft:#e7d3ab;
    --ink:#4a323a;
  }

  *{margin:0;padding:0;box-sizing:border-box;}

  html,body{
    width:100%;
    overflow-x:hidden;
    background:var(--cream);
    color:var(--ink);
    font-family:'Nunito',sans-serif;
    -webkit-tap-highlight-color:transparent;
  }

  body{
    background:
      radial-gradient(circle at 15% 10%, #fdeef0 0%, transparent 45%),
      radial-gradient(circle at 85% 25%, #f6e6d8 0%, transparent 50%),
      radial-gradient(circle at 50% 90%, #f3dfe4 0%, transparent 55%),
      var(--cream);
    min-height:100vh;
    position:relative;
  }

  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.01ms !important; animation-iteration-count:1 !important; transition-duration:0.01ms !important;}
  }

  /* floating petal field */
  #petal-field{
    position:fixed;
    inset:0;
    pointer-events:none;
    z-index:1;
    overflow:hidden;
  }
  .petal{
    position:absolute;
    top:-5%;
    font-size:16px;
    opacity:0.55;
    animation:fall linear infinite;
    filter:drop-shadow(0 2px 3px rgba(181,100,111,0.15));
  }
  @keyframes fall{
    0%{transform:translateY(-10vh) translateX(0) rotate(0deg);}
    100%{transform:translateY(110vh) translateX(var(--drift,20px)) rotate(360deg);}
  }

  main{
    position:relative;
    z-index:2;
    max-width:560px;
    margin:0 auto;
    padding:38px 20px 60px;
  }

  /* ---------- HERO ---------- */
  .eyebrow{
    text-align:center;
    font-size:0.95rem;
    letter-spacing:0.02em;
    color:var(--deep-rose);
    font-weight:600;
    opacity:0;
    animation:fadeUp 0.9s ease forwards;
  }

  .lead-line{
    text-align:center;
    font-family:'Cormorant Garamond',serif;
    font-style:italic;
    font-size:1.15rem;
    color:var(--wine);
    margin-top:6px;
    opacity:0;
    animation:fadeUp 0.9s ease 0.15s forwards;
  }

  @keyframes fadeUp{
    from{opacity:0; transform:translateY(14px);}
    to{opacity:1; transform:translateY(0);}
  }

  /* portrait */
  .portrait-wrap{
    position:relative;
    width:min(78vw, 300px);
    margin:34px auto 0;
    opacity:0;
    animation:fadeUp 1s ease 0.3s forwards;
  }
  .portrait-glow{
    position:absolute;
    inset:-18px;
    border-radius:50%;
    background:radial-gradient(circle, rgba(233,180,190,0.55) 0%, rgba(233,180,190,0) 70%);
    filter:blur(6px);
    animation:pulse-glow 4.5s ease-in-out infinite;
    z-index:0;
  }
  @keyframes pulse-glow{
    0%,100%{transform:scale(1); opacity:0.8;}
    50%{transform:scale(1.08); opacity:1;}
  }
  .portrait-frame{
    position:relative;
    z-index:1;
    border-radius:50%;
    padding:6px;
    background:linear-gradient(135deg, var(--gold-soft), var(--rose) 40%, var(--gold-soft) 100%);
    box-shadow:0 18px 40px -12px rgba(181,100,111,0.45);
  }
  .portrait-frame img{
    display:block;
    width:100%;
    aspect-ratio:1/1;
    object-fit:cover;
    border-radius:50%;
    border:4px solid var(--cream);
  }
  .portrait-deco{
    position:absolute;
    font-size:1.4rem;
    z-index:2;
    animation:sway 3.6s ease-in-out infinite;
  }
  .portrait-deco.d1{ top:-6px; left:-10px; animation-delay:0s;}
  .portrait-deco.d2{ bottom:2px; right:-14px; font-size:1.6rem; animation-delay:0.6s;}
  .portrait-deco.d3{ top:40%; right:-22px; font-size:1.1rem; animation-delay:1.2s;}
  @keyframes sway{
    0%,100%{transform:rotate(-6deg) translateY(0);}
    50%{transform:rotate(6deg) translateY(-6px);}
  }

  .chapter{
    text-align:center;
    margin-top:26px;
    font-family:'Cormorant Garamond',serif;
    font-weight:600;
    font-size:2.05rem;
    letter-spacing:0.01em;
    color:var(--wine);
    opacity:0;
    animation:fadeUp 0.9s ease 0.5s forwards;
  }
  .chapter .age-num{
    background:linear-gradient(120deg, var(--deep-rose), var(--gold) 60%, var(--deep-rose));
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
  }

  .subline{
    text-align:center;
    margin-top:8px;
    font-size:0.98rem;
    color:#7a5a63;
    font-style:italic;
    font-family:'Cormorant Garamond',serif;
    opacity:0;
    animation:fadeUp 0.9s ease 0.65s forwards;
  }

  /* ---------- COUNTDOWN ---------- */
  .countdown-section{
    margin-top:44px;
    text-align:center;
  }
  .countdown-title{
    font-size:0.85rem;
    letter-spacing:0.14em;
    text-transform:uppercase;
    color:var(--deep-rose);
    font-weight:700;
    margin-bottom:16px;
  }
  .countdown-grid{
    display:grid;
    grid-template-columns:repeat(4, 1fr);
    gap:10px;
    max-width:420px;
    margin:0 auto;
  }
  .count-card{
    background:linear-gradient(160deg, #fffdfb, var(--blush));
    border:1px solid rgba(201,161,90,0.35);
    border-radius:16px;
    padding:14px 4px 12px;
    box-shadow:0 10px 24px -14px rgba(181,100,111,0.4);
  }
  .count-num{
    font-family:'Cormorant Garamond',serif;
    font-weight:600;
    font-size:clamp(1.7rem, 7vw, 2.3rem);
    color:var(--wine);
    line-height:1;
    font-variant-numeric:tabular-nums;
  }
  .count-label{
    margin-top:6px;
    font-size:0.62rem;
    letter-spacing:0.12em;
    text-transform:uppercase;
    color:#9c7680;
    font-weight:600;
  }

  .celebration{
    display:none;
    font-family:'Cormorant Garamond',serif;
    font-size:1.5rem;
    font-weight:600;
    color:var(--wine);
    padding:26px 18px;
    background:linear-gradient(160deg, #fffdfb, var(--blush));
    border-radius:20px;
    border:1px solid rgba(201,161,90,0.4);
  }

  /* ---------- GIFT SECTION ---------- */
  .gift-section{
    margin-top:64px;
    text-align:center;
    position:relative;
  }
  .flower-row{
    display:flex;
    justify-content:center;
    gap:22px;
    font-size:1.5rem;
    margin-bottom:18px;
  }
  .flower-row span{
    display:inline-block;
    animation:sway 4s ease-in-out infinite;
  }
  .flower-row span:nth-child(2){animation-delay:0.5s;}
  .flower-row span:nth-child(3){animation-delay:1s;}

  .gift-hint{
    font-size:0.85rem;
    color:#9c7680;
    font-style:italic;
    font-family:'Cormorant Garamond',serif;
    margin-bottom:14px;
    animation:hint-fade 2.4s ease-in-out infinite;
  }
  @keyframes hint-fade{
    0%,100%{opacity:0.5;}
    50%{opacity:1;}
  }

  .gift-box{
    display:inline-block;
    cursor:pointer;
    font-size:4.2rem;
    background:none;
    border:none;
    line-height:1;
    animation:float-box 3s ease-in-out infinite;
    filter:drop-shadow(0 12px 18px rgba(181,100,111,0.35));
    transition:transform 0.25s ease;
    padding:10px;
  }
  .gift-box:active{transform:scale(0.9);}
  @keyframes float-box{
    0%,100%{transform:translateY(0) rotate(-2deg);}
    50%{transform:translateY(-10px) rotate(2deg);}
  }
  .gift-box.opened{
    animation:pop-open 0.5s ease forwards;
  }
  @keyframes pop-open{
    0%{transform:scale(1);}
    40%{transform:scale(1.35) rotate(-6deg);}
    70%{transform:scale(0.92) rotate(4deg);}
    100%{transform:scale(1) rotate(0);}
  }

  .from-james{
    margin-top:16px;
    font-family:'Cormorant Garamond',serif;
    font-style:italic;
    font-size:1.15rem;
    color:var(--deep-rose);
    font-weight:600;
  }

  .gift-caption{
    margin-top:4px;
    font-size:0.9rem;
    color:#9c7680;
  }

  .hidden-message{
    margin-top:26px;
    max-width:440px;
    margin-left:auto;
    margin-right:auto;
    display:none;
  }
  .hidden-message.show{display:block;}

  .msg-card{
    background:linear-gradient(160deg, #fffdfb, var(--blush));
    border:1px solid rgba(201,161,90,0.4);
    border-radius:20px;
    padding:26px 22px;
    box-shadow:0 16px 34px -16px rgba(181,100,111,0.4);
    opacity:0;
    transform:translateY(16px);
    transition:opacity 0.7s ease, transform 0.7s ease;
  }
  .msg-card.reveal{
    opacity:1;
    transform:translateY(0);
  }
  .msg-card p{
    font-family:'Cormorant Garamond',serif;
    font-size:1.18rem;
    color:var(--wine);
    margin-bottom:12px;
    line-height:1.5;
  }
  .msg-card p:last-child{margin-bottom:0;}
  .msg-card .script{
    font-family:'Marck Script',cursive;
    font-size:1.3rem;
    color:var(--deep-rose);
  }

  footer{
    margin-top:70px;
    text-align:center;
    font-size:0.8rem;
    color:#b593a0;
    letter-spacing:0.02em;
  }

  @media (min-width:600px){
    .chapter{font-size:2.4rem;}
    .count-num{font-size:2.6rem;}
  }
</style>
</head>
<body>

<div id="petal-field"></div>

<main>

  <section class="hero">
    <p class="eyebrow">A little surprise for Blessing ✨</p>
    <p class="lead-line">September 26 is getting closer&hellip;</p>

    <div class="portrait-wrap">
      <div class="portrait-glow"></div>
      <span class="portrait-deco d1">🌸</span>
      <span class="portrait-deco d2">✨</span>
      <span class="portrait-deco d3">🌷</span>
      <div class="portrait-frame">
        <img src="https://i.ibb.co/20KWQgQX/IMG-20260807-WA0082-1.jpg" alt="A portrait of Blessing" style="object-position:center top;">
      </div>
    </div>

    <p class="chapter">Chapter <span class="age-num" id="ageNumber">--</span> ✨</p>
    <p class="subline">Another beautiful chapter is about to begin.</p>
  </section>

  <section class="countdown-section">
    <p class="countdown-title">Counting down to her day</p>
    <div class="countdown-grid" id="countdownGrid">
      <div class="count-card">
        <div class="count-num" id="days">00</div>
        <div class="count-label">Days</div>
      </div>
      <div class="count-card">
        <div class="count-num" id="hours">00</div>
        <div class="count-label">Hours</div>
      </div>
      <div class="count-card">
        <div class="count-num" id="minutes">00</div>
        <div class="count-label">Minutes</div>
      </div>
      <div class="count-card">
        <div class="count-num" id="seconds">00</div>
        <div class="count-label">Seconds</div>
      </div>
    </div>
    <div class="celebration" id="celebration">It&rsquo;s finally here! 🎂✨<br>Happy Birthday, Blessing!</div>
  </section>

  <section class="gift-section">
    <div class="flower-row">
      <span>🌸</span><span>🌷</span><span>🌸</span>
    </div>

    <p class="gift-hint" id="giftHint">tap the gift, if you dare 👉</p>
    <button class="gift-box" id="giftBox" aria-label="Open your gift">🎁</button>

    <p class="from-james">From James 🌷</p>
    <p class="gift-caption">a little something for you</p>

    <div class="hidden-message" id="hiddenMessage">
      <div class="msg-card reveal-1">
        <p>You thought that was all? 😂</p>
        <p>You still have to wait until September 26.</p>
      </div>
      <div class="msg-card reveal-2" style="margin-top:14px;">
        <p class="script">But I couldn&rsquo;t let the countdown begin without leaving you a little something from me. 🌸</p>
      </div>
    </div>
  </section>

  <footer>Made with care by James</footer>

</main>

<script>
  /* =========================================================
     EDIT THIS: Blessing's birth year, used to calculate her
     age automatically. Month/day stay September 26.
     ========================================================= */
  const birthDate = new Date("2000-09-26"); // <-- change 2000 to her real birth year

  /* ---------- Age calculation ---------- */
  function calculateAge(birth, now){
    let age = now.getFullYear() - birth.getFullYear();
    const hasHadBirthdayThisYear =
      (now.getMonth() > birth.getMonth()) ||
      (now.getMonth() === birth.getMonth() && now.getDate() >= birth.getDate());
    if(!hasHadBirthdayThisYear) age--;
    return age;
  }

  function renderAge(){
    const now = new Date();
    document.getElementById('ageNumber').textContent = calculateAge(birthDate, now);
  }

  /* ---------- Countdown to next Sept 26 ---------- */
  function getNextBirthday(now){
    const year = now.getFullYear();
    let next = new Date(year, 8, 26, 0, 0, 0); // month index 8 = September
    const todayStripped = new Date(now.getFullYear(), now.getMonth(), now.getDate());
    const birthdayStripped = new Date(year, 8, 26);

    if(todayStripped.getTime() === birthdayStripped.getTime()){
      return 'today';
    }
    if(now > next){
      next = new Date(year + 1, 8, 26, 0, 0, 0);
    }
    return next;
  }

  function pad(n){ return n.toString().padStart(2,'0'); }

  function tickCountdown(){
    const now = new Date();
    const next = getNextBirthday(now);

    if(next === 'today'){
      document.getElementById('countdownGrid').style.display = 'none';
      document.getElementById('celebration').style.display = 'block';
      renderAge();
      return;
    }

    const diff = next - now;
    const days = Math.floor(diff / (1000*60*60*24));
    const hours = Math.floor((diff / (1000*60*60)) % 24);
    const minutes = Math.floor((diff / (1000*60)) % 60);
    const seconds = Math.floor((diff / 1000) % 60);

    document.getElementById('days').textContent = pad(days);
    document.getElementById('hours').textContent = pad(hours);
    document.getElementById('minutes').textContent = pad(minutes);
    document.getElementById('seconds').textContent = pad(seconds);

    renderAge();
  }

  tickCountdown();
  setInterval(tickCountdown, 1000);

  /* ---------- Gift interaction ---------- */
  const giftBox = document.getElementById('giftBox');
  const hiddenMessage = document.getElementById('hiddenMessage');
  const giftHint = document.getElementById('giftHint');
  let opened = false;

  giftBox.addEventListener('click', () => {
    if(opened) return;
    opened = true;
    giftBox.classList.add('opened');
    giftHint.style.display = 'none';
    hiddenMessage.classList.add('show');
    spawnPetalBurst();

    const cards = hiddenMessage.querySelectorAll('.msg-card');
    cards.forEach((card, i) => {
      setTimeout(() => card.classList.add('reveal'), 250 + i * 500);
    });
  });

  /* ---------- Ambient floating petals ---------- */
  const petalField = document.getElementById('petal-field');
  const petalEmojis = ['🌸','🌷','✨'];

  function spawnPetal(){
    const petal = document.createElement('span');
    petal.className = 'petal';
    petal.textContent = petalEmojis[Math.floor(Math.random()*petalEmojis.length)];
    const left = Math.random()*100;
    const duration = 9 + Math.random()*8;
    const drift = (Math.random()*80 - 40) + 'px';
    petal.style.left = left + 'vw';
    petal.style.setProperty('--drift', drift);
    petal.style.animationDuration = duration + 's';
    petal.style.fontSize = (12 + Math.random()*10) + 'px';
    petalField.appendChild(petal);
    setTimeout(() => petal.remove(), duration*1000 + 200);
  }

  for(let i=0; i<6; i++){
    setTimeout(spawnPetal, i*900);
  }
  setInterval(spawnPetal, 1600);

  function spawnPetalBurst(){
    for(let i=0; i<14; i++){
      setTimeout(spawnPetal, i*60);
    }
  }
</script>

</body>
</html>

