<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Priyanshu Mishra — AI Systems Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;600;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #060810;
    --surface: #0d1117;
    --surface2: #111827;
    --border: rgba(99,179,237,0.15);
    --accent: #63b3ed;
    --accent2: #9f7aea;
    --accent3: #68d391;
    --text: #e2e8f0;
    --muted: #718096;
    --dim: #4a5568;
    --mono: 'Space Mono', monospace;
    --sans: 'Syne', sans-serif;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  body{background:var(--bg);color:var(--text);font-family:var(--sans);overflow-x:hidden;min-height:100vh;}

  /* HERO */
  .hero{position:relative;min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;overflow:hidden;}
  #neural-canvas{position:absolute;inset:0;width:100%;height:100%;opacity:0.5;}
  .hero-content{position:relative;z-index:2;text-align:center;padding:2rem;}
  .glitch-name{font-family:var(--sans);font-weight:800;font-size:clamp(2.5rem,8vw,6rem);letter-spacing:-2px;color:#fff;position:relative;display:inline-block;}
  .glitch-name::before,.glitch-name::after{content:attr(data-text);position:absolute;top:0;left:0;width:100%;}
  .glitch-name::before{color:var(--accent);clip-path:polygon(0 0,100% 0,100% 35%,0 35%);animation:glitch1 3s infinite;}
  .glitch-name::after{color:var(--accent2);clip-path:polygon(0 65%,100% 65%,100% 100%,0 100%);animation:glitch2 3s infinite;}
  @keyframes glitch1{0%,90%,100%{transform:translate(0)}91%{transform:translate(-3px,1px)}93%{transform:translate(3px,-1px)}95%{transform:translate(-2px,2px)}}
  @keyframes glitch2{0%,88%,100%{transform:translate(0)}89%{transform:translate(3px,-2px)}92%{transform:translate(-3px,1px)}96%{transform:translate(2px,-1px)}}
  .title-badge{font-family:var(--mono);font-size:0.85rem;color:var(--accent);border:1px solid var(--border);padding:6px 18px;border-radius:2px;letter-spacing:3px;text-transform:uppercase;margin:1.2rem 0;display:inline-block;animation:fadeIn 1s 0.4s both;}
  .subtitle{font-family:var(--mono);font-size:0.9rem;color:var(--muted);max-width:500px;line-height:1.8;animation:fadeIn 1s 0.7s both;}
  .typed-line{min-height:1.5em;}
  #typed-text{color:var(--accent3);}
  .cursor{display:inline-block;width:2px;height:1em;background:var(--accent3);animation:blink 0.7s infinite;vertical-align:text-bottom;}
  @keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
  @keyframes fadeIn{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:none}}
  .hero-cta{display:flex;gap:12px;justify-content:center;margin-top:2.5rem;animation:fadeIn 1s 1s both;}
  .btn{font-family:var(--mono);font-size:0.75rem;padding:10px 22px;border-radius:2px;letter-spacing:2px;text-transform:uppercase;cursor:pointer;transition:all 0.2s;text-decoration:none;}
  .btn-primary{background:var(--accent);color:#000;border:none;}
  .btn-primary:hover{background:#fff;transform:translateY(-2px);}
  .btn-ghost{background:transparent;color:var(--accent);border:1px solid var(--accent);}
  .btn-ghost:hover{background:rgba(99,179,237,0.1);transform:translateY(-2px);}
  .scroll-hint{position:absolute;bottom:2rem;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:8px;animation:fadeIn 1s 1.5s both;}
  .scroll-hint span{font-family:var(--mono);font-size:0.7rem;color:var(--dim);letter-spacing:2px;}
  .scroll-arrow{width:1px;height:48px;background:linear-gradient(to bottom,var(--dim),transparent);animation:scrollPulse 2s infinite;}
  @keyframes scrollPulse{0%,100%{opacity:0.3}50%{opacity:1}}

  /* SECTIONS */
  section{padding:80px 24px;max-width:900px;margin:0 auto;}
  .section-label{font-family:var(--mono);font-size:0.7rem;color:var(--accent);letter-spacing:4px;text-transform:uppercase;margin-bottom:12px;display:flex;align-items:center;gap:12px;}
  .section-label::after{content:'';flex:1;height:1px;background:var(--border);}
  h2{font-family:var(--sans);font-size:clamp(1.6rem,4vw,2.4rem);font-weight:800;color:#fff;margin-bottom:2rem;}

  /* FOCUS PILLS */
  .focus-grid{display:flex;flex-wrap:wrap;gap:10px;margin-top:1rem;}
  .focus-pill{font-family:var(--mono);font-size:0.75rem;padding:8px 16px;border:1px solid var(--border);border-radius:2px;color:var(--muted);letter-spacing:1px;transition:all 0.3s;cursor:default;}
  .focus-pill:hover{border-color:var(--accent);color:var(--accent);background:rgba(99,179,237,0.07);}
  .focus-pill.accent{border-color:var(--accent2);color:var(--accent2);}
  .focus-pill.green{border-color:var(--accent3);color:var(--accent3);}

  /* PHILOSOPHY CARDS */
  .phil-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:16px;margin-top:1rem;}
  .phil-card{background:var(--surface2);border:1px solid var(--border);padding:24px 20px;border-radius:2px;transition:border-color 0.3s,transform 0.3s;}
  .phil-card:hover{border-color:var(--accent2);transform:translateY(-3px);}
  .phil-card .icon{font-size:1.5rem;margin-bottom:12px;}
  .phil-card h3{font-size:0.85rem;font-family:var(--mono);color:#fff;letter-spacing:1px;margin-bottom:8px;}
  .phil-card p{font-size:0.8rem;color:var(--muted);line-height:1.7;font-family:var(--mono);}

  /* STATS */
  .stats-row{display:flex;flex-wrap:wrap;gap:16px;justify-content:center;}
  .stat-card{background:var(--surface2);border:1px solid var(--border);padding:28px 32px;flex:1;min-width:140px;text-align:center;border-radius:2px;transition:all 0.3s;}
  .stat-card:hover{border-color:var(--accent);background:rgba(99,179,237,0.05);}
  .stat-num{font-family:var(--mono);font-size:2.4rem;font-weight:700;color:var(--accent);display:block;}
  .stat-label{font-family:var(--mono);font-size:0.7rem;color:var(--muted);letter-spacing:2px;margin-top:6px;text-transform:uppercase;}

  /* GAME SECTION */
  #game-section{max-width:900px;margin:0 auto;padding:80px 24px;}
  .game-header{display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:12px;margin-bottom:24px;}
  .game-title{font-family:var(--sans);font-size:1.6rem;font-weight:800;color:#fff;}
  .game-subtitle{font-family:var(--mono);font-size:0.75rem;color:var(--muted);margin-top:4px;}
  .game-meta{font-family:var(--mono);font-size:0.7rem;color:var(--dim);text-align:right;}
  .game-controls{display:flex;gap:10px;margin-bottom:16px;flex-wrap:wrap;align-items:center;}
  .game-btn{font-family:var(--mono);font-size:0.7rem;padding:8px 16px;border:1px solid var(--border);background:transparent;color:var(--text);border-radius:2px;cursor:pointer;letter-spacing:1px;text-transform:uppercase;transition:all 0.2s;}
  .game-btn:hover{border-color:var(--accent);color:var(--accent);}
  .game-btn.active{border-color:var(--accent3);color:var(--accent3);background:rgba(104,211,145,0.07);}
  #game-canvas-wrap{border:1px solid var(--border);background:var(--surface2);border-radius:2px;position:relative;overflow:hidden;}
  #game-canvas{display:block;cursor:crosshair;}
  .game-legend{display:flex;gap:16px;margin-top:12px;flex-wrap:wrap;}
  .legend-item{display:flex;align-items:center;gap:6px;font-family:var(--mono);font-size:0.7rem;color:var(--muted);}
  .legend-dot{width:10px;height:10px;border-radius:2px;flex-shrink:0;}
  #game-status{font-family:var(--mono);font-size:0.75rem;color:var(--accent3);margin-top:10px;min-height:1.2em;}

  /* TECH STACK */
  .stack-wrap{display:flex;flex-wrap:wrap;gap:8px;}
  .stack-tag{font-family:var(--mono);font-size:0.72rem;padding:5px 12px;border:1px solid var(--border);color:var(--dim);border-radius:1px;letter-spacing:1px;transition:all 0.2s;}
  .stack-tag:hover{color:var(--accent);border-color:var(--accent);}

  /* FOOTER */
  footer{border-top:1px solid var(--border);padding:48px 24px;text-align:center;}
  .footer-quote{font-family:var(--sans);font-size:clamp(1.2rem,3vw,1.8rem);font-weight:800;color:#fff;letter-spacing:-0.5px;}
  .footer-sub{font-family:var(--mono);font-size:0.75rem;color:var(--dim);margin-top:16px;letter-spacing:2px;}
  .github-link{display:inline-flex;align-items:center;gap:8px;margin-top:24px;font-family:var(--mono);font-size:0.75rem;color:var(--accent);text-decoration:none;border:1px solid var(--border);padding:10px 20px;border-radius:2px;letter-spacing:2px;text-transform:uppercase;transition:all 0.2s;}
  .github-link:hover{border-color:var(--accent);background:rgba(99,179,237,0.08);}
  .divider{width:1px;height:60px;background:linear-gradient(to bottom,transparent,var(--border),transparent);margin:48px auto;}
  .terminal-line{font-family:var(--mono);font-size:0.8rem;color:var(--dim);text-align:center;margin:8px 0;}
  .terminal-line .prompt{color:var(--accent3);}
  .terminal-line .cmd{color:var(--text);}

  /* SCAN LINE OVERLAY */
  body::after{content:'';position:fixed;inset:0;background:repeating-linear-gradient(0deg,rgba(0,0,0,0.03) 0px,rgba(0,0,0,0.03) 1px,transparent 1px,transparent 2px);pointer-events:none;z-index:9999;}
</style>
</head>
<body>

<!-- HERO -->
<section class="hero">
  <canvas id="neural-canvas"></canvas>
  <div class="hero-content">
    <div class="title-badge">AI Systems Engineer · CognitiveOps Architect</div>
    <h1 class="glitch-name" data-text="PRIYANSHU MISHRA">PRIYANSHU MISHRA</h1>
    <p class="subtitle">
      <span class="typed-line">&gt; <span id="typed-text"></span><span class="cursor"></span></span>
    </p>
    <div class="hero-cta">
      <a class="btn btn-primary" href="https://github.com/priyanshumishra610">github.com/priyanshumishra610</a>
      <a class="btn btn-ghost" href="#game-section">play neural pathfinder ↓</a>
    </div>
  </div>
  <div class="scroll-hint"><span>scroll</span><div class="scroll-arrow"></div></div>
</section>

<!-- TERMINAL LINES -->
<div style="padding:0 24px;max-width:900px;margin:0 auto 40px;">
  <div class="terminal-line"><span class="prompt">~/systems $</span> <span class="cmd">cat focus.md</span></div>
  <div class="terminal-line"><span class="prompt">~/systems $</span> <span class="cmd">./run_intelligence.sh --persistent --adaptive --evolving</span></div>
</div>

<!-- FOCUS -->
<section>
  <div class="section-label">01 · Focus Areas</div>
  <h2>What I Build</h2>
  <div class="focus-grid">
    <div class="focus-pill">Memory-Driven AI</div>
    <div class="focus-pill">AI Agents</div>
    <div class="focus-pill accent">Reasoning Systems</div>
    <div class="focus-pill">Feedback Loops</div>
    <div class="focus-pill green">Intelligence Infrastructure</div>
    <div class="focus-pill accent">Adaptive Architectures</div>
    <div class="focus-pill">Long-Context Pipelines</div>
    <div class="focus-pill green">Self-Improving Systems</div>
  </div>
  <p style="font-family:var(--mono);font-size:0.85rem;color:var(--muted);margin-top:28px;line-height:1.9;max-width:640px;">
    I build <span style="color:#fff">long-lived intelligent systems</span> designed to learn from memory, adapt through feedback, reason across complex workflows, and improve continuously over time.<br><br>
    The goal: <span style="color:var(--accent3)">create systems that become more capable the longer they run.</span>
  </p>
</section>

<!-- PHILOSOPHY -->
<section>
  <div class="section-label">02 · Engineering Philosophy</div>
  <h2>Systems Over Software</h2>
  <div class="phil-grid">
    <div class="phil-card">
      <div class="icon">⬡</div>
      <h3>Persistent Memory</h3>
      <p>State that survives sessions. Knowledge that compounds across time.</p>
    </div>
    <div class="phil-card">
      <div class="icon">⟳</div>
      <h3>Adaptive Loops</h3>
      <p>Systems that observe their own performance and adjust without manual intervention.</p>
    </div>
    <div class="phil-card">
      <div class="icon">◈</div>
      <h3>Reasoning Pipelines</h3>
      <p>Multi-step inference chains. Not pattern matching — actual structured thought.</p>
    </div>
    <div class="phil-card">
      <div class="icon">⊕</div>
      <h3>Modular Intelligence</h3>
      <p>Components that compose. Capabilities that stack. Architecture that endures.</p>
    </div>
  </div>
</section>

<!-- STATS -->
<section>
  <div class="section-label">03 · Activity</div>
  <h2>Development Signal</h2>
  <div class="stats-row">
    <div class="stat-card"><span class="stat-num" id="commits-count">0</span><span class="stat-label">Commits This Year</span></div>
    <div class="stat-card"><span class="stat-num" id="repos-count">0</span><span class="stat-label">Public Repos</span></div>
    <div class="stat-card"><span class="stat-num" id="streak-count">0</span><span class="stat-label">Day Streak</span></div>
    <div class="stat-card"><span class="stat-num" id="stars-count">0</span><span class="stat-label">Stars Earned</span></div>
  </div>
  <p style="font-family:var(--mono);font-size:0.7rem;color:var(--dim);margin-top:14px;text-align:center;letter-spacing:1px;">
    * stats pulled from github-readme-stats · update widget urls for live data
  </p>
</section>

<!-- GAME -->
<section id="game-section">
  <div class="section-label">04 · Neural Pathfinder</div>
  <div class="game-header">
    <div>
      <div class="game-title">Neural Pathfinder</div>
      <div class="game-subtitle">A* search · draw walls · watch the agent reason</div>
    </div>
    <div class="game-meta">an interactive metaphor<br>for intelligence infrastructure</div>
  </div>
  <div class="game-controls">
    <button class="game-btn active" id="btn-wall" onclick="setMode('wall')">✦ Draw Walls</button>
    <button class="game-btn" id="btn-start" onclick="setMode('start')">◉ Set Start</button>
    <button class="game-btn" id="btn-end" onclick="setMode('end')">◎ Set Goal</button>
    <button class="game-btn" onclick="runAStar()">▶ Pathfind</button>
    <button class="game-btn" onclick="clearPath()">↺ Clear Path</button>
    <button class="game-btn" onclick="resetGrid()">⊘ Reset</button>
    <button class="game-btn" onclick="genMaze()">⊞ Maze</button>
  </div>
  <div id="game-canvas-wrap">
    <canvas id="game-canvas"></canvas>
  </div>
  <div class="game-legend">
    <div class="legend-item"><div class="legend-dot" style="background:#63b3ed;"></div>open node</div>
    <div class="legend-item"><div class="legend-dot" style="background:#1a202c;border:1px solid #4a5568"></div>wall</div>
    <div class="legend-item"><div class="legend-dot" style="background:#68d391;"></div>start</div>
    <div class="legend-item"><div class="legend-dot" style="background:#9f7aea;"></div>goal</div>
    <div class="legend-item"><div class="legend-dot" style="background:rgba(99,179,237,0.2);border:1px solid #63b3ed"></div>explored</div>
    <div class="legend-item"><div class="legend-dot" style="background:#f6ad55;"></div>optimal path</div>
  </div>
  <div id="game-status">ready. draw walls, then click ▶ pathfind.</div>
</section>

<!-- TECH STACK -->
<section>
  <div class="section-label">05 · Tech Stack</div>
  <h2>Instruments</h2>
  <div class="stack-wrap">
    <span class="stack-tag">Python</span>
    <span class="stack-tag">PyTorch</span>
    <span class="stack-tag">LangChain</span>
    <span class="stack-tag">LangGraph</span>
    <span class="stack-tag">FastAPI</span>
    <span class="stack-tag">PostgreSQL</span>
    <span class="stack-tag">Redis</span>
    <span class="stack-tag">Docker</span>
    <span class="stack-tag">Kubernetes</span>
    <span class="stack-tag">Pinecone</span>
    <span class="stack-tag">OpenAI API</span>
    <span class="stack-tag">Anthropic API</span>
    <span class="stack-tag">Ray</span>
    <span class="stack-tag">Celery</span>
    <span class="stack-tag">GraphQL</span>
    <span class="stack-tag">TypeScript</span>
    <span class="stack-tag">Next.js</span>
    <span class="stack-tag">Git</span>
    <span class="stack-tag">Linux</span>
    <span class="stack-tag">Terraform</span>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="divider"></div>
  <div class="footer-quote">Code fades. Systems remain.</div>
  <div class="footer-sub">— priyanshu mishra · ai systems engineer · cognitiveops architect</div>
  <a class="github-link" href="https://github.com/priyanshumishra610">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
    github.com/priyanshumishra610
  </a>
</footer>

<script>
// ─── NEURAL CANVAS ───────────────────────────────────────────────
const nc = document.getElementById('neural-canvas');
const nctx = nc.getContext('2d');
let nW, nH, nodes = [], animId;

function initNeural() {
  nW = nc.width = nc.offsetWidth;
  nH = nc.height = nc.offsetHeight;
  nodes = [];
  const count = Math.floor((nW * nH) / 9000);
  for (let i = 0; i < count; i++) {
    nodes.push({
      x: Math.random() * nW, y: Math.random() * nH,
      vx: (Math.random() - 0.5) * 0.4, vy: (Math.random() - 0.5) * 0.4,
      r: Math.random() * 2 + 1, pulse: Math.random() * Math.PI * 2
    });
  }
}

function drawNeural(ts) {
  nctx.clearRect(0, 0, nW, nH);
  nodes.forEach(n => {
    n.x += n.vx; n.y += n.vy; n.pulse += 0.02;
    if (n.x < 0 || n.x > nW) n.vx *= -1;
    if (n.y < 0 || n.y > nH) n.vy *= -1;
  });
  const maxDist = 120;
  for (let i = 0; i < nodes.length; i++) {
    for (let j = i + 1; j < nodes.length; j++) {
      const a = nodes[i], b = nodes[j];
      const dx = a.x - b.x, dy = a.y - b.y;
      const dist = Math.sqrt(dx*dx + dy*dy);
      if (dist < maxDist) {
        const alpha = (1 - dist / maxDist) * 0.35;
        const col = dist < 60 ? `rgba(159,122,234,${alpha})` : `rgba(99,179,237,${alpha})`;
        nctx.beginPath(); nctx.moveTo(a.x, a.y); nctx.lineTo(b.x, b.y);
        nctx.strokeStyle = col; nctx.lineWidth = 0.8; nctx.stroke();
      }
    }
  }
  nodes.forEach(n => {
    const s = 0.6 + Math.sin(n.pulse) * 0.4;
    nctx.beginPath(); nctx.arc(n.x, n.y, n.r * s, 0, Math.PI * 2);
    nctx.fillStyle = `rgba(99,179,237,${0.4 + s * 0.4})`; nctx.fill();
  });
  animId = requestAnimationFrame(drawNeural);
}

initNeural();
drawNeural(0);
window.addEventListener('resize', () => { initNeural(); });

// ─── TYPED EFFECT ────────────────────────────────────────────────
const phrases = [
  'Building intelligence infrastructure...',
  'Designing systems that evolve.',
  'Memory > stateless computation.',
  'Feedback loops over rigid rules.',
  'Create. Deploy. Improve. Repeat.',
  'Strong systems endure.'
];
let pIdx = 0, cIdx = 0, deleting = false;
const typedEl = document.getElementById('typed-text');

function typeLoop() {
  const phrase = phrases[pIdx];
  if (!deleting) {
    typedEl.textContent = phrase.slice(0, cIdx++);
    if (cIdx > phrase.length) { deleting = true; setTimeout(typeLoop, 2000); return; }
    setTimeout(typeLoop, 55);
  } else {
    typedEl.textContent = phrase.slice(0, cIdx--);
    if (cIdx < 0) { deleting = false; pIdx = (pIdx + 1) % phrases.length; setTimeout(typeLoop, 400); return; }
    setTimeout(typeLoop, 28);
  }
}
typeLoop();

// ─── STAT COUNTERS ───────────────────────────────────────────────
function animCount(id, target, duration) {
  const el = document.getElementById(id);
  const start = performance.now();
  function step(now) {
    const p = Math.min((now - start) / duration, 1);
    const eased = 1 - Math.pow(1 - p, 3);
    el.textContent = Math.floor(eased * target);
    if (p < 1) requestAnimationFrame(step);
    else el.textContent = target;
  }
  requestAnimationFrame(step);
}

const observer = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      animCount('commits-count', 847, 1500);
      animCount('repos-count', 23, 1200);
      animCount('streak-count', 41, 1400);
      animCount('stars-count', 119, 1600);
      observer.disconnect();
    }
  });
});
const statsEl = document.getElementById('commits-count');
if (statsEl) observer.observe(statsEl.closest('section'));

