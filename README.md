<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI Solutions Architect | Infrastructure · Intelligence · Innovation</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Rajdhani:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --cyan: #00f5ff;
    --magenta: #ff006e;
    --gold: #ffd700;
    --dark: #020812;
    --dark2: #040f1e;
    --panel: rgba(0,245,255,0.04);
    --border: rgba(0,245,255,0.18);
    --text: #c8e8f0;
    --dim: #5a8a99;
    --glow-cyan: 0 0 20px rgba(0,245,255,0.5), 0 0 60px rgba(0,245,255,0.2);
    --glow-mag: 0 0 20px rgba(255,0,110,0.5), 0 0 60px rgba(255,0,110,0.2);
  }
  *, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
  html { scroll-behavior:smooth; }
  body {
    background:var(--dark); color:var(--text);
    font-family:'Rajdhani',sans-serif; font-size:17px;
    line-height:1.6; overflow-x:hidden;
  }
  body::before {
    content:''; position:fixed; inset:0;
    background-image:
      linear-gradient(rgba(0,245,255,0.03) 1px,transparent 1px),
      linear-gradient(90deg,rgba(0,245,255,0.03) 1px,transparent 1px);
    background-size:60px 60px; pointer-events:none; z-index:0;
  }
  body::after {
    content:''; position:fixed; inset:0;
    background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,0.03) 2px,rgba(0,0,0,0.03) 4px);
    pointer-events:none; z-index:999;
  }

  /* NAV */
  nav {
    position:fixed; top:0; left:0; right:0; z-index:100;
    display:flex; align-items:center; justify-content:space-between;
    padding:16px 40px;
    background:rgba(2,8,18,0.88); backdrop-filter:blur(20px);
    border-bottom:1px solid var(--border);
  }
  .nav-logo { font-family:'Orbitron',monospace; font-size:13px; font-weight:900; color:var(--cyan); letter-spacing:4px; text-shadow:var(--glow-cyan); animation:flicker 9s infinite; }
  .nav-links { display:flex; gap:34px; list-style:none; }
  .nav-links a { font-family:'Share Tech Mono',monospace; font-size:11px; color:var(--dim); text-decoration:none; letter-spacing:2px; transition:color .3s; }
  .nav-links a:hover { color:var(--cyan); text-shadow:var(--glow-cyan); }
  .nav-cta { font-family:'Share Tech Mono',monospace; font-size:11px; padding:8px 20px; border:1px solid var(--cyan); color:var(--cyan); text-decoration:none; letter-spacing:2px; transition:all .3s; clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%); }
  .nav-cta:hover { background:var(--cyan); color:var(--dark); box-shadow:var(--glow-cyan); }
  .hamburger { display:none; flex-direction:column; gap:5px; cursor:pointer; padding:8px; }
  .hamburger span { width:24px; height:1px; background:var(--cyan); transition:all .3s; }
  @keyframes flicker { 0%,94%,100%{opacity:1} 95%{opacity:.6} 97%{opacity:1} 98%{opacity:.4} 99%{opacity:1} }

  /* HERO */
  #hero {
    min-height:100vh; display:flex; flex-direction:column;
    align-items:center; justify-content:center;
    position:relative; padding:120px 40px 100px;
    text-align:center; overflow:hidden; max-width:100%;
  }
  .orb { position:absolute; border-radius:50%; pointer-events:none; }
  .orb1 { width:700px; height:700px; top:50%; left:50%; transform:translate(-50%,-50%); background:radial-gradient(circle,rgba(0,245,255,0.07) 0%,transparent 70%); animation:orbpulse 6s ease-in-out infinite; }
  .orb2 { width:1100px; height:1100px; top:50%; left:50%; transform:translate(-50%,-50%); background:radial-gradient(circle,rgba(255,0,110,0.04) 0%,transparent 60%); animation:orbpulse 10s ease-in-out infinite reverse; }
  @keyframes orbpulse { 0%,100%{transform:translate(-50%,-50%) scale(1);opacity:1} 50%{transform:translate(-50%,-50%) scale(1.08);opacity:.6} }

  .eyebrow { font-family:'Share Tech Mono',monospace; font-size:11px; color:var(--magenta); letter-spacing:5px; margin-bottom:24px; opacity:0; animation:fadeUp .8s .3s forwards; }
  .hero-title { font-family:'Orbitron',monospace; font-size:clamp(38px,7vw,96px); font-weight:900; line-height:1; margin-bottom:16px; opacity:0; animation:fadeUp .8s .5s forwards; }
  .hero-title .t1 { color:#fff; display:block; }
  .hero-title .t2 { display:block; background:linear-gradient(90deg,var(--cyan),var(--magenta)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }
  .hero-sub { font-size:18px; color:var(--dim); max-width:640px; margin:24px auto 48px; font-weight:300; letter-spacing:1px; opacity:0; animation:fadeUp .8s .7s forwards; }

  .hero-badges { display:flex; flex-wrap:wrap; gap:12px; justify-content:center; margin-bottom:56px; opacity:0; animation:fadeUp .8s .9s forwards; }
  .badge { font-family:'Share Tech Mono',monospace; font-size:10px; letter-spacing:2px; padding:6px 16px; border:1px solid; clip-path:polygon(6px 0%,100% 0%,calc(100% - 6px) 100%,0% 100%); }
  .bc { border-color:var(--cyan); color:var(--cyan); }
  .bm { border-color:var(--magenta); color:var(--magenta); }
  .bg { border-color:var(--gold); color:var(--gold); }

  .hero-btns { display:flex; gap:20px; justify-content:center; flex-wrap:wrap; opacity:0; animation:fadeUp .8s 1.1s forwards; }

  .btn { display:inline-block; font-family:'Orbitron',monospace; font-size:13px; font-weight:700; letter-spacing:3px; padding:18px 48px; text-decoration:none; position:relative; overflow:hidden; transition:all .4s; clip-path:polygon(12px 0%,100% 0%,calc(100% - 12px) 100%,0% 100%); }
  .btn::before { content:''; position:absolute; inset:0; transform:scaleX(0); transform-origin:left; transition:transform .4s; z-index:-1; }
  .btn-c { border:1px solid var(--cyan); color:var(--cyan); }
  .btn-c::before { background:var(--cyan); }
  .btn-c:hover { color:var(--dark); box-shadow:var(--glow-cyan); }
  .btn-c:hover::before { transform:scaleX(1); }
  .btn-m { border:1px solid var(--magenta); color:var(--magenta); }
  .btn-m::before { background:var(--magenta); }
  .btn-m:hover { color:var(--dark); box-shadow:var(--glow-mag); }
  .btn-m:hover::before { transform:scaleX(1); }

  .scroll-indicator { position:absolute; bottom:40px; left:50%; transform:translateX(-50%); display:flex; flex-direction:column; align-items:center; gap:8px; opacity:0; animation:fadeUp .8s 1.4s forwards; }
  .scroll-line { width:1px; height:56px; background:linear-gradient(var(--cyan),transparent); animation:sblink 2s infinite; }
  @keyframes sblink { 0%,100%{opacity:1} 50%{opacity:.2} }
  .scroll-txt { font-family:'Share Tech Mono',monospace; font-size:9px; color:var(--dim); letter-spacing:3px; writing-mode:vertical-rl; }
  @keyframes fadeUp { from{opacity:0;transform:translateY(30px)} to{opacity:1;transform:translateY(0)} }

  /* STAT ROW */
  .stat-row { display:grid; grid-template-columns:repeat(auto-fit,minmax(180px,1fr)); gap:2px; margin-bottom:80px; }
  .stat-item { border:1px solid var(--border); padding:32px 28px; background:var(--panel); text-align:center; }
  .stat-num { font-family:'Orbitron',monospace; font-size:clamp(28px,5vw,48px); font-weight:900; background:linear-gradient(90deg,var(--cyan),var(--magenta)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; display:block; line-height:1; margin-bottom:8px; }
  .stat-label { font-family:'Share Tech Mono',monospace; font-size:10px; color:var(--dim); letter-spacing:2px; }

  /* SHARED */
  section { position:relative; z-index:1; padding:100px 40px; max-width:1200px; margin:0 auto; }
  .sec-label { font-family:'Share Tech Mono',monospace; font-size:10px; letter-spacing:5px; color:var(--magenta); margin-bottom:12px; display:flex; align-items:center; gap:12px; }
  .sec-label::before { content:'//'; color:var(--cyan); }
  .sec-title { font-family:'Orbitron',monospace; font-size:clamp(24px,4vw,44px); font-weight:700; color:#fff; margin-bottom:60px; line-height:1.2; }
  .sec-title span { background:linear-gradient(90deg,var(--cyan),#00b8c8); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }

  .cdiv { display:flex; align-items:center; gap:16px; margin:0 40px; height:1px; }
  .cdiv::before,.cdiv::after { content:''; flex:1; height:1px; }
  .cdiv::before { background:linear-gradient(90deg,transparent,var(--border)); }
  .cdiv::after  { background:linear-gradient(270deg,transparent,var(--border)); }
  .cdiv-lbl { font-family:'Share Tech Mono',monospace; font-size:9px; color:var(--dim); letter-spacing:3px; white-space:nowrap; }

  /* EXPERTISE */
  .exp-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(280px,1fr)); gap:2px; }
  .exp-card { background:var(--panel); border:1px solid var(--border); padding:36px 32px; position:relative; overflow:hidden; transition:all .4s; cursor:default; }
  .exp-card::before { content:''; position:absolute; top:0; left:0; right:0; height:2px; background:linear-gradient(90deg,transparent,var(--cyan),transparent); opacity:0; transition:opacity .4s; }
  .exp-card:hover { background:rgba(0,245,255,0.07); border-color:rgba(0,245,255,.4); transform:translateY(-4px); }
  .exp-card:hover::before { opacity:1; }
  .exp-n { position:absolute; top:20px; right:24px; font-family:'Share Tech Mono',monospace; font-size:11px; color:rgba(0,245,255,.15); }
  .exp-icon { font-size:32px; margin-bottom:20px; display:block; }
  .exp-title { font-family:'Orbitron',monospace; font-size:13px; font-weight:700; color:var(--cyan); letter-spacing:2px; margin-bottom:12px; }
  .exp-desc { font-size:15px; color:var(--dim); line-height:1.7; font-weight:300; }

  /* CERTS */
  .cert-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(220px,1fr)); gap:20px; }
  .cert-card { border:1px solid var(--border); padding:28px 24px; background:var(--panel); display:flex; flex-direction:column; gap:10px; clip-path:polygon(0 0,calc(100% - 20px) 0,100% 20px,100% 100%,0 100%); position:relative; transition:all .3s; }
  .cert-card:hover { border-color:var(--gold); box-shadow:0 0 30px rgba(255,215,0,.1); }
  .cert-card::after { content:''; position:absolute; top:0; right:0; width:20px; height:20px; border-bottom:1px solid var(--border); border-left:1px solid var(--border); clip-path:polygon(0 0,100% 100%,0 100%); background:var(--dark2); }
  .cert-name { font-family:'Orbitron',monospace; font-size:12px; font-weight:700; color:var(--gold); letter-spacing:1px; }
  .cert-body { font-family:'Share Tech Mono',monospace; font-size:11px; color:var(--dim); letter-spacing:1px; }
  .cert-issuer { font-family:'Share Tech Mono',monospace; font-size:10px; color:var(--cyan); }
  .cert-check { font-size:18px; margin-top:8px; }

  /* VENDORS */
  .vendor-intro { font-size:16px; color:var(--dim); max-width:700px; margin-bottom:60px; font-weight:300; line-height:1.8; }
  .vendor-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(160px,1fr)); gap:16px; }
  .vc { border:1px solid var(--border); padding:24px 20px; text-align:center; background:var(--panel); transition:all .3s; cursor:default; display:flex; flex-direction:column; align-items:center; gap:12px; }
  .vc:hover { border-color:rgba(0,245,255,.5); background:rgba(0,245,255,.07); box-shadow:var(--glow-cyan); }
  .vn { font-family:'Orbitron',monospace; font-size:13px; font-weight:700; letter-spacing:1px; }
  .vs { font-family:'Share Tech Mono',monospace; font-size:9px; color:var(--dim); letter-spacing:1px; line-height:1.6; }
  .nvidia{color:#76b900} .cisco{color:#049fd9} .dell{color:#007db8} .hpe{color:#01a982}
  .sm{color:#e5792a} .netapp{color:#0065a0} .vast{color:#e64082} .vertiv{color:#c8102e}
  .vmware{color:#607d8b} .redhat{color:#e00} .k8s{color:#326ce5} .runai{color:#7c3aed}

  /* AI CONCEPTS */
  .concepts-wrap { display:grid; grid-template-columns:1fr 1fr; gap:60px; align-items:start; }
  .concept-list { display:flex; flex-direction:column; gap:2px; }
  .ci { border:1px solid var(--border); padding:20px 24px; background:var(--panel); cursor:pointer; transition:all .3s; display:flex; justify-content:space-between; align-items:center; }
  .ci:hover,.ci.active { border-color:var(--cyan); background:rgba(0,245,255,.06); }
  .ci-title { font-family:'Orbitron',monospace; font-size:12px; font-weight:700; color:#fff; letter-spacing:1px; }
  .ci-arrow { color:var(--cyan); font-size:18px; transition:transform .3s; }
  .ci.active .ci-arrow { transform:rotate(90deg); }
  .cp { border:1px solid var(--border); padding:40px; background:var(--panel); position:sticky; top:100px; }
  .cp h3 { font-family:'Orbitron',monospace; font-size:15px; color:var(--cyan); margin-bottom:20px; letter-spacing:2px; }
  .cp p { font-size:15px; color:var(--dim); line-height:1.9; font-weight:300; }
  .ctag-row { display:flex; flex-wrap:wrap; gap:8px; margin-top:24px; }
  .ctag { font-family:'Share Tech Mono',monospace; font-size:9px; padding:4px 12px; border:1px solid rgba(0,245,255,.3); color:var(--cyan); letter-spacing:1px; clip-path:polygon(4px 0%,100% 0%,calc(100% - 4px) 100%,0% 100%); }

  /* AGENTIC */
  .ag-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(260px,1fr)); gap:20px; }
  .ag { padding:36px 28px; border:1px solid; position:relative; overflow:hidden; transition:transform .3s; }
  .ag:hover { transform:translateY(-6px); }
  .ag::after { content:''; position:absolute; bottom:0; right:0; width:60px; height:60px; background:radial-gradient(circle at bottom right,var(--ac),transparent); opacity:.2; }
  .ag.a { border-color:rgba(0,245,255,.3); --ac:#00f5ff; background:rgba(0,245,255,.03); }
  .ag.b { border-color:rgba(255,0,110,.3); --ac:#ff006e; background:rgba(255,0,110,.03); }
  .ag.c { border-color:rgba(255,215,0,.3);  --ac:#ffd700; background:rgba(255,215,0,.03); }
  .ag-num { font-family:'Orbitron',monospace; font-size:48px; font-weight:900; opacity:.07; position:absolute; top:10px; right:16px; color:#fff; }
  .ag-title { font-family:'Orbitron',monospace; font-size:13px; font-weight:700; margin-bottom:16px; letter-spacing:2px; }
  .ag.a .ag-title{color:var(--cyan)} .ag.b .ag-title{color:var(--magenta)} .ag.c .ag-title{color:var(--gold)}
  .ag-desc { font-size:14px; color:var(--dim); line-height:1.8; font-weight:300; }

  /* SKILLS */
  .skills-wrap { display:grid; grid-template-columns:1fr 1fr; gap:60px; align-items:start; }
  .skill-group-label { font-family:'Share Tech Mono',monospace; font-size:10px; letter-spacing:4px; color:var(--cyan); margin-bottom:28px; }
  .skill-row { margin-bottom:20px; }
  .skill-lbl { display:flex; justify-content:space-between; font-family:'Rajdhani',sans-serif; font-size:13px; font-weight:600; color:var(--text); letter-spacing:1px; margin-bottom:8px; }
  .skill-lbl span { color:var(--dim); font-size:11px; }
  .skill-track { height:4px; background:rgba(255,255,255,.05); border-radius:2px; overflow:hidden; }
  .skill-fill { height:100%; background:linear-gradient(90deg,var(--cyan),var(--magenta)); border-radius:2px; transform-origin:left; animation:barGrow 1.5s cubic-bezier(.4,0,.2,1) forwards; transform:scaleX(0); }
  @keyframes barGrow { to{transform:scaleX(1)} }

  /* TIMELINE */
  .timeline { position:relative; padding-left:40px; }
  .timeline::before { content:''; position:absolute; left:0; top:0; bottom:0; width:1px; background:linear-gradient(var(--cyan),var(--magenta),transparent); }
  .tl { position:relative; margin-bottom:40px; padding:28px 32px; border:1px solid var(--border); background:var(--panel); transition:all .3s; }
  .tl:hover { border-color:rgba(0,245,255,.4); background:rgba(0,245,255,.05); }
  .tl-dot { position:absolute; left:-47px; top:28px; width:14px; height:14px; border:2px solid var(--cyan); background:var(--dark); border-radius:50%; box-shadow:var(--glow-cyan); }
  .tl-title { font-family:'Orbitron',monospace; font-size:13px; font-weight:700; color:var(--cyan); letter-spacing:2px; margin-bottom:10px; }
  .tl-desc { font-size:14px; color:var(--dim); line-height:1.8; font-weight:300; }
  .tl-tags { display:flex; flex-wrap:wrap; gap:6px; margin-top:14px; }
  .tl-tag { font-family:'Share Tech Mono',monospace; font-size:9px; padding:3px 10px; border:1px solid rgba(255,0,110,.3); color:var(--magenta); letter-spacing:1px; }

  /* CONTACT */
  .contact-wrap { text-align:center; padding:120px 40px; position:relative; overflow:hidden; }
  .contact-wrap::before { content:''; position:absolute; inset:0; background:radial-gradient(ellipse at center,rgba(0,245,255,.05) 0%,transparent 70%); pointer-events:none; }
  .contact-title { font-family:'Orbitron',monospace; font-size:clamp(28px,5vw,64px); font-weight:900; color:#fff; line-height:1.1; margin-bottom:24px; }
  .contact-title span { background:linear-gradient(90deg,var(--cyan),var(--magenta)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }
  .contact-sub { font-size:16px; color:var(--dim); margin-bottom:56px; font-weight:300; letter-spacing:1px; }

  /* FOOTER */
  footer { border-top:1px solid var(--border); padding:40px; display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:16px; position:relative; z-index:1; }
  .footer-logo { font-family:'Orbitron',monospace; font-size:11px; font-weight:900; color:var(--cyan); letter-spacing:4px; }
  .footer-copy { font-family:'Share Tech Mono',monospace; font-size:10px; color:var(--dim); letter-spacing:2px; }

  /* PARTICLES */
  .particle { position:fixed; width:2px; height:2px; border-radius:50%; pointer-events:none; z-index:0; animation:floatUp linear infinite; opacity:0; }
  @keyframes floatUp { 0%{transform:translateY(100vh);opacity:0} 10%{opacity:.5} 90%{opacity:.2} 100%{transform:translateY(-100px) translateX(30px);opacity:0} }

  /* REVEAL */
  .reveal { opacity:0; transform:translateY(40px); transition:opacity .8s ease,transform .8s ease; }
  .reveal.in { opacity:1; transform:translateY(0); }

  /* RESPONSIVE */
  @media(max-width:900px){
    .concepts-wrap { grid-template-columns:1fr; }
    .cp { display:none; }
    .skills-wrap { grid-template-columns:1fr; }
  }
  @media(max-width:768px){
    nav { padding:16px 24px; }
    .nav-links { display:none; }
    .nav-links.open { display:flex; flex-direction:column; position:absolute; top:60px; left:0; right:0; background:rgba(2,8,18,.97); padding:24px; border-bottom:1px solid var(--border); }
    .hamburger { display:flex; }
    .nav-cta { display:none; }
    section { padding:70px 24px; }
    .cdiv { margin:0 24px; }
    footer { flex-direction:column; text-align:center; }
    .contact-wrap { padding:80px 24px; }
    #hero { padding:100px 24px 80px; }
  }
</style>
</head>
<body>

<div id="particles"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">AI.ARCHITECT</div>
  <ul class="nav-links" id="navlinks">
    <li><a href="#expertise">EXPERTISE</a></li>
    <li><a href="#certs">CERTS</a></li>
    <li><a href="#vendors">VENDORS</a></li>
    <li><a href="#ai-concepts">AI CONCEPTS</a></li>
    <li><a href="#agentic">AGENTIC</a></li>
    <li><a href="#skills">SKILLS</a></li>
    <li><a href="#contact">CONTACT</a></li>
  </ul>
  <a href="https://www.linkedin.com/in/christianniz" target="_blank" class="nav-cta">LINKEDIN</a>
  <div class="hamburger" id="hbg"><span></span><span></span><span></span></div>
</nav>

<!-- HERO -->
<div id="hero">
  <div class="orb orb1"></div>
  <div class="orb orb2"></div>
  <div class="eyebrow">// AI INFRASTRUCTURE · HARDWARE · CLOUD NATIVE</div>
  <h1 class="hero-title">
    <span class="t1">AI SOLUTIONS</span>
    <span class="t2">ARCHITECT</span>
  </h1>
  <p class="hero-sub">From bare-metal silicon to containerized intelligence — architecting the infrastructure that powers tomorrow's AI.</p>
  <div class="hero-badges">
    <span class="badge bc">CKA CERTIFIED</span>
    <span class="badge bg">NETWORK+</span>
    <span class="badge bm">VMware VCP-DC</span>
    <span class="badge bc">NVIDIA BCM</span>
    <span class="badge bg">HPe PRIVATE AI</span>
    <span class="badge bm">CISCO SECURE AI FACTORY</span>
    <span class="badge bc">OPENSHIFT</span>
    <span class="badge bg">RUN:AI</span>
  </div>
  <div class="hero-btns">
    <a href="#contact" class="btn btn-c">GET IN TOUCH</a>
    <a href="https://www.linkedin.com/in/christianniz" target="_blank" class="btn btn-m">LINKEDIN PROFILE</a>
  </div>
  <div class="scroll-indicator">
    <div class="scroll-line"></div>
    <span class="scroll-txt">SCROLL</span>
  </div>
</div>

<!-- STAT ROW -->
<div style="position:relative;z-index:1;max-width:1200px;margin:0 auto;padding:0 40px;" class="reveal">
  <div class="stat-row">
    <div class="stat-item">
      <span class="stat-num">10+</span>
      <span class="stat-label">VENDOR ECOSYSTEMS</span>
    </div>
    <div class="stat-item">
      <span class="stat-num">AI</span>
      <span class="stat-label">DATA CENTERS DEPLOYED</span>
    </div>
    <div class="stat-item">
      <span class="stat-num">FULL</span>
      <span class="stat-label">STACK COVERAGE</span>
    </div>
    <div class="stat-item">
      <span class="stat-num">∞</span>
      <span class="stat-label">STACK DEPTH</span>
    </div>
  </div>
</div>

<div class="cdiv"><span class="cdiv-lbl">CORE_EXPERTISE</span></div>

<!-- EXPERTISE -->
<section id="expertise" class="reveal">
  <div class="sec-label">SPECIALIZATIONS</div>
  <h2 class="sec-title">Built for the <span>AI Era</span></h2>
  <div class="exp-grid">
    <div class="exp-card"><span class="exp-n">01</span><span class="exp-icon">⬡</span><div class="exp-title">AI DATA CENTER DEPLOYMENT</div><p class="exp-desc">End-to-end architecture and deployment of AI data centers. From rack design and power planning to GPU cluster commissioning, I build the physical foundation that AI runs on.</p></div>
    <div class="exp-card"><span class="exp-n">02</span><span class="exp-icon">◈</span><div class="exp-title">LIQUID COOLING SOLUTIONS</div><p class="exp-desc">Certified in Vertiv liquid cooling infrastructure. Designing and deploying direct liquid cooling for high-density GPU environments where air simply isn't enough.</p></div>
    <div class="exp-card"><span class="exp-n">03</span><span class="exp-icon">◎</span><div class="exp-title">KUBERNETES & CONTAINERS</div><p class="exp-desc">CKA-certified administrator deploying containerized AI workloads at scale. OpenShift, Run:AI, and native Kubernetes across bare-metal and hybrid environments.</p></div>
    <div class="exp-card"><span class="exp-n">04</span><span class="exp-icon">⬢</span><div class="exp-title">NVIDIA AI INFRASTRUCTURE</div><p class="exp-desc">Deep expertise in NVIDIA Base Command Manager, DGX systems, networking fabric, and GPU cluster management for enterprise AI training and inference workloads.</p></div>
    <div class="exp-card"><span class="exp-n">05</span><span class="exp-icon">◇</span><div class="exp-title">NETWORKING & SECURITY</div><p class="exp-desc">Network+ certified with hands-on experience in AI fabric networking. One of a select few engineers to deploy the Cisco Secure AI Factory — securing AI infrastructure at the network layer.</p></div>
    <div class="exp-card"><span class="exp-n">06</span><span class="exp-icon">⬟</span><div class="exp-title">PRIVATE AI PLATFORMS</div><p class="exp-desc">HPe Private Cloud AI, Run:AI workload orchestration, and VMware VCP-certified virtualization — delivering sovereign, on-premises AI that keeps data in your control.</p></div>
  </div>
</section>

<div class="cdiv"><span class="cdiv-lbl">CERTIFICATIONS</span></div>

<!-- CERTIFICATIONS -->
<section id="certs" class="reveal">
  <div class="sec-label">CREDENTIALS</div>
  <h2 class="sec-title">Certified <span>Stack</span></h2>
  <div class="cert-grid">
    <div class="cert-card"><div class="cert-name">CKA</div><div class="cert-body">Certified Kubernetes Administrator</div><div class="cert-issuer">CNCF</div><div class="cert-check">✦</div></div>
    <div class="cert-card"><div class="cert-name">NETWORK+</div><div class="cert-body">CompTIA Network+ Certification</div><div class="cert-issuer">CompTIA</div><div class="cert-check">✦</div></div>
    <div class="cert-card"><div class="cert-name">VCP-DCV</div><div class="cert-body">VMware Certified Professional — Data Center Virtualization</div><div class="cert-issuer">Broadcom / VMware</div><div class="cert-check">✦</div></div>
    <div class="cert-card"><div class="cert-name">CISCO SECURE AI</div><div class="cert-body">Cisco Secure AI Factory — Select Deployment Engineer</div><div class="cert-issuer">Cisco</div><div class="cert-check">✦</div></div>
    <div class="cert-card"><div class="cert-name">NVIDIA BCM</div><div class="cert-body">NVIDIA Base Command Manager Infrastructure</div><div class="cert-issuer">NVIDIA</div><div class="cert-check">✦</div></div>
    <div class="cert-card"><div class="cert-name">HPe PRIVATE AI</div><div class="cert-body">HPe Private Cloud AI Deployment Specialist</div><div class="cert-issuer">Hewlett Packard Enterprise</div><div class="cert-check">✦</div></div>
  </div>
</section>

<div class="cdiv"><span class="cdiv-lbl">VENDOR_ECOSYSTEM</span></div>

<!-- VENDORS -->
<section id="vendors" class="reveal">
  <div class="sec-label">HARDWARE & SOFTWARE ECOSYSTEM</div>
  <h2 class="sec-title">Vendor <span>Alliance</span></h2>
  <p class="vendor-intro">Hands-on deployment expertise across the full AI infrastructure stack — from compute silicon and high-density storage to hyperconverged networking and enterprise software platforms.</p>
  <div class="vendor-grid">
    <div class="vc"><div class="vn nvidia">◈ NVIDIA</div><div class="vs">DGX · H100 · BCM<br>GPU CLUSTERS · NVLink<br>Networking Fabric</div></div>
    <div class="vc"><div class="vn cisco">◈ CISCO</div><div class="vs">Secure AI Factory<br>UCS Compute<br>AI Fabric Networking</div></div>
    <div class="vc"><div class="vn dell">◈ DELL</div><div class="vs">PowerEdge AI<br>PowerScale Storage<br>VxRail HCI</div></div>
    <div class="vc"><div class="vn hpe">◈ HPe</div><div class="vs">Private Cloud AI<br>ProLiant DL Servers<br>Alletra Storage</div></div>
    <div class="vc"><div class="vn sm">◈ SUPERMICRO</div><div class="vs">AI Servers<br>GPU Optimized<br>Liquid Cooled Systems</div></div>
    <div class="vc"><div class="vn netapp">◈ NetApp</div><div class="vs">ONTAP AI<br>StorageGRID<br>AIPod Architecture</div></div>
    <div class="vc"><div class="vn vast">◈ VAST DATA</div><div class="vs">Universal Storage<br>AI Data Platform<br>NVMe-oF</div></div>
    <div class="vc"><div class="vn vertiv">◈ VERTIV</div><div class="vs">Liquid Cooling<br>CDU Systems<br>Power &amp; Thermal</div></div>
    <div class="vc"><div class="vn vmware">◈ VMware</div><div class="vs">vSphere · vSAN<br>NSX Networking<br>VCP-DCV Certified</div></div>
    <div class="vc"><div class="vn redhat">◈ RED HAT</div><div class="vs">OpenShift Platform<br>RHOAI · Operators<br>Enterprise Kubernetes</div></div>
    <div class="vc"><div class="vn k8s">◈ KUBERNETES</div><div class="vs">CKA Certified<br>Bare-Metal Clusters<br>GPU Operator</div></div>
    <div class="vc"><div class="vn runai">◈ RUN:AI</div><div class="vs">GPU Orchestration<br>Workload Scheduling<br>Resource Pooling</div></div>
  </div>
</section>

<div class="cdiv"><span class="cdiv-lbl">AI_KNOWLEDGE</span></div>

<!-- AI CONCEPTS -->
<section id="ai-concepts" class="reveal">
  <div class="sec-label">TECHNOLOGY LANDSCAPE</div>
  <h2 class="sec-title">Core AI <span>Concepts</span></h2>
  <div class="concepts-wrap">
    <div class="concept-list" id="clist">
      <div class="ci active" data-key="llm"><span class="ci-title">LARGE LANGUAGE MODELS</span><span class="ci-arrow">›</span></div>
      <div class="ci" data-key="inference"><span class="ci-title">INFERENCE OPTIMIZATION</span><span class="ci-arrow">›</span></div>
      <div class="ci" data-key="training"><span class="ci-title">DISTRIBUTED TRAINING</span><span class="ci-arrow">›</span></div>
      <div class="ci" data-key="rag"><span class="ci-title">RETRIEVAL AUGMENTED GEN</span><span class="ci-arrow">›</span></div>
      <div class="ci" data-key="mlops"><span class="ci-title">MLOps & AI PIPELINES</span><span class="ci-arrow">›</span></div>
      <div class="ci" data-key="fabric"><span class="ci-title">AI NETWORKING FABRIC</span><span class="ci-arrow">›</span></div>
      <div class="ci" data-key="sovereign"><span class="ci-title">SOVEREIGN AI</span><span class="ci-arrow">›</span></div>
    </div>
    <div class="cp" id="cpanel">
      <h3 id="cp-title">LARGE LANGUAGE MODELS</h3>
      <p id="cp-body">Foundation models trained on massive datasets, capable of understanding and generating human language. The infrastructure behind LLMs — from H100 GPU clusters to high-throughput InfiniBand networking — is where my expertise directly enables their deployment at scale.</p>
      <div class="ctag-row" id="cp-tags">
        <span class="ctag">TRANSFORMER</span><span class="ctag">GPU CLUSTER</span><span class="ctag">TENSOR PARALLEL</span><span class="ctag">KV CACHE</span>
      </div>
    </div>
  </div>
</section>

<div class="cdiv"><span class="cdiv-lbl">AGENTIC_AI</span></div>

<!-- AGENTIC -->
<section id="agentic" class="reveal" style="max-width:100%;background:linear-gradient(180deg,transparent,rgba(255,0,110,.04),transparent);">
  <div style="max-width:1200px;margin:0 auto;">
    <div class="sec-label">THE NEXT FRONTIER</div>
    <h2 class="sec-title">Agentic <span>AI Systems</span></h2>
    <p style="font-size:clamp(14px,2vw,18px);color:var(--dim);max-width:800px;line-height:1.9;font-weight:300;margin-bottom:60px;">Agentic AI represents the shift from reactive models to autonomous systems that plan, reason, and act — orchestrating tools, APIs, and sub-agents to complete complex, multi-step objectives. The infrastructure to run agentic workloads demands low-latency, high-throughput compute with intelligent orchestration layers. This is where the physical and digital stack converge.</p>
    <div class="ag-grid">
      <div class="ag a"><span class="ag-num">01</span><div class="ag-title">AUTONOMOUS AGENTS</div><p class="ag-desc">AI systems that perceive their environment, form goals, and execute multi-step plans without continuous human input. Requires robust inference infrastructure with deterministic SLAs.</p></div>
      <div class="ag b"><span class="ag-num">02</span><div class="ag-title">MULTI-AGENT ORCHESTRATION</div><p class="ag-desc">Networks of specialized agents collaborating in real-time — supervisor agents routing tasks to workers, with shared memory and tool access. Demands containerized microservice architectures on GPU-accelerated Kubernetes.</p></div>
      <div class="ag c"><span class="ag-num">03</span><div class="ag-title">TOOL-USE & FUNCTION CALLING</div><p class="ag-desc">Agents equipped with APIs, search, code execution, and external system access. The secure AI factory model — with Cisco zero-trust networking — ensures agents can act safely within enterprise boundaries.</p></div>
      <div class="ag a"><span class="ag-num">04</span><div class="ag-title">MEMORY ARCHITECTURES</div><p class="ag-desc">Short and long-term memory systems powering persistent agent state. Vector databases, RAG pipelines, and high-speed NVMe storage like VAST Data provide the retrieval backbone.</p></div>
      <div class="ag b"><span class="ag-num">05</span><div class="ag-title">INFERENCE PIPELINES</div><p class="ag-desc">Low-latency inference at the core of every agentic loop. Run:AI GPU scheduling, vLLM serving, and NVIDIA Triton ensure agents respond in milliseconds under heavy concurrent load.</p></div>
      <div class="ag c"><span class="ag-num">06</span><div class="ag-title">HUMAN-IN-THE-LOOP</div><p class="ag-desc">Agentic systems designed with control checkpoints, audit trails, and override mechanisms — critical for enterprise safety. Architectural decisions that make AI explainable and controllable from day one.</p></div>
    </div>
  </div>
</section>

<div class="cdiv"><span class="cdiv-lbl">DEPLOYMENT_STACK</span></div>

<!-- SKILLS -->
<section id="skills" class="reveal">
  <div class="sec-label">FULL STACK DEPLOYMENT</div>
  <h2 class="sec-title">From Silicon to <span>Inference</span></h2>
  <div class="skills-wrap">
    <div>
      <div class="skill-group-label">// INFRASTRUCTURE LAYERS</div>
      <div class="skill-row"><div class="skill-lbl">AI Hardware &amp; Compute <span>Expert</span></div><div class="skill-track"><div class="skill-fill" style="width:97%"></div></div></div>
      <div class="skill-row"><div class="skill-lbl">Data Center Networking <span>Expert</span></div><div class="skill-track"><div class="skill-fill" style="width:93%"></div></div></div>
      <div class="skill-row"><div class="skill-lbl">Kubernetes / OpenShift <span>CKA</span></div><div class="skill-track"><div class="skill-fill" style="width:95%"></div></div></div>
      <div class="skill-row"><div class="skill-lbl">NVIDIA BCM / GPU Ops <span>Specialist</span></div><div class="skill-track"><div class="skill-fill" style="width:92%"></div></div></div>
      <div class="skill-row"><div class="skill-lbl">Liquid Cooling (Vertiv) <span>Certified</span></div><div class="skill-track"><div class="skill-fill" style="width:89%"></div></div></div>
      <div class="skill-row"><div class="skill-lbl">VMware vSphere / vSAN <span>VCP-DCV</span></div><div class="skill-track"><div class="skill-fill" style="width:90%"></div></div></div>
    </div>
    <div class="timeline">
      <div class="tl"><div class="tl-dot"></div><div class="tl-title">LAYER 0 — PHYSICAL</div><p class="tl-desc">Rack design, power distribution, liquid cooling loops, structured cabling. The atoms before the bits.</p><div class="tl-tags"><span class="tl-tag">VERTIV CDU</span><span class="tl-tag">SUPERMICRO</span><span class="tl-tag">DELL</span><span class="tl-tag">HPe</span></div></div>
      <div class="tl"><div class="tl-dot"></div><div class="tl-title">LAYER 1 — COMPUTE & STORAGE</div><p class="tl-desc">GPU cluster provisioning, NVMe storage fabric, RAID config, DGX OS deployment, NetApp &amp; VAST integration.</p><div class="tl-tags"><span class="tl-tag">NVIDIA DGX</span><span class="tl-tag">NETAPP</span><span class="tl-tag">VAST</span></div></div>
      <div class="tl"><div class="tl-dot"></div><div class="tl-title">LAYER 2 — NETWORKING</div><p class="tl-desc">InfiniBand &amp; RoCE fabric, Cisco AI networking, zero-trust Secure AI Factory perimeter, east-west GPU traffic optimization.</p><div class="tl-tags"><span class="tl-tag">CISCO</span><span class="tl-tag">INFINIBAND</span><span class="tl-tag">ROCE</span></div></div>
      <div class="tl"><div class="tl-dot"></div><div class="tl-title">LAYER 3 — ORCHESTRATION</div><p class="tl-desc">Kubernetes cluster standup, OpenShift operators, Run:AI scheduler, NVIDIA GPU Operator, namespace isolation, RBAC.</p><div class="tl-tags"><span class="tl-tag">OPENSHIFT</span><span class="tl-tag">RUN:AI</span><span class="tl-tag">CKA</span></div></div>
      <div class="tl"><div class="tl-dot" style="border-color:var(--magenta);box-shadow:var(--glow-mag);"></div><div class="tl-title" style="color:var(--magenta);">LAYER 4 — AI WORKLOADS</div><p class="tl-desc">Model deployment, inference serving with Triton, training pipelines, MLflow, monitoring, and production AI operations.</p><div class="tl-tags"><span class="tl-tag">TRITON</span><span class="tl-tag">NVIDIA BCM</span><span class="tl-tag">HPe PRIVATE AI</span></div></div>
    </div>
  </div>
</section>

<div class="cdiv"><span class="cdiv-lbl">CONTACT</span></div>

<!-- CONTACT -->
<div class="contact-wrap reveal" style="position:relative;z-index:1;">
  <div class="sec-label" style="justify-content:center;">READY TO DEPLOY</div>
  <h2 class="contact-title">Let's Build the<br><span>AI Infrastructure</span><br>of Tomorrow</h2>
  <p class="contact-sub">From a single GPU server to a full-scale AI data center —<br>every deployment starts with a conversation.</p>
  <div style="display:flex;gap:20px;justify-content:center;flex-wrap:wrap;">
    <a href="mailto:contact@yourdomain.com" class="btn btn-c">INITIATE CONTACT</a>
    <a href="https://www.linkedin.com/in/christianniz" target="_blank" class="btn btn-m">LINKEDIN PROFILE</a>
  </div>
  <div style="margin-top:80px;display:flex;flex-wrap:wrap;justify-content:center;gap:40px;align-items:center;">
    <div style="text-align:center;"><div style="font-family:'Share Tech Mono',monospace;font-size:10px;color:var(--dim);letter-spacing:3px;margin-bottom:8px;">SPECIALTIES</div><div style="font-family:'Orbitron',monospace;font-size:12px;color:var(--cyan);">AI INFRASTRUCTURE</div></div>
    <div style="width:1px;height:40px;background:var(--border);"></div>
    <div style="text-align:center;"><div style="font-family:'Share Tech Mono',monospace;font-size:10px;color:var(--dim);letter-spacing:3px;margin-bottom:8px;">LOCATION</div><div style="font-family:'Orbitron',monospace;font-size:12px;color:var(--cyan);">AVAILABLE NATIONWIDE</div></div>
    <div style="width:1px;height:40px;background:var(--border);"></div>
    <div style="text-align:center;"><div style="font-family:'Share Tech Mono',monospace;font-size:10px;color:var(--dim);letter-spacing:3px;margin-bottom:8px;">STATUS</div><div style="font-family:'Orbitron',monospace;font-size:12px;color:#00ff88;">● AVAILABLE</div></div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">AI.ARCHITECT</div>
  <div class="footer-copy">© 2025 · AI SOLUTIONS ARCHITECT · ALL RIGHTS RESERVED</div>
  <a href="https://www.linkedin.com/in/christianniz" target="_blank" style="font-family:'Share Tech Mono',monospace;font-size:10px;color:var(--cyan);letter-spacing:2px;text-decoration:none;">linkedin.com/in/christianniz</a>
</footer>

<script>
// Particles
const pc = document.getElementById('particles');
['#00f5ff','#ff006e','#ffd700'].forEach(col => {
  for(let i=0;i<10;i++){
    const p=document.createElement('div');
    p.className='particle';
    p.style.cssText=`left:${Math.random()*100}vw;background:${col};animation-duration:${8+Math.random()*16}s;animation-delay:${Math.random()*20}s;`;
    pc.appendChild(p);
  }
});

// Hamburger
document.getElementById('hbg').addEventListener('click',()=>{
  document.getElementById('navlinks').classList.toggle('open');
});

// AI Concepts
const concepts = {
  llm:      {title:'LARGE LANGUAGE MODELS',    body:'Foundation models trained on massive datasets, capable of understanding and generating human language. The infrastructure behind LLMs — from H100 GPU clusters to high-throughput InfiniBand networking — is where my expertise directly enables their deployment at scale.',tags:['TRANSFORMER','GPU CLUSTER','TENSOR PARALLEL','KV CACHE']},
  inference:{title:'INFERENCE OPTIMIZATION',   body:'Getting models into production at low latency and high throughput. NVIDIA Triton, vLLM, TensorRT, and custom batching strategies deployed on bare-metal Kubernetes with GPU Operator — squeezing every token per second from the hardware.',tags:['TRITON','vLLM','TensorRT','QUANTIZATION','BATCHING']},
  training: {title:'DISTRIBUTED TRAINING',     body:'Multi-node, multi-GPU training across NVLink and InfiniBand fabrics. Data parallelism, model parallelism, and pipeline parallelism at scale. The physical infrastructure — network topology, storage throughput, and GPU topology — makes or breaks training runs.',tags:['NVLink','INFINIBAND','DDP','FSDP','MEGATRON']},
  rag:      {title:'RETRIEVAL AUGMENTED GEN',  body:'Grounding LLMs with real-time knowledge retrieval. Vector databases on VAST Data or NetApp storage, embedding pipelines, and hybrid search architectures that connect enterprise data to AI without hallucination.',tags:['VECTOR DB','EMBEDDINGS','CHUNKING','HYBRID SEARCH','VAST']},
  mlops:    {title:'MLOps & AI PIPELINES',     body:'The operational backbone of production AI. Model registries, experiment tracking with MLflow, automated retraining pipelines, A/B inference routing, and observability stacks — all running on OpenShift and Kubernetes.',tags:['MLFLOW','KUBEFLOW','ARGO','MONITORING','GITOPS']},
  fabric:   {title:'AI NETWORKING FABRIC',     body:'AI clusters demand ultra-low-latency, high-bandwidth network fabric. InfiniBand HDR/NDR for GPU-to-GPU communication, RoCE v2 over Ethernet, and Cisco AI fabric architecture — the arteries of high-performance compute.',tags:['INFINIBAND','ROCE','CISCO','RDMA','GPUDirect']},
  sovereign:{title:'SOVEREIGN AI',             body:'On-premises, private AI deployments where data never leaves your control. HPe Private Cloud AI, Run:AI workload orchestration, and VMware-backed virtualization deliver enterprise-grade AI sovereignty without sacrificing capability.',tags:['HPe PRIVATE AI','RUN:AI','ON-PREM','DATA RESIDENCY','VMware']}
};
document.getElementById('clist').addEventListener('click',e=>{
  const item=e.target.closest('.ci');
  if(!item)return;
  document.querySelectorAll('.ci').forEach(i=>i.classList.remove('active'));
  item.classList.add('active');
  const d=concepts[item.dataset.key];
  document.getElementById('cp-title').textContent=d.title;
  document.getElementById('cp-body').textContent=d.body;
  document.getElementById('cp-tags').innerHTML=d.tags.map(t=>`<span class="ctag">${t}</span>`).join('');
});

// Scroll reveal
const obs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('in');obs.unobserve(e.target);}});
},{threshold:0.08});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));
</script>
</body>
</html>
