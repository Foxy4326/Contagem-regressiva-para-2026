<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>📖 Bíblia Sagrada | Contagem Regressiva 2026 – por Tysi</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:'Segoe UI',sans-serif;min-height:100vh;display:flex;flex-direction:column;align-items:center;padding-top:90px;overflow-x:hidden;transition:background .5s,color .5s}
body.dark{background:linear-gradient(135deg,#0d1b2a,#1b263b,#2c3e50);color:white}
body.light{background:linear-gradient(135deg,#fff,#fff9f0,#f0f0f0);color:#1a1a2e}

/* TOPO */
.top-bar{position:fixed;top:0;width:100%;padding:1rem 2rem;display:flex;justify-content:space-between;align-items:center;z-index:100;background:rgba(13,27,42,.95);border-bottom:1px solid rgba(255,215,0,.3)}
body.light .top-bar{background:rgba(255,255,255,.95);border-bottom:1px solid #DAA520}
.logo{font-weight:bold;color:#FFD700;display:flex;align-items:center;gap:.5rem}
.date-display{text-align:right}
.weekday{font-weight:600;color:#FFD700}
.full-date{font-size:.9rem;color:#ccc}
body.light .weekday{color:#DAA520}
body.light .full-date{color:#555}

/* BOTÕES MENU */
.menu-buttons{display:flex;gap:1rem;flex-wrap:wrap;justify-content:center;margin-top:1.5rem}
.btn{display:inline-flex;align-items:center;gap:.6rem;padding:.8rem 1.5rem;border-radius:50px;font-weight:700;text-decoration:none;transition:.2s}
.btn:hover{transform:translateY(-2px)}
.btn-bible{background:linear-gradient(135deg,#d4b060,#f9e89f);color:#1a1a2e;border:2px solid #FFD700}
.btn-youtube{background:#c4302b;color:white;border:2px solid #FFD700}
.btn-video{background:linear-gradient(135deg,#6a0dad,#9b30ff);color:white}
.btn-login{background:rgba(30,58,138,0.8);color:white}
.btn-signup{background:rgba(13,148,136,0.8);color:white}

/* CONTAGEM */
.container{display:flex;gap:1rem;margin:1.5rem 0;flex-wrap:wrap;justify-content:center}
.time-segment{background:#0d1b2a;border:1px solid rgba(255,215,0,.2);border-radius:12px;padding:1rem .7rem;min-width:90px;text-align:center}
body.light .time-segment{background:#fff9f0;border:1px solid #DAA520}
.number{font-size:2rem;font-weight:bold;color:#FFD700;text-shadow:0 0 8px rgba(255,215,0,.6)}
.label{text-transform:uppercase;letter-spacing:1px;font-size:.8rem;color:#ccc}
body.light .label{color:#555}

/* CHAT */
.chat-section{margin-top:2.5rem;background:rgba(20,30,50,.7);padding:1.5rem;border-radius:20px;width:90%;max-width:600px}
body.light .chat-section{background:rgba(240,240,240,.7);color:#1a1a2e}
#spiritualChatBox{height:220px;overflow-y:auto;background:rgba(0,0,0,.3);padding:1rem;border-radius:10px;margin-bottom:1rem;font-size:.95rem}
body.light #spiritualChatBox{background:rgba(200,200,200,.3);color:#1a1a2e}
#spiritualChatInput{width:70%;padding:.7rem;border-radius:50px;border:none;outline:none;background:rgba(255,255,255,.1);color:white}
body.light #spiritualChatInput{background:rgba(0,0,0,.05);color:#1a1a2e}
.send-btn{padding:.7rem 1.2rem;background:#4B0082;color:white;border:none;border-radius:50px;cursor:pointer}

/* CALENDÁRIO */
#calendar{margin-top:2rem;max-width:400px;border:2px solid #FFD700;border-radius:12px;overflow:hidden}
#calendar th{background:#0d1b2a;color:#FFD700}
body.light #calendar th{background:#DAA520;color:#1a1a2e}
#calendar table{width:100%;border-collapse:collapse;text-align:center}
#calendar th,#calendar td{padding:8px}
#calendar td{height:40px;transition:.3s}
#calendar td:hover{background:rgba(255,215,0,.3);border-radius:50%}
body.light #calendar td:hover{background:rgba(218,165,32,.3)}

/* TEMA E PLAY PROTECT */
#themeToggle{position:fixed;bottom:20px;right:20px;padding:.7rem 1.2rem;border:none;border-radius:50px;font-weight:bold;cursor:pointer;z-index:1000;background:#FFD700;color:#1a1a2e}
#playProtect{display:none;position:fixed;top:20px;left:50%;transform:translateX(-50%);background:#0d1b2a;color:#FFD700;padding:12px 20px;border-radius:10px;border:1px solid #FFD700;z-index:10000}

/* ELEMENTOS FLUTUANTES */
.spiritual-element{position:fixed;opacity:.7;animation:float 15s infinite ease-in-out}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-20px)}}

/* FOOTER */
footer{margin:2rem 0;font-size:.85rem;color:#FFD700}
body.light footer{color:#DAA520}
</style>
</head>
<body class="dark">

<div class="top-bar">
  <div class="logo"><i class="fas fa-bible"></i> Bíblia Sagrada</div>
  <div class="date-display">
    <div class="weekday" id="weekday">Carregando...</div>
    <div class="full-date" id="full-date">—</div>
  </div>
</div>

<main>
  <h1>⏳ Contagem Regressiva para 2026</h1>

  <div class="container">
    <div class="time-segment"><div class="number" id="weeks">000</div><div class="label">Semanas</div></div>
    <div class="time-segment"><div class="number" id="days">000</div><div class="label">Dias</div></div>
    <div class="time-segment"><div class="number" id="hours">00</div><div class="label">Horas</div></div>
    <div class="time-segment"><div class="number" id="minutes">00</div><div class="label">Minutos</div></div>
    <div class="time-segment"><div class="number" id="seconds">00</div><div class="label">Segundos</div></div>
  </div>

  <div class="menu-buttons">
    <a href="https://youtube.com/@bibliasagrada-r3c4o?si=rcpyTgzjQt9DRdUL" target="_blank" class="btn btn-youtube"><i class="fab fa-youtube"></i> Canal YouTube</a>
    <a href="#" class="btn btn-bible"><i class="fas fa-book"></i> Ler Bíblia</a>
    <a href="#" class="btn btn-video"><i class="fas fa-video"></i> Vídeos</a>
    <a href="#" class="btn btn-login"><i class="fas fa-user"></i> Login</a>
    <a href="#" class="btn btn-signup"><i class="fas fa-user-plus"></i> Cadastrar</a>
  </div>

  <div class="chat-section">
    <h3>💬 Chat Espiritual</h3>
    <div id="spiritualChatBox"></div>
    <div>
      <input type="text" id="spiritualChatInput" placeholder="Escreva sua oração ou dúvida...">
      <button class="send-btn" onclick="sendSpiritualMessage()">Enviar</button>
      <button class="send-btn" onclick="clearSpiritualChat()">Limpar</button>
    </div>
  </div>

  <div id="calendar">
    <div style="display:flex;justify-content:space-between;padding:8px;background:#0d1b2a;color:#FFD700">
      <span id="prev-month" style="cursor:pointer">&#8592;</span>
      <span id="month-year">Mês Ano</span>
      <span id="next-month" style="cursor:pointer">&#8594;</span>
    </div>
    <table>
      <thead><tr><th>Dom</th><th>Seg</th><th>Ter</th><th>Qua</th><th>Qui</th><th>Sex</th><th>Sáb</th></tr></thead>
      <tbody id="calendar-body"></tbody>
    </table>
  </div>
</main>

<button id="themeToggle">🌙</button>
<div id="playProtect"><i class="fas fa-shield-alt"></i> Verificando site...</div>
<footer>© 2025 Bíblia Sagrada | Criado por <b>Tysi</b></footer>

<script>
const themeToggle=document.getElementById("themeToggle");
function updateTheme(m){document.body.className=m;themeToggle.textContent=m==='dark'?'🌙':'☀️'}
let saved=localStorage.getItem("theme")||(window.matchMedia('(prefers-color-scheme: dark)').matches?'dark':'light');
updateTheme(saved);
themeToggle.onclick=()=>{let n=document.body.classList.contains('dark')?'light':'dark';updateTheme(n);localStorage.setItem('theme',n)}

function sitePlayProtect(){const b=document.getElementById('playProtect');b.style.display='block';setTimeout(()=>{b.innerHTML='<i class="fas fa-check-circle"></i> Site verificado e seguro!';setTimeout(()=>{b.style.opacity='0';setTimeout(()=>b.style.display='none',1000)},2000)},1500)}
window.onload=sitePlayProtect;

function updateCurrentDate(){const n=new Date();const w={weekday:'long',timeZone:'America/Sao_Paulo'};const d={day:'numeric',month:'long',year:'numeric',timeZone:'America/Sao_Paulo'};document.getElementById('weekday').textContent=n.toLocaleDateString('pt-BR',w);document.getElementById('full-date').textContent=n.toLocaleDateString('pt-BR',d)}
function updateCountdown(){const t=Date.UTC(2026,0,1,0,0,0),n=Date.now(),diff=Math.max(0,t-n);const s=Math.floor(diff/1e3)%60,m=Math.floor(diff/1e3/60)%60,h=Math.floor(diff/1e3/60/60)%24,d=Math.floor(diff/1e3/60/60/24),w=Math.floor(d/7);document.getElementById('weeks').textContent=w;document.getElementById('days').textContent=d;document.getElementById('hours').textContent=h.toString().padStart(2,'0');document.getElementById('minutes').textContent=m.toString().padStart(2,'0');document.getElementById('seconds').textContent=s.toString().padStart(2,'0')}
setInterval(updateCurrentDate,6e4);setInterval(updateCountdown,1e3);updateCurrentDate();updateCountdown();

function sendSpiritualMessage(){const i=document.getElementById('spiritualChatInput');if(i.value.trim()==='')return;const u=i.value.trim();const r='💡 Resposta: "'+u+' – Confie, Deus é contigo!"';const b=document.getElementById('spiritualChatBox');b.innerHTML+=`<p><b>Você:</b> ${u}</p><p>${r}</p>`;b.scrollTop=b.scrollHeight;i.value=''}
function clearSpiritualChat(){document.getElementById('spiritualChatBox').innerHTML=''}

const calBody=document.getElementById('calendar-body');let today=new Date();let cM=today.getMonth(),cY=today.getFullYear();
function renderCalendar(m,y){const f=new Date(y,m,1).getDay(),days=new Date(y,m+1,0).getDate(),names=['Janeiro','Fevereiro','Março','Abril','Maio','Junho','Julho','Agosto','Setembro','Outubro','Novembro','Dezembro'];document.getElementById('month-year').textContent=names[m]+' '+y;calBody.innerHTML='';let d=1;for(let i=0;i<6;i++){let r=document.createElement('tr');for(let j=0;j<7;j++){let cell=document.createElement('td');if(i===0&&j<f)cell.textContent='';else if(d>days)cell.textContent='';else{cell.textContent=d;if(d===today.getDate()&&m===today.getMonth()&&y===today.getFullYear()){cell.style.background='#FFD700';cell.style.color='#1a1a2e';cell.style.fontWeight='bold'}d++}r.appendChild(cell)}calBody.appendChild(r)}}
document.getElementById('prev-month').onclick=()=>{cM--;if(cM<0){cM=11;cY--;}renderCalendar(cM,cY)}
document.getElementById('next-month').onclick=()=>{cM++;if(cM>11){cM=0;cY++;}renderCalendar(cM,cY)}
renderCalendar(cM,cY);

function spawnSpiritualElements(){const icons=['📖','✝️','🕊️','🙏','💫'];for(let i=0;i<15;i++){const e=document.createElement('div');e.className='spiritual-element';e.textContent=icons[Math.floor(Math.random()*icons.length)];e.style.top=Math.random()*90+'%';e.style.left=Math.random()*90+'%';e.style.fontSize=(20+Math.random()*30)+'px';document.body.appendChild(e)}}
spawnSpiritualElements();
</script>
</body>
</html>