// ─── A* GAME ─────────────────────────────────────────────────────
const gc = document.getElementById('game-canvas');
const gctx = gc.getContext('2d');
const COLS = 40, ROWS = 24;
let CELL;
let grid, startNode, endNode, mode = 'wall';
let isDrawing = false;
let drawWall = true;

function initGame() {
  const wrap = document.getElementById('game-canvas-wrap');
  const W = wrap.offsetWidth;
  CELL = Math.floor(W / COLS);
  gc.width = CELL * COLS;
  gc.height = CELL * ROWS;
  grid = [];
  for (let r = 0; r < ROWS; r++) {
    grid[r] = [];
    for (let c = 0; c < COLS; c++) grid[r][c] = { wall: false, visited: false, path: false };
  }
  startNode = { r: Math.floor(ROWS/2), c: 2 };
  endNode = { r: Math.floor(ROWS/2), c: COLS - 3 };
  drawGrid();
}

function drawGrid() {
  gctx.clearRect(0, 0, gc.width, gc.height);
  for (let r = 0; r < ROWS; r++) {
    for (let c = 0; c < COLS; c++) {
      const cell = grid[r][c];
      const x = c * CELL, y = r * CELL;
      if (cell.wall) { gctx.fillStyle = '#0d1117'; }
      else if (cell.path) { gctx.fillStyle = '#f6ad55'; }
      else if (cell.visited) { gctx.fillStyle = 'rgba(99,179,237,0.18)'; }
      else { gctx.fillStyle = '#111827'; }
      gctx.fillRect(x, y, CELL, CELL);
      gctx.strokeStyle = 'rgba(99,179,237,0.07)';
      gctx.lineWidth = 0.5;
      gctx.strokeRect(x, y, CELL, CELL);
    }
  }
  // start
  const sx = startNode.c * CELL + CELL/2, sy = startNode.r * CELL + CELL/2;
  gctx.beginPath(); gctx.arc(sx, sy, CELL/2 - 2, 0, Math.PI*2);
  gctx.fillStyle = '#68d391'; gctx.fill();
  // end
  const ex = endNode.c * CELL + CELL/2, ey = endNode.r * CELL + CELL/2;
  gctx.beginPath(); gctx.arc(ex, ey, CELL/2 - 2, 0, Math.PI*2);
  gctx.fillStyle = '#9f7aea'; gctx.fill();
}

