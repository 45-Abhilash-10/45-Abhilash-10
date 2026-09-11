<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abhilash Velpula — Data Analyst & Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #140F21;
    --panel: #1C1630;
    --panel-2: #221A3B;
    --border: #33285A;
    --lav: #B9A6E3;
    --lav-deep: #8B6FCE;
    --text: #EDE9F7;
    --text-dim: #9A8FBF;
    --accent-glow: rgba(139,111,206,0.35);
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html,body{height:100%;}
  body{
    background: radial-gradient(1200px 600px at 80% -10%, #241A45 0%, var(--bg) 55%);
    color: var(--text);
    font-family:'Inter', sans-serif;
    display:flex;
    min-height:100vh;
    line-height:1.5;
  }
  ::selection{ background: var(--lav-deep); color:#fff; }

  /* ---------- Sidebar ---------- */
  .sidebar{
    width: 240px;
    flex-shrink:0;
    background: var(--panel);
    border-right:1px solid var(--border);
    padding: 32px 20px;
    display:flex;
    flex-direction:column;
    gap: 36px;
    position: sticky;
    top:0;
    height:100vh;
  }
  .brand{ display:flex; align-items:center; gap:12px; }
  .brand .mark{
    width:42px; height:42px; border-radius:10px;
    background: linear-gradient(135deg, var(--lav), var(--lav-deep));
    display:flex; align-items:center; justify-content:center;
    font-family:'Space Grotesk', sans-serif; font-weight:700; color:#140F21; font-size:16px;
  }
  .brand .name{ font-family:'Space Grotesk', sans-serif; font-size:15px; font-weight:600; }
  .brand .role{ font-size:11.5px; color:var(--text-dim); }

  nav{ display:flex; flex-direction:column; gap:4px; }
  .nav-btn{
    all:unset;
    cursor:pointer;
    padding:10px 14px;
    border-radius:8px;
    font-size:13.5px;
    color: var(--text-dim);
    display:flex;
    align-items:center;
    gap:10px;
    transition: background .18s ease, color .18s ease, transform .18s ease;
  }
  .nav-btn:hover{ background: var(--panel-2); color: var(--text); transform: translateX(2px); }
  .nav-btn.active{ background: var(--panel-2); color: var(--lav); box-shadow: inset 2px 0 0 var(--lav); }
  .nav-btn .dot{ width:6px; height:6px; border-radius:50%; background: currentColor; opacity:.6; }

  .sidebar-foot{ margin-top:auto; display:flex; flex-direction:column; gap:10px; }
  .status-pill{
    font-size:11px; color:#C9F7D9; background: rgba(60,180,120,.12);
    border:1px solid rgba(60,180,120,.35);
    padding:6px 10px; border-radius:20px; display:flex; align-items:center; gap:6px; width:fit-content;
  }
  .status-pill .blip{ width:6px; height:6px; border-radius:50%; background:#4ADE80; box-shadow:0 0 8px #4ADE80; }
  .sidebar-links{ display:flex; gap:8px; }
  .icon-link{
    width:32px; height:32px; border-radius:8px; border:1px solid var(--border);
    display:flex; align-items:center; justify-content:center; color:var(--text-dim);
    text-decoration:none; font-size:13px; transition: all .2s ease;
  }
  .icon-link:hover{ color:var(--lav); border-color:var(--lav-deep); background:var(--panel-2); transform: translateY(-2px); }

  /* ---------- Main ---------- */
  main{ flex:1; padding: 44px 56px; max-width:1180px; }
  .view{ display:none; animation: fadein .35s ease; }
  .view.active{ display:block; }
  @keyframes fadein{ from{opacity:0; transform:translateY(6px);} to{opacity:1; transform:translateY(0);} }

  .eyebrow{ color:var(--text-dim); font-size:13px; margin-bottom:6px; }
  h1{ font-family:'Space Grotesk', sans-serif; font-size:38px; font-weight:600; letter-spacing:-.5px; }
  h2{ font-family:'Space Grotesk', sans-serif; font-size:22px; font-weight:600; margin-bottom:18px; }
  p.lede{ color: var(--text-dim); font-size:15px; max-width: 60ch; margin-top:10px; }

  /* Hero */
  .hero{ display:flex; justify-content:space-between; align-items:flex-end; gap:40px; flex-wrap:wrap; margin-bottom:34px; }
  .hero-stats{ display:flex; gap:14px; }
  .stat-card{
    background: var(--panel); border:1px solid var(--border); border-radius:12px;
    padding:14px 18px; min-width:110px; transition: border-color .2s ease, transform .2s ease, box-shadow .2s ease;
  }
  .stat-card:hover{ border-color: var(--lav-deep); transform: translateY(-3px); box-shadow:0 10px 24px var(--accent-glow); }
  .stat-card .num{ font-family:'Space Grotesk', sans-serif; font-size:22px; color:var(--lav); }
  .stat-card .label{ font-size:11.5px; color:var(--text-dim); margin-top:2px; }

  .divider{ height:1px; background: linear-gradient(90deg, var(--border), transparent); margin: 30px 0; }

  /* Overview grid */
  .grid-2{ display:grid; grid-template-columns: 1.3fr 1fr; gap:20px; }
  .card{
    background: var(--panel); border:1px solid var(--border); border-radius:14px; padding:22px;
    transition: border-color .2s ease, box-shadow .2s ease;
  }
  .card:hover{ border-color: var(--lav-deep); box-shadow: 0 12px 30px rgba(0,0,0,.25); }
  .fact-row{ display:flex; justify-content:space-between; padding:9px 0; border-bottom:1px dashed var(--border); font-size:13.5px; }
  .fact-row:last-child{ border-bottom:none; }
  .fact-row span:first-child{ color:var(--text-dim); }

  /* Skills */
  .tab-row{ display:flex; gap:8px; margin-bottom:22px; flex-wrap:wrap; }
  .tab{
    all:unset; cursor:pointer; font-size:13px; padding:8px 16px; border-radius:20px;
    border:1px solid var(--border); color: var(--text-dim); transition: all .18s ease;
  }
  .tab:hover{ color:var(--text); border-color:var(--lav-deep); }
  .tab.active{ background: var(--lav-deep); color:#fff; border-color: var(--lav-deep); }

  .skill-panel{ display:none; }
  .skill-panel.active{ display:grid; grid-template-columns: 1fr 1fr; gap: 16px 32px; }
  .skill{ }
  .skill-top{ display:flex; justify-content:space-between; font-size:13.5px; margin-bottom:6px; }
  .skill-top .pct{ color: var(--lav); font-family:'Space Grotesk', sans-serif; }
  .bar-track{ height:7px; border-radius:6px; background: var(--panel-2); overflow:hidden; }
  .bar-fill{ height:100%; border-radius:6px; background: linear-gradient(90deg, var(--lav-deep), var(--lav)); width:0%; transition: width 1s cubic-bezier(.22,.9,.3,1); }

  /* Projects */
  .proj-filter{ display:flex; gap:8px; margin-bottom:20px; flex-wrap:wrap; }
  .proj-grid{ display:grid; grid-template-columns: 1fr 1fr; gap:18px; }
  .proj-card{
    background: var(--panel); border:1px solid var(--border); border-radius:14px; padding:20px;
    cursor:pointer; transition: transform .2s ease, border-color .2s ease, box-shadow .2s ease;
    display:none;
  }
  .proj-card.show{ display:block; }
  .proj-card:hover{ transform: translateY(-4px); border-color: var(--lav-deep); box-shadow:0 14px 28px var(--accent-glow); }
  .proj-head{ display:flex; justify-content:space-between; align-items:flex-start; }
  .proj-title{ font-family:'Space Grotesk', sans-serif; font-size:16px; font-weight:600; }
  .proj-tags{ display:flex; gap:6px; flex-wrap:wrap; margin: 10px 0 12px; }
  .tag{ font-size:10.5px; color: var(--lav); background: rgba(185,166,227,.1); border:1px solid rgba(185,166,227,.25); padding:3px 9px; border-radius:20px; }
  .proj-desc{ font-size:13px; color: var(--text-dim); max-height:0; overflow:hidden; transition: max-height .3s ease, margin-top .3s ease; }
  .proj-card.open .proj-desc{ max-height:120px; margin-top:8px; }
  .proj-foot{ display:flex; justify-content:space-between; align-items:center; margin-top:14px; }
  .repo-link{ font-size:12.5px; color: var(--lav); text-decoration:none; display:flex; align-items:center; gap:5px; opacity:0; transform: translateX(-4px); transition: all .2s ease; }
  .proj-card:hover .repo-link{ opacity:1; transform: translateX(0); }
  .expand-hint{ font-size:11px; color: var(--text-dim); }
  .chev{ transition: transform .25s ease; display:inline-block; }
  .proj-card.open .chev{ transform: rotate(180deg); }

  /* Contact */
  .contact-grid{ display:grid; grid-template-columns: repeat(3,1fr); gap:16px; }
  .contact-card{
    background: var(--panel); border:1px solid var(--border); border-radius:14px; padding:22px;
    text-decoration:none; color: var(--text); display:flex; flex-direction:column; gap:10px;
    transition: transform .2s ease, border-color .2s ease, box-shadow .2s ease;
    position:relative; overflow:hidden;
  }
  .contact-card::before{
    content:""; position:absolute; inset:0; background: radial-gradient(120px 80px at 90% 0%, var(--accent-glow), transparent);
    opacity:0; transition: opacity .25s ease;
  }
  .contact-card:hover::before{ opacity:1; }
  .contact-card:hover{ transform: translateY(-4px); border-color: var(--lav-deep); box-shadow:0 14px 28px rgba(0,0,0,.3); }
  .contact-icon{ font-size:20px; }
  .contact-label{ font-size:13px; color: var(--text-dim); }
  .contact-value{ font-family:'Space Grotesk', sans-serif; font-size:14.5px; }

  .footer-note{ margin-top:40px; font-size:12px; color:var(--text-dim); text-align:center; }

  @media (max-width: 880px){
    body{ flex-direction:column; }
    .sidebar{ position:relative; height:auto; width:100%; flex-direction:row; align-items:center; overflow-x:auto; }
    nav{ flex-direction:row; }
    .sidebar-foot{ display:none; }
    main{ padding: 28px 22px; }
    .grid-2, .proj-grid, .contact-grid, .skill-panel.active{ grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<aside class="sidebar">
  <div class="brand">
    <div class="mark">AV</div>
    <div>
      <div class="name">Abhilash Velpula</div>
      <div class="role">Data Analyst</div>
    </div>
  </div>

  <nav>
    <button class="nav-btn active" data-view="overview"><span class="dot"></span>Overview</button>
    <button class="nav-btn" data-view="skills"><span class="dot"></span>Skills</button>
    <button class="nav-btn" data-view="projects"><span class="dot"></span>Projects</button>
    <button class="nav-btn" data-view="contact"><span class="dot"></span>Contact</button>
  </nav>

  <div class="sidebar-foot">
    <div class="status-pill"><span class="blip"></span>Open to internships</div>
    <div class="sidebar-links">
      <a class="icon-link" href="https://linkedin.com/in/abhilash-velpula-72444a348" title="LinkedIn" target="_blank">in</a>
      <a class="icon-link" href="mailto:abhilashvelpula826@gmail.com" title="Email">@</a>
      <a class="icon-link" href="https://github.com/45-Abhilash-10" title="GitHub" target="_blank">GH</a>
    </div>
  </div>
</aside>

<main>

  <!-- OVERVIEW -->
  <section class="view active" id="overview">
    <div class="hero">
      <div>
        <div class="eyebrow">B.Tech Information Technology · CBIT</div>
        <h1>Abhilash Velpula</h1>
        <p class="lede">Data Analyst and full-stack developer building with Python, SQL, Power BI and the MERN stack. Co-founder at SmartPlot Designs, focused on turning raw data into decisions people can act on.</p>
      </div>
      <div class="hero-stats">
        <div class="stat-card"><div class="num">5+</div><div class="label">Core Projects</div></div>
        <div class="stat-card"><div class="num">10+</div><div class="label">Tools & Frameworks</div></div>
        <div class="stat-card"><div class="num">2026</div><div class="label">Graduating</div></div>
      </div>
    </div>

    <div class="divider"></div>

    <div class="grid-2">
      <div class="card">
        <h2>Education</h2>
        <div class="fact-row"><span>Degree</span><span>B.Tech, Information Technology</span></div>
        <div class="fact-row"><span>Institute</span><span>Chaitanya Bharathi Institute of Technology</span></div>
        <div class="fact-row"><span>Focus areas</span><span>Data Analytics, Machine Learning</span></div>
        <div class="fact-row"><span>Location</span><span>Hyderabad, India</span></div>
      </div>
      <div class="card">
        <h2>Eligibility Snapshot</h2>
        <div class="fact-row"><span>Role interest</span><span>Data Analyst / DS</span></div>
        <div class="fact-row"><span>Availability</span><span>Internship &amp; Full-time</span></div>
        <div class="fact-row"><span>Notice period</span><span>Immediate</span></div>
        <div class="fact-row"><span>Relocation</span><span>Open</span></div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section class="view" id="skills">
    <div class="eyebrow">Capabilities</div>
    <h1 style="font-size:28px;">Skills</h1>
    <p class="lede" style="margin-bottom:26px;">Grouped by domain — switch tabs to filter.</p>

    <div class="tab-row">
      <button class="tab active" data-skill="data">Data & Analytics</button>
      <button class="tab" data-skill="ml">Machine Learning</button>
      <button class="tab" data-skill="web">Web Development</button>
      <button class="tab" data-skill="tools">Tools</button>
    </div>

    <div class="skill-panel active" data-panel="data">
      <div class="skill"><div class="skill-top"><span>Python (Pandas / NumPy)</span><span class="pct">90%</span></div><div class="bar-track"><div class="bar-fill" data-w="90"></div></div></div>
      <div class="skill"><div class="skill-top"><span>SQL</span><span class="pct">85%</span></div><div class="bar-track"><div class="bar-fill" data-w="85"></div></div></div>
      <div class="skill"><div class="skill-top"><span>Power BI & DAX</span><span class="pct">88%</span></div><div class="bar-track"><div class="bar-fill" data-w="88"></div></div></div>
      <div class="skill"><div class="skill-top"><span>Excel</span><span class="pct">85%</span></div><div class="bar-track"><div class="bar-fill" data-w="85"></div></div></div>
      <div class="skill"><div class="skill-top"><span>Matplotlib / Plotly</span><span class="pct">80%</span></div><div class="bar-track"><div class="bar-fill" data-w="80"></div></div></div>
    </div>

    <div class="skill-panel" data-panel="ml">
      <div class="skill"><div class="skill-top"><span>Scikit-learn</span><span class="pct">80%</span></div><div class="bar-track"><div class="bar-fill" data-w="80"></div></div></div>
      <div class="skill"><div class="skill-top"><span>TensorFlow / Keras</span><span class="pct">70%</span></div><div class="bar-track"><div class="bar-fill" data-w="70"></div></div></div>
      <div class="skill"><div class="skill-top"><span>Statistical Modeling</span><span class="pct">75%</span></div><div class="bar-track"><div class="bar-fill" data-w="75"></div></div></div>
      <div class="skill"><div class="skill-top"><span>Model Evaluation</span><span class="pct">78%</span></div><div class="bar-track"><div class="bar-fill" data-w="78"></div></div></div>
    </div>

    <div class="skill-panel" data-panel="web">
      <div class="skill"><div class="skill-top"><span>React</span><span class="pct">78%</span></div><div class="bar-track"><div class="bar-fill" data-w="78"></div></div></div>
      <div class="skill"><div class="skill-top"><span>Node.js / Express</span><span class="pct">72%</span></div><div class="bar-track"><div class="bar-fill" data-w="72"></div></div></div>
      <div class="skill"><div class="skill-top"><span>MongoDB</span><span class="pct">70%</span></div><div class="bar-track"><div class="bar-fill" data-w="70"></div></div></div>
      <div class="skill"><div class="skill-top"><span>REST APIs</span><span class="pct">75%</span></div><div class="bar-track"><div class="bar-fill" data-w="75"></div></div></div>
    </div>

    <div class="skill-panel" data-panel="tools">
      <div class="skill"><div class="skill-top"><span>Git & GitHub</span><span class="pct">85%</span></div><div class="bar-track"><div class="bar-fill" data-w="85"></div></div></div>
      <div class="skill"><div class="skill-top"><span>VS Code</span><span class="pct">90%</span></div><div class="bar-track"><div class="bar-fill" data-w="90"></div></div></div>
      <div class="skill"><div class="skill-top"><span>MySQL</span><span class="pct">80%</span></div><div class="bar-track"><div class="bar-fill" data-w="80"></div></div></div>
      <div class="skill"><div class="skill-top"><span>DSA (Arrays–Graphs–DP)</span><span class="pct">70%</span></div><div class="bar-track"><div class="bar-fill" data-w="70"></div></div></div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section class="view" id="projects">
    <div class="eyebrow">Portfolio</div>
    <h1 style="font-size:28px;">Featured Projects</h1>
    <p class="lede" style="margin-bottom:22px;">Click a card to expand. Filter by category.</p>

    <div class="proj-filter">
      <button class="tab active" data-filter="all">All</button>
      <button class="tab" data-filter="analytics">Analytics</button>
      <button class="tab" data-filter="ml">Machine Learning</button>
      <button class="tab" data-filter="web">Web Dev</button>
    </div>

    <div class="proj-grid" id="projGrid">

      <div class="proj-card show" data-cat="analytics">
        <div class="proj-head">
          <div class="proj-title">🍫 Chocolate Sales Analysis</div>
          <span class="chev">⌄</span>
        </div>
        <div class="proj-tags"><span class="tag">Power BI</span><span class="tag">Python</span><span class="tag">DAX</span></div>
        <div class="proj-desc">Interactive dashboard covering revenue, product-level performance, monthly/yearly trends, KPIs and market performance.</div>
        <div class="proj-foot">
          <span class="expand-hint">Click to expand</span>
          <a class="repo-link" href="https://github.com/45-Abhilash-10/Chocolate-Company-Sales-Analysis-" target="_blank" onclick="event.stopPropagation()">View repo →</a>
        </div>
      </div>

      <div class="proj-card show" data-cat="analytics">
        <div class="proj-head">
          <div class="proj-title">📚 EDAV Project</div>
          <span class="chev">⌄</span>
        </div>
        <div class="proj-tags"><span class="tag">Python</span><span class="tag">Pandas</span><span class="tag">Matplotlib</span></div>
        <div class="proj-desc">Exploratory analysis of online course completion and learner-related patterns through cleaning, analysis and visualization.</div>
        <div class="proj-foot">
          <span class="expand-hint">Click to expand</span>
          <a class="repo-link" href="https://github.com/45-Abhilash-10/EDAV-project" target="_blank" onclick="event.stopPropagation()">View repo →</a>
        </div>
      </div>

      <div class="proj-card show" data-cat="web">
        <div class="proj-head">
          <div class="proj-title">🌐 Full-Stack Web Projects</div>
          <span class="chev">⌄</span>
        </div>
        <div class="proj-tags"><span class="tag">React</span><span class="tag">Node.js</span><span class="tag">MongoDB</span></div>
        <div class="proj-desc">Responsive interfaces, REST APIs, backend development, database integration and authentication logic.</div>
        <div class="proj-foot">
          <span class="expand-hint">Click to expand</span>
          <a class="repo-link" href="https://github.com/45-Abhilash-10/Frontend" target="_blank" onclick="event.stopPropagation()">View repo →</a>
        </div>
      </div>

      <div class="proj-card show" data-cat="ml">
        <div class="proj-head">
          <div class="proj-title">🧠 Multi-Disease Prediction System</div>
          <span class="chev">⌄</span>
        </div>
        <div class="proj-tags"><span class="tag">Scikit-learn</span><span class="tag">Flask</span></div>
        <div class="proj-desc">Disease prediction using Decision Trees, KNN and Naive Bayes with model evaluation and Flask-based deployment.</div>
        <div class="proj-foot">
          <span class="expand-hint">Click to expand</span>
          <span class="repo-link" style="opacity:.5; pointer-events:none;">Private repo</span>
        </div>
      </div>

      <div class="proj-card show" data-cat="analytics">
        <div class="proj-head">
          <div class="proj-title">📈 Macro Indicators & NIFTY 50</div>
          <span class="chev">⌄</span>
        </div>
        <div class="proj-tags"><span class="tag">Power BI</span><span class="tag">Python</span></div>
        <div class="proj-desc">Studies the relationship between GDP, CPI, Repo Rate, Crude Oil prices and NIFTY 50 performance.</div>
        <div class="proj-foot">
          <span class="expand-hint">Click to expand</span>
          <span class="repo-link" style="opacity:.5; pointer-events:none;">Private repo</span>
        </div>
      </div>

    </div>
  </section>

  <!-- CONTACT -->
  <section class="view" id="contact">
    <div class="eyebrow">Get in touch</div>
    <h1 style="font-size:28px;">Contact</h1>
    <p class="lede" style="margin-bottom:24px;">Open to internships, placements and collaborations.</p>

    <div class="contact-grid">
      <a class="contact-card" href="mailto:abhilashvelpula826@gmail.com">
        <div class="contact-icon">✉️</div>
        <div class="contact-label">Email</div>
        <div class="contact-value">abhilashvelpula826@gmail.com</div>
      </a>
      <a class="contact-card" href="https://linkedin.com/in/abhilash-velpula-72444a348" target="_blank">
        <div class="contact-icon">💼</div>
        <div class="contact-label">LinkedIn</div>
        <div class="contact-value">abhilash-velpula</div>
      </a>
      <a class="contact-card" href="https://github.com/45-Abhilash-10" target="_blank">
        <div class="contact-icon">🖥️</div>
        <div class="contact-label">GitHub</div>
        <div class="contact-value">45-Abhilash-10</div>
      </a>
    </div>

    <div class="footer-note">Available for interviews · Immediate joining · Hyderabad, India</div>
  </section>

</main>

<script>
  // Sidebar nav
  const navBtns = document.querySelectorAll('.nav-btn');
  const views = document.querySelectorAll('.view');
  navBtns.forEach(btn => {
    btn.addEventListener('click', () => {
      navBtns.forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
      views.forEach(v => v.classList.remove('active'));
      document.getElementById(btn.dataset.view).classList.add('active');
    });
  });

  // Skill tabs
  const skillTabs = document.querySelectorAll('[data-skill]');
  const skillPanels = document.querySelectorAll('.skill-panel');
  function animateBars(panel){
    panel.querySelectorAll('.bar-fill').forEach(bar=>{
      const w = bar.dataset.w;
      bar.style.width = '0%';
      requestAnimationFrame(()=> requestAnimationFrame(()=>{ bar.style.width = w + '%'; }));
    });
  }
  skillTabs.forEach(tab => {
    tab.addEventListener('click', () => {
      skillTabs.forEach(t => t.classList.remove('active'));
      tab.classList.add('active');
      skillPanels.forEach(p => p.classList.remove('active'));
      const target = document.querySelector(`[data-panel="${tab.dataset.skill}"]`);
      target.classList.add('active');
      animateBars(target);
    });
  });
  // initial animation
  animateBars(document.querySelector('.skill-panel.active'));

  // Project filter
  const filterTabs = document.querySelectorAll('[data-filter]');
  const projCards = document.querySelectorAll('.proj-card');
  filterTabs.forEach(tab => {
    tab.addEventListener('click', () => {
      filterTabs.forEach(t => t.classList.remove('active'));
      tab.classList.add('active');
      const f = tab.dataset.filter;
      projCards.forEach(card => {
        card.classList.toggle('show', f === 'all' || card.dataset.cat === f);
      });
    });
  });

  // Project card expand
  projCards.forEach(card => {
    card.addEventListener('click', () => card.classList.toggle('open'));
  });
</script>

</body>
</html>