function getCell(e) {
  const rect = gc.getBoundingClientRect();
  const x = (e.clientX || (e.touches && e.touches[0].clientX)) - rect.left;
  const y = (e.clientY || (e.touches && e.touches[0].clientY)) - rect.top;
  return { r: Math.floor(y / CELL), c: Math.floor(x / CELL) };
}

function handleCell(e) {
  const {r, c} = getCell(e);
  if (r < 0 || r >= ROWS || c < 0 || c >= COLS) return;
  if (mode === 'wall') {
    if ((r===startNode.r&&c===startNode.c)||(r===endNode.r&&c===endNode.c)) return;
    grid[r][c].wall = drawWall;
  } else if (mode === 'start') {
    startNode = {r, c}; grid[r][c].wall = false;
  } else if (mode === 'end') {
    endNode = {r, c}; grid[r][c].wall = false;
  }
  drawGrid();
}

gc.addEventListener('mousedown', e => {
  isDrawing = true;
  const {r,c} = getCell(e);
  if (r>=0&&r<ROWS&&c>=0&&c<COLS) drawWall = !grid[r][c].wall;
  handleCell(e);
});
gc.addEventListener('mousemove', e => { if (isDrawing) handleCell(e); });
gc.addEventListener('mouseup', () => isDrawing = false);
gc.addEventListener('touchstart', e => { e.preventDefault(); isDrawing = true; handleCell(e); }, {passive:false});
gc.addEventListener('touchmove', e => { e.preventDefault(); if(isDrawing) handleCell(e); }, {passive:false});
gc.addEventListener('touchend', () => isDrawing = false);

function setMode(m) {
  mode = m;
  document.querySelectorAll('.game-btn').forEach(b => b.classList.remove('active'));
  const ids = {wall:'btn-wall',start:'btn-start',end:'btn-end'};
  if (ids[m]) document.getElementById(ids[m]).classList.add('active');
}

function heuristic(a, b) { return Math.abs(a.r-b.r) + Math.abs(a.c-b.c); }

async function runAStar() {
  clearPath();
  const status = document.getElementById('game-status');
  status.textContent = 'searching...';
  const open = [];
  const gScore = {}, fScore = {}, came = {};
  const key = (r,c) => r+','+c;
  const sk = key(startNode.r, startNode.c);
  gScore[sk] = 0; fScore[sk] = heuristic(startNode, endNode);
  open.push({...startNode, f: fScore[sk]});

  let found = false;
  let steps = 0;
  while (open.length > 0) {
    open.sort((a,b) => a.f - b.f);
    const cur = open.shift();
    const ck = key(cur.r, cur.c);
    if (cur.r === endNode.r && cur.c === endNode.c) { found = true; break; }
    const neighbors = [{r:cur.r-1,c:cur.c},{r:cur.r+1,c:cur.c},{r:cur.r,c:cur.c-1},{r:cur.r,c:cur.c+1}];
    for (const nb of neighbors) {
      if (nb.r < 0||nb.r>=ROWS||nb.c<0||nb.c>=COLS) continue;
      if (grid[nb.r][nb.c].wall) continue;
      const nbk = key(nb.r, nb.c);
      const tg = (gScore[ck] || 0) + 1;
      if (tg < (gScore[nbk] ?? Infinity)) {
        came[nbk] = ck; gScore[nbk] = tg;
        fScore[nbk] = tg + heuristic(nb, endNode);
        if (!open.find(o => key(o.r,o.c)===nbk)) open.push({...nb, f: fScore[nbk]});
        if (!(nb.r===endNode.r&&nb.c===endNode.c)) {
          grid[nb.r][nb.c].visited = true;
        }
      }
    }
    steps++;
    if (steps % 8 === 0) { drawGrid(); await new Promise(r => setTimeout(r, 12)); }
  }

  if (found) {
    let ck = key(endNode.r, endNode.c);
    let len = 0;
    while (came[ck]) {
      const [r,c] = ck.split(',').map(Number);
      if (!(r===startNode.r&&c===startNode.c)&&!(r===endNode.r&&c===endNode.c)) grid[r][c].path = true;
      ck = came[ck]; len++;
      drawGrid(); await new Promise(r => setTimeout(r, 18));
    }
    status.textContent = `path found. length: ${len} nodes. explored: ${steps} cells.`;
  } else {
    status.textContent = 'no path found. the walls have won.';
    status.style.color = '#fc8181';
    setTimeout(() => status.style.color = '', 2000);
  }
  drawGrid();
}

function clearPath() {
  for (let r=0;r<ROWS;r++) for (let c=0;c<COLS;c++) { grid[r][c].visited=false; grid[r][c].path=false; }
  document.getElementById('game-status').textContent = 'path cleared.';
  drawGrid();
}

function resetGrid() {
  initGame();
  document.getElementById('game-status').textContent = 'reset. draw walls, then pathfind.';
}

function genMaze() {
  resetGrid();
  // Recursive division maze
  for (let r=0;r<ROWS;r++) for (let c=0;c<COLS;c++) {
    if (r===0||r===ROWS-1||c===0||c===COLS-1) grid[r][c].wall=true;
  }
  function divide(r1,c1,r2,c2,h) {
    if (r2-r1 < 2 || c2-c1 < 2) return;
    if (h) {
      const wr = r1+1 + Math.floor(Math.random()*(r2-r1-1));
      const pc = c1 + Math.floor(Math.random()*(c2-c1+1));
      for (let c=c1;c<=c2;c++) { if(c!==pc) grid[wr][c].wall=true; }
      divide(r1,c1,wr-1,c2,!h); divide(wr+1,c1,r2,c2,!h);
    } else {
      const wc = c1+1 + Math.floor(Math.random()*(c2-c1-1));
      const pr = r1 + Math.floor(Math.random()*(r2-r1+1));
      for (let r=r1;r<=r2;r++) { if(r!==pr) grid[r][wc].wall=true; }
      divide(r1,c1,r2,wc-1,!h); divide(r1,wc+1,r2,c2,!h);
    }
  }
  divide(1,1,ROWS-2,COLS-2,Math.random()<0.5);
  grid[startNode.r][startNode.c].wall=false;
  grid[startNode.r][startNode.c+1].wall=false;
  grid[endNode.r][endNode.c].wall=false;
  grid[endNode.r][endNode.c-1].wall=false;
  document.getElementById('game-status').textContent = 'maze generated. click ▶ pathfind!';
  drawGrid();
}

initGame();
window.addEventListener('resize', initGame);
</script>
</body>
</html>
