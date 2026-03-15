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
    --dark3: #071525;
    --panel: rgba(0,245,255,0.04);
    --border: rgba(0,245,255,0.18);
    --text: #c8e8f0;
    --dim: #5a8a99;
    --glow-cyan: 0 0 20px rgba(0,245,255,0.5), 0 0 60px rgba(0,245,255,0.2);
    --glow-mag: 0 0 20px rgba(255,0,110,0.5), 0 0 60px rgba(255,0,110,0.2);
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--dark);
    color: var(--text);
    font-family: 'Rajdhani', sans-serif;
    font-size: 17px;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* ── GRID BACKGROUND ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,245,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,245,255,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* ── SCANLINE OVERLAY ── */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      0deg, transparent, transparent 2px,
      rgba(0,0,0,0.03) 2px, rgba(0,0,0,0.03) 4px
    );
    pointer-events: none;
    z-index: 999;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 16px 40px;
    background: rgba(2,8,18,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
  }

  .nav-logo {
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    font-weight: 900;
    color: var(--cyan);
    letter-spacing: 4px;
    text-shadow: var(--glow-cyan);
  }

  .nav-links {
    display: flex;
    gap: 36px;
    list-style: none;
  }

  .nav-links a {
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    color: var(--dim);
    text-decoration: none;
    letter-spacing: 2px;
    transition: color .3s;
  }

  .nav-links a:hover { color: var(--cyan); text-shadow: var(--glow-cyan); }

  .nav-cta {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    padding: 8px 20px;
    border: 1px solid var(--cyan);
    color: var(--cyan);
    text-decoration: none;
    letter-spacing: 2px;
    transition: all .3s;
    clip-path: polygon(8px 0%, 100% 0%, calc(100% - 8px) 100%, 0% 100%);
  }
  .nav-cta:hover {
    background: var(--cyan);
    color: var(--dark);
    box-shadow: var(--glow-cyan);
  }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: relative;
    padding: 120px 40px 80px;
    text-align: center;
    overflow: hidden;
  }

  .hero-bg-circle {
    position: absolute;
    border-radius: 50%;
    pointer-events: none;
  }
  .hero-bg-circle.c1 {
    width: 700px; height: 700px;
    top: 50%; left: 50%;
    transform: translate(-50%,-50%);
    background: radial-gradient(circle, rgba(0,245,255,0.06) 0%, transparent 70%);
    animation: pulse 6s ease-in-out infinite;
  }
  .hero-bg-circle.c2 {
    width: 1100px; height: 1100px;
    top: 50%; left: 50%;
    transform: translate(-50%,-50%);
    background: radial-gradient(circle, rgba(255,0,110,0.04) 0%, transparent 60%);
    animation: pulse 9s ease-in-out infinite reverse;
  }

  @keyframes pulse {
    0%,100% { transform: translate(-50%,-50%) scale(1); opacity:1; }
    50% { transform: translate(-50%,-50%) scale(1.08); opacity:.7; }
  }

  .hero-tag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--magenta);
    letter-spacing: 5px;
    margin-bottom: 24px;
    opacity: 0;
    animation: fadeUp .8s .3s forwards;
  }

  .hero-title {
    font-family: 'Orbitron', monospace;
    font-size: clamp(36px, 7vw, 92px);
    font-weight: 900;
    line-height: 1;
    margin-bottom: 16px;
    opacity: 0;
    animation: fadeUp .8s .5s forwards;
  }

  .hero-title .line1 { color: #fff; display: block; }
  .hero-title .line2 {
    display: block;
    background: linear-gradient(90deg, var(--cyan), var(--magenta));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    text-shadow: none;
  }

  .hero-sub {
    font-size: 18px;
    color: var(--dim);
    max-width: 620px;
    margin: 24px auto 48px;
    font-weight: 300;
    letter-spacing: 1px;
    opacity: 0;
    animation: fadeUp .8s .7s forwards;
  }

  .hero-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: center;
    margin-bottom: 56px;
    opacity: 0;
    animation: fadeUp .8s .9s forwards;
  }

  .badge {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    padding: 6px 16px;
    border: 1px solid;
    clip-path: polygon(6px 0%, 100% 0%, calc(100% - 6px) 100%, 0% 100%);
  }
  .badge.cyan { border-color: var(--cyan); color: var(--cyan); }
  .badge.mag { border-color: var(--magenta); color: var(--magenta); }
  .badge.gold { border-color: var(--gold); color: var(--gold); }

  .hero-scroll {
    position: absolute;
    bottom: 40px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    opacity: 0;
    animation: fadeUp .8s 1.4s forwards;
  }
  .scroll-line {
    width: 1px; height: 60px;
    background: linear-gradient(var(--cyan), transparent);
    animation: scrollPulse 2s infinite;
  }
  @keyframes scrollPulse {
    0%,100% { opacity:1; } 50% { opacity:.3; }
  }
  .scroll-text {
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    color: var(--dim);
    letter-spacing: 3px;
    writing-mode: vertical-rl;
  }

  @keyframes fadeUp {
    from { opacity:0; transform: translateY(30px); }
    to { opacity:1; transform: translateY(0); }
  }

  /* ── SECTION SHARED ── */
  section {
    position: relative;
    z-index: 1;
    padding: 100px 40px;
    max-width: 1200px;
    margin: 0 auto;
  }

  .section-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    letter-spacing: 5px;
    color: var(--magenta);
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 16px;
  }
  .section-label::before {
    content: '//';
    color: var(--cyan);
  }

  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: clamp(24px, 4vw, 42px);
    font-weight: 700;
    color: #fff;
    margin-bottom: 60px;
    line-height: 1.2;
  }

  .section-title span {
    background: linear-gradient(90deg, var(--cyan), #00a8b5);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  /* ── EXPERTISE GRID ── */
  .expertise-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 2px;
    position: relative;
  }

  .exp-card {
    background: var(--panel);
    border: 1px solid var(--border);
    padding: 36px 32px;
    position: relative;
    overflow: hidden;
    transition: all .4s;
    cursor: default;
  }
  .exp-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--cyan), transparent);
    opacity: 0;
    transition: opacity .4s;
  }
  .exp-card:hover {
    background: rgba(0,245,255,0.07);
    border-color: rgba(0,245,255,0.4);
    transform: translateY(-4px);
  }
  .exp-card:hover::before { opacity: 1; }

  .exp-icon {
    font-size: 32px;
    margin-bottom: 20px;
    display: block;
  }

  .exp-title {
    font-family: 'Orbitron', monospace;
    font-size: 14px;
    font-weight: 700;
    color: var(--cyan);
    letter-spacing: 2px;
    margin-bottom: 12px;
  }

  .exp-desc {
    font-size: 15px;
    color: var(--dim);
    line-height: 1.7;
    font-weight: 300;
  }

  .exp-number {
    position: absolute;
    top: 20px; right: 24px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: rgba(0,245,255,0.2);
  }

  /* ── CERTIFICATIONS ── */
  #certifications { background: transparent; }

  .cert-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
  }

  .cert-card {
    border: 1px solid var(--border);
    padding: 28px 24px;
    display: flex;
    flex-direction: column;
    gap: 10px;
    background: var(--panel);
    position: relative;
    clip-path: polygon(0 0, calc(100% - 20px) 0, 100% 20px, 100% 100%, 0 100%);
    transition: all .3s;
  }
  .cert-card:hover {
    border-color: var(--gold);
    box-shadow: 0 0 30px rgba(255,215,0,0.1);
  }
  .cert-card::after {
    content: '';
    position: absolute;
    top: 0; right: 0;
    width: 20px; height: 20px;
    border-bottom: 1px solid var(--border);
    border-left: 1px solid var(--border);
    clip-path: polygon(0 0, 100% 100%, 0 100%);
    background: var(--dark2);
  }

  .cert-name {
    font-family: 'Orbitron', monospace;
    font-size: 12px;
    font-weight: 700;
    color: var(--gold);
    letter-spacing: 1px;
  }
  .cert-body {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--dim);
    letter-spacing: 1px;
  }
  .cert-check {
    font-size: 18px;
    margin-top: 8px;
  }

  /* ── VENDORS ── */
  #vendors .vendor-intro {
    font-size: 16px;
    color: var(--dim);
    max-width: 700px;
    margin-bottom: 60px;
    font-weight: 300;
    line-height: 1.8;
  }

  .vendor-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 16px;
  }

  .vendor-card {
    border: 1px solid var(--border);
    padding: 24px 20px;
    text-align: center;
    background: var(--panel);
    transition: all .3s;
    cursor: default;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
  }
  .vendor-card:hover {
    border-color: rgba(0,245,255,0.5);
    background: rgba(0,245,255,0.07);
    box-shadow: var(--glow-cyan);
  }

  .vendor-logo-text {
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 1px;
  }
  .vendor-desc {
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    color: var(--dim);
    letter-spacing: 1px;
    line-height: 1.6;
  }

  /* vendor brand colors */
  .v-nvidia { color: #76b900; }
  .v-cisco  { color: #049fd9; }
  .v-dell   { color: #007db8; }
  .v-hpe    { color: #01a982; }
  .v-netapp { color: #0065a0; }
  .v-vast   { color: #e64082; }
  .v-sm     { color: #e5792a; }
  .v-vertiv { color: #c8102e; }
  .v-vmware { color: #607d8b; }
  .v-redhat { color: #e00; }
  .v-k8s    { color: #326ce5; }
  .v-runai  { color: #7c3aed; }

  /* ── AI CONCEPTS ── */
  #ai-concepts { background: transparent; }

  .concepts-wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: start;
  }

  .concept-list { display: flex; flex-direction: column; gap: 2px; }

  .concept-item {
    border: 1px solid var(--border);
    padding: 20px 24px;
    background: var(--panel);
    cursor: pointer;
    transition: all .3s;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .concept-item.active,
  .concept-item:hover {
    border-color: var(--cyan);
    background: rgba(0,245,255,0.06);
  }

  .concept-item-title {
    font-family: 'Orbitron', monospace;
    font-size: 12px;
    font-weight: 700;
    color: #fff;
    letter-spacing: 1px;
  }

  .concept-arrow {
    color: var(--cyan);
    font-size: 18px;
    transition: transform .3s;
  }
  .concept-item.active .concept-arrow { transform: rotate(90deg); }

  .concept-panel {
    border: 1px solid var(--border);
    padding: 40px;
    background: var(--panel);
    position: sticky;
    top: 100px;
  }

  .concept-panel h3 {
    font-family: 'Orbitron', monospace;
    font-size: 16px;
    color: var(--cyan);
    margin-bottom: 20px;
    letter-spacing: 2px;
  }

  .concept-panel p {
    font-size: 15px;
    color: var(--dim);
    line-height: 1.9;
    font-weight: 300;
  }

  .concept-tag-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 24px;
  }
  .ctag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    padding: 4px 12px;
    border: 1px solid rgba(0,245,255,0.3);
    color: var(--cyan);
    letter-spacing: 1px;
    clip-path: polygon(4px 0%, 100% 0%, calc(100% - 4px) 100%, 0% 100%);
  }

  /* ── AGENTIC AI SECTION ── */
  #agentic {
    background: linear-gradient(180deg, transparent, rgba(255,0,110,0.04), transparent);
  }

  .agentic-hero-text {
    font-size: clamp(14px, 2vw, 18px);
    color: var(--dim);
    max-width: 800px;
    line-height: 1.9;
    font-weight: 300;
    margin-bottom: 60px;
  }

  .agentic-cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 20px;
  }

  .ag-card {
    padding: 36px 28px;
    border: 1px solid;
    position: relative;
    overflow: hidden;
    transition: transform .3s;
  }
  .ag-card:hover { transform: translateY(-6px); }
  .ag-card::after {
    content: '';
    position: absolute;
    bottom: 0; right: 0;
    width: 60px; height: 60px;
    background: radial-gradient(circle at bottom right, var(--accent-col), transparent);
    opacity: .2;
  }
  .ag-card.type-a { border-color: rgba(0,245,255,.3); --accent-col: #00f5ff; background: rgba(0,245,255,.03); }
  .ag-card.type-b { border-color: rgba(255,0,110,.3); --accent-col: #ff006e; background: rgba(255,0,110,.03); }
  .ag-card.type-c { border-color: rgba(255,215,0,.3); --accent-col: #ffd700; background: rgba(255,215,0,.03); }

  .ag-num {
    font-family: 'Orbitron', monospace;
    font-size: 48px;
    font-weight: 900;
    opacity: .08;
    position: absolute;
    top: 10px; right: 16px;
    color: white;
  }
  .ag-title {
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    font-weight: 700;
    margin-bottom: 16px;
    letter-spacing: 2px;
  }
  .ag-card.type-a .ag-title { color: var(--cyan); }
  .ag-card.type-b .ag-title { color: var(--magenta); }
  .ag-card.type-c .ag-title { color: var(--gold); }
  .ag-desc { font-size: 14px; color: var(--dim); line-height: 1.8; font-weight: 300; }

  /* ── SKILLS BAR ── */
  #skills { background: transparent; }

  .skills-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 48px;
  }

  .skill-group-title {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    letter-spacing: 4px;
    color: var(--cyan);
    margin-bottom: 28px;
  }

  .skill-bar-row {
    margin-bottom: 20px;
  }

  .skill-bar-label {
    display: flex;
    justify-content: space-between;
    font-family: 'Rajdhani', sans-serif;
    font-size: 13px;
    font-weight: 600;
    color: var(--text);
    letter-spacing: 1px;
    margin-bottom: 8px;
  }
  .skill-bar-label span { color: var(--dim); font-size: 11px; }

  .skill-bar-track {
    height: 4px;
    background: rgba(255,255,255,0.05);
    border-radius: 2px;
    overflow: hidden;
    position: relative;
  }

  .skill-bar-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--cyan), var(--magenta));
    border-radius: 2px;
    transform-origin: left;
    animation: barGrow 1.5s cubic-bezier(.4,0,.2,1) forwards;
    transform: scaleX(0);
  }

  @keyframes barGrow {
    to { transform: scaleX(1); }
  }

  /* ── DEPLOYMENT TIMELINE ── */
  .timeline {
    position: relative;
    padding-left: 40px;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(var(--cyan), var(--magenta), transparent);
  }

  .tl-item {
    position: relative;
    margin-bottom: 40px;
    padding: 28px 32px;
    border: 1px solid var(--border);
    background: var(--panel);
    transition: all .3s;
  }
  .tl-item:hover {
    border-color: rgba(0,245,255,.4);
    background: rgba(0,245,255,.05);
  }

  .tl-dot {
    position: absolute;
    left: -47px;
    top: 28px;
    width: 14px; height: 14px;
    border: 2px solid var(--cyan);
    background: var(--dark);
    border-radius: 50%;
    box-shadow: var(--glow-cyan);
  }

  .tl-title {
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    font-weight: 700;
    color: var(--cyan);
    letter-spacing: 2px;
    margin-bottom: 10px;
  }

  .tl-desc {
    font-size: 14px;
    color: var(--dim);
    line-height: 1.8;
    font-weight: 300;
  }

  .tl-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 14px;
  }
  .tl-tag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    padding: 3px 10px;
    border: 1px solid rgba(255,0,110,.3);
    color: var(--magenta);
    letter-spacing: 1px;
  }

  /* ── CONTACT / CTA ── */
  #contact {
    text-align: center;
    padding: 120px 40px;
    position: relative;
    overflow: hidden;
  }

  #contact::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at center, rgba(0,245,255,0.06) 0%, transparent 70%);
    pointer-events: none;
  }

  .contact-title {
    font-family: 'Orbitron', monospace;
    font-size: clamp(28px, 5vw, 64px);
    font-weight: 900;
    color: #fff;
    line-height: 1.1;
    margin-bottom: 24px;
  }

  .contact-title span {
    background: linear-gradient(90deg, var(--cyan), var(--magenta));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .contact-sub {
    font-size: 16px;
    color: var(--dim);
    margin-bottom: 56px;
    font-weight: 300;
    letter-spacing: 1px;
  }

  .cta-btn {
    display: inline-block;
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 3px;
    padding: 18px 48px;
    border: 1px solid var(--cyan);
    color: var(--cyan);
    text-decoration: none;
    position: relative;
    overflow: hidden;
    transition: all .4s;
    clip-path: polygon(12px 0%, 100% 0%, calc(100% - 12px) 100%, 0% 100%);
  }
  .cta-btn::before {
    content: '';
    position: absolute;
    inset: 0;
    background: var(--cyan);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform .4s;
    z-index: -1;
  }
  .cta-btn:hover { color: var(--dark); box-shadow: var(--glow-cyan); }
  .cta-btn:hover::before { transform: scaleX(1); }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid var(--border);
    padding: 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: gap;
    position: relative;
    z-index: 1;
  }

  .footer-logo {
    font-family: 'Orbitron', monospace;
    font-size: 11px;
    font-weight: 900;
    color: var(--cyan);
    letter-spacing: 4px;
  }

  .footer-copy {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    color: var(--dim);
    letter-spacing: 2px;
  }

  /* ── FLOATING PARTICLES ── */
  .particle {
    position: fixed;
    width: 2px; height: 2px;
    background: var(--cyan);
    border-radius: 50%;
    pointer-events: none;
    z-index: 0;
    animation: floatParticle linear infinite;
    opacity: 0;
  }

  @keyframes floatParticle {
    0% { transform: translateY(100vh) translateX(0); opacity: 0; }
    10% { opacity: .6; }
    90% { opacity: .3; }
    100% { transform: translateY(-100px) translateX(40px); opacity: 0; }
  }

  /* ── CYBER DIVIDER ── */
  .cyber-divider {
    display: flex;
    align-items: center;
    gap: 16px;
    margin: 0 40px 0;
    padding: 0;
    height: 1px;
  }
  .cyber-divider::before, .cyber-divider::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border));
  }
  .cyber-divider::after {
    background: linear-gradient(270deg, transparent, var(--border));
  }
  .cyber-divider-inner {
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    color: var(--dim);
    letter-spacing: 3px;
    white-space: nowrap;
  }

  /* ── STAT ROW ── */
  .stat-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 2px;
    margin-bottom: 80px;
  }

  .stat-item {
    border: 1px solid var(--border);
    padding: 32px 28px;
    background: var(--panel);
    text-align: center;
    position: relative;
  }

  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: clamp(28px, 5vw, 48px);
    font-weight: 900;
    background: linear-gradient(90deg, var(--cyan), var(--magenta));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    display: block;
    line-height: 1;
    margin-bottom: 8px;
  }

  .stat-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    color: var(--dim);
    letter-spacing: 2px;
  }

  /* ── HAMBURGER MOBILE ── */
  .hamburger {
    display: none;
    flex-direction: column;
    gap: 5px;
    cursor: pointer;
    padding: 8px;
  }
  .hamburger span {
    width: 24px; height: 1px;
    background: var(--cyan);
    transition: all .3s;
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    nav { padding: 16px 24px; }
    .nav-links { display: none; }
    .nav-links.open {
      display: flex;
      flex-direction: column;
      position: absolute;
      top: 60px; left: 0; right: 0;
      background: rgba(2,8,18,0.97);
      padding: 24px;
      border-bottom: 1px solid var(--border);
    }
    .hamburger { display: flex; }
    .nav-cta { display: none; }
    #hero { padding: 100px 24px 60px; }
    section { padding: 70px 24px; }
    .concepts-wrapper { grid-template-columns: 1fr; }
    .concept-panel { display: none; }
    .skills-grid { grid-template-columns: 1fr; }
    footer { flex-direction: column; gap: 16px; text-align: center; }
    .cyber-divider { margin: 0 24px; }
  }

  /* ── GLOW TEXT ANIMATION ── */
  .glow-flicker {
    animation: textFlicker 8s infinite;
  }
  @keyframes textFlicker {
    0%,95%,100% { opacity:1; }
    96% { opacity:.7; }
    97% { opacity:1; }
    98% { opacity:.5; }
    99% { opacity:1; }
  }

  /* ── TERMINAL BLINK ── */
  .blink { animation: blink 1s step-end infinite; }
  @keyframes blink { 0%,100% { opacity:1; } 50% { opacity:0; } }

  /* ── SECTION FADE IN ── */
  .fade-in-section {
    opacity: 0;
    transform: translateY(40px);
    transition: opacity .8s ease, transform .8s ease;
  }
  .fade-in-section.visible {
    opacity: 1;
    transform: translateY(0);
  }
</style>
</head>
<body>

<!-- PARTICLES -->
<div id="particles"></div>

<!-- NAV -->
<nav id="main-nav">
  <div class="nav-logo glow-flicker">AI.ARCHITECT</div>
  <ul class="nav-links" id="nav-links">
    <li><a href="#expertise">EXPERTISE</a></li>
    <li><a href="#vendors">VENDORS</a></li>
    <li><a href="#ai-concepts">AI CONCEPTS</a></li>
    <li><a href="#agentic">AGENTIC</a></li>
    <li><a href="#skills">SKILLS</a></li>
    <li><a href="#contact">CONTACT</a></li>
  </ul>
  <a href="#contact" class="nav-cta">CONNECT</a>
  <div class="hamburger" id="hamburger">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- HERO -->
<section id="hero" style="max-width:100%; padding-top:0; padding-bottom:0;">
  <div class="hero-bg-circle c1"></div>
  <div class="hero-bg-circle c2"></div>

  <div class="hero-tag">// AI INFRASTRUCTURE · HARDWARE · CLOUD NATIVE</div>

  <h1 class="hero-title">
    <span class="line1">AI SOLUTIONS</span>
    <span class="line2">ARCHITECT</span>
  </h1>

  <p class="hero-sub">
    From bare-metal silicon to containerized intelligence — architecting the infrastructure that powers tomorrow's AI.
  </p>

  <div class="hero-badges">
    <span class="badge cyan">CKA CERTIFIED</span>
    <span class="badge gold">NETWORK+</span>
    <span class="badge mag">VMware VCP-DC</span>
    <span class="badge cyan">NVIDIA BCM</span>
    <span class="badge gold">HPe PRIVATE AI</span>
    <span class="badge mag">CISCO SECURE AI</span>
    <span class="badge cyan">OPENSHIFT</span>
    <span class="badge gold">RUN:AI</span>
  </div>

  <div class="hero-scroll">
    <div class="scroll-line"></div>
    <span class="scroll-text">SCROLL</span>
  </div>
</section>

<!-- STAT ROW -->
<div style="position:relative;z-index:1;max-width:1200px;margin:0 auto;padding:0 40px;" class="fade-in-section">
  <div class="stat-row">
    <div class="stat-item">
      <span class="stat-num">10+</span>
      <span class="stat-label">VENDOR ECOSYSTEMS</span>
    </div>
    <div class="stat-item">
      <span class="stat-num">3</span>
      <span class="stat-label">CERTIFICATIONS</span>
    </div>
    <div class="stat-item">
      <span class="stat-num">AI</span>
      <span class="stat-label">DATA CENTERS DEPLOYED</span>
    </div>
    <div class="stat-item">
      <span class="stat-num">∞</span>
      <span class="stat-label">STACK DEPTH</span>
    </div>
  </div>
</div>

<div class="cyber-divider"><span class="cyber-divider-inner">CORE_EXPERTISE</span></div>

<!-- EXPERTISE -->
<section id="expertise" class="fade-in-section">
  <div class="section-label">SPECIALIZATIONS</div>
  <h2 class="section-title">Built for the <span>AI Era</span></h2>

  <div class="expertise-grid">
    <div class="exp-card">
      <span class="exp-number">01</span>
      <span class="exp-icon">⬡</span>
      <div class="exp-title">AI DATA CENTER DEPLOYMENT</div>
      <p class="exp-desc">End-to-end architecture and deployment of AI data centers. From rack design and power planning to GPU cluster commissioning, I build the physical foundation that AI runs on.</p>
    </div>
    <div class="exp-card">
      <span class="exp-number">02</span>
      <span class="exp-icon">◈</span>
      <div class="exp-title">LIQUID COOLING SOLUTIONS</div>
      <p class="exp-desc">Certified in Vertiv liquid cooling infrastructure. Designing and deploying direct liquid cooling for high-density GPU environments where air simply isn't enough.</p>
    </div>
    <div class="exp-card">
      <span class="exp-number">03</span>
      <span class="exp-icon">◎</span>
      <div class="exp-title">KUBERNETES & CONTAINERS</div>
      <p class="exp-desc">CKA-certified administrator deploying containerized AI workloads at scale. OpenShift, Run:AI, and native Kubernetes across bare-metal and hybrid environments.</p>
    </div>
    <div class="exp-card">
      <span class="exp-number">04</span>
      <span class="exp-icon">⬢</span>
      <div class="exp-title">NVIDIA AI INFRASTRUCTURE</div>
      <p class="exp-desc">Deep expertise in NVIDIA Base Command Manager, DGX systems, networking fabric, and GPU cluster management for enterprise AI training and inference workloads.</p>
    </div>
    <div class="exp-card">
      <span class="exp-number">05</span>
      <span class="exp-icon">◇</span>
      <div class="exp-title">NETWORKING & SECURITY</div>
      <p class="exp-desc">Network+ certified with hands-on experience in AI fabric networking. One of a select few engineers to deploy the Cisco Secure AI Factory — securing AI infrastructure at the network layer.</p>
    </div>
    <div class="exp-card">
      <span class="exp-number">06</span>
      <span class="exp-icon">⬟</span>
      <div class="exp-title">PRIVATE AI PLATFORMS</div>
      <p class="exp-desc">HPe Private Cloud AI, Run:AI workload orchestration, and VMware VCP-certified virtualization — delivering sovereign, on-premises AI that keeps data in your control.</p>
    </div>
  </div>
</section>

<div class="cyber-divider"><span class="cyber-divider-inner">CERTIFICATIONS</span></div>

<!-- CERTIFICATIONS -->
<section id="certifications" class="fade-in-section">
  <div class="section-label">CREDENTIALS</div>
  <h2 class="section-title">Certified <span>Stack</span></h2>

  <div class="cert-row">
    <div class="cert-card">
      <div class="cert-name">CKA</div>
      <div class="cert-body">Certified Kubernetes Administrator</div>
      <div class="cert-body" style="color:var(--cyan);">CNCF</div>
      <div class="cert-check">✦</div>
    </div>
    <div class="cert-card">
      <div class="cert-name">NETWORK+</div>
      <div class="cert-body">CompTIA Network+ Certification</div>
      <div class="cert-body" style="color:var(--cyan);">CompTIA</div>
      <div class="cert-check">✦</div>
    </div>
    <div class="cert-card">
      <div class="cert-name">VCP-DCV</div>
      <div class="cert-body">VMware Certified Professional — Data Center Virtualization</div>
      <div class="cert-body" style="color:var(--cyan);">Broadcom / VMware</div>
      <div class="cert-check">✦</div>
    </div>
    <div class="cert-card">
      <div class="cert-name">CISCO SECURE AI</div>
      <div class="cert-body">Cisco Secure AI Factory — Select Deployment Engineer</div>
      <div class="cert-body" style="color:var(--cyan);">Cisco</div>
      <div class="cert-check">✦</div>
    </div>
    <div class="cert-card">
      <div class="cert-name">NVIDIA BCM</div>
      <div class="cert-body">NVIDIA Base Command Manager Infrastructure</div>
      <div class="cert-body" style="color:var(--cyan);">NVIDIA</div>
      <div class="cert-check">✦</div>
    </div>
    <div class="cert-card">
      <div class="cert-name">HPe PRIVATE AI</div>
      <div class="cert-body">HPe Private Cloud AI Deployment Specialist</div>
      <div class="cert-body" style="color:var(--cyan);">Hewlett Packard Enterprise</div>
      <div class="cert-check">✦</div>
    </div>
  </div>
</section>

<div class="cyber-divider"><span class="cyber-divider-inner">VENDOR_ECOSYSTEM</span></div>

<!-- VENDORS -->
<section id="vendors" class="fade-in-section">
  <div class="section-label">HARDWARE & SOFTWARE ECOSYSTEM</div>
  <h2 class="section-title">Vendor <span>Alliance</span></h2>
  <p class="vendor-intro">Hands-on deployment expertise across the full AI infrastructure stack — from compute silicon and high-density storage to hyperconverged networking and enterprise software platforms.</p>

  <div class="vendor-grid">
    <div class="vendor-card">
      <div class="vendor-logo-text v-nvidia">◈ NVIDIA</div>
      <div class="vendor-desc">DGX · H100 · BCM<br>GPU CLUSTERS · NVLink<br>Networking Fabric</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-cisco">◈ CISCO</div>
      <div class="vendor-desc">Secure AI Factory<br>UCS Compute<br>AI Fabric Networking</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-dell">◈ DELL</div>
      <div class="vendor-desc">PowerEdge AI<br>PowerScale Storage<br>VxRail HCI</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-hpe">◈ HPe</div>
      <div class="vendor-desc">Private Cloud AI<br>ProLiant DL Servers<br>Alletra Storage</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-sm">◈ SUPERMICRO</div>
      <div class="vendor-desc">AI Servers<br>GPU Optimized<br>Liquid Cooled Systems</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-netapp">◈ NetApp</div>
      <div class="vendor-desc">ONTAP AI<br>StorageGRID<br>AIPod Architecture</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-vast">◈ VAST DATA</div>
      <div class="vendor-desc">Universal Storage<br>AI Data Platform<br>NVMe-oF</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-vertiv">◈ VERTIV</div>
      <div class="vendor-desc">Liquid Cooling<br>CDU Systems<br>Power & Thermal</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-vmware">◈ VMware</div>
      <div class="vendor-desc">vSphere · vSAN<br>NSX Networking<br>VCP-DCV Certified</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-redhat">◈ RED HAT</div>
      <div class="vendor-desc">OpenShift Platform<br>RHOAI · Operators<br>Enterprise Kubernetes</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-k8s">◈ KUBERNETES</div>
      <div class="vendor-desc">CKA Certified<br>Bare-Metal Clusters<br>GPU Operator</div>
    </div>
    <div class="vendor-card">
      <div class="vendor-logo-text v-runai">◈ RUN:AI</div>
      <div class="vendor-desc">GPU Orchestration<br>Workload Scheduling<br>Resource Pooling</div>
    </div>
  </div>
</section>

<div class="cyber-divider"><span class="cyber-divider-inner">AI_KNOWLEDGE</span></div>

<!-- AI CONCEPTS -->
<section id="ai-concepts" class="fade-in-section">
  <div class="section-label">TECHNOLOGY LANDSCAPE</div>
  <h2 class="section-title">Core AI <span>Concepts</span></h2>

  <div class="concepts-wrapper">
    <div class="concept-list" id="concept-list">
      <div class="concept-item active" data-concept="llm">
        <span class="concept-item-title">LARGE LANGUAGE MODELS</span>
        <span class="concept-arrow">›</span>
      </div>
      <div class="concept-item" data-concept="inference">
        <span class="concept-item-title">INFERENCE OPTIMIZATION</span>
        <span class="concept-arrow">›</span>
      </div>
      <div class="concept-item" data-concept="training">
        <span class="concept-item-title">DISTRIBUTED TRAINING</span>
        <span class="concept-arrow">›</span>
      </div>
      <div class="concept-item" data-concept="rag">
        <span class="concept-item-title">RETRIEVAL AUGMENTED GEN</span>
        <span class="concept-arrow">›</span>
      </div>
      <div class="concept-item" data-concept="mlops">
        <span class="concept-item-title">MLOps & AI PIPELINES</span>
        <span class="concept-arrow">›</span>
      </div>
      <div class="concept-item" data-concept="fabric">
        <span class="concept-item-title">AI NETWORKING FABRIC</span>
        <span class="concept-arrow">›</span>
      </div>
      <div class="concept-item" data-concept="sovereign">
        <span class="concept-item-title">SOVEREIGN AI</span>
        <span class="concept-arrow">›</span>
      </div>
    </div>

    <div class="concept-panel" id="concept-panel">
      <h3 id="cp-title">LARGE LANGUAGE MODELS</h3>
      <p id="cp-body">Foundation models trained on massive datasets, capable of understanding and generating human language. The infrastructure behind LLMs — from H100 GPU clusters to high-throughput InfiniBand networking — is where my expertise directly enables their deployment at scale.</p>
      <div class="concept-tag-row" id="cp-tags">
        <span class="ctag">TRANSFORMER</span>
        <span class="ctag">GPU CLUSTER</span>
        <span class="ctag">TENSOR PARALLEL</span>
        <span class="ctag">KV CACHE</span>
      </div>
    </div>
  </div>
</section>

<div class="cyber-divider"><span class="cyber-divider-inner">AGENTIC_AI</span></div>

<!-- AGENTIC AI -->
<section id="agentic" class="fade-in-section">
  <div class="section-label">THE NEXT FRONTIER</div>
  <h2 class="section-title">Agentic <span>AI Systems</span></h2>

  <p class="agentic-hero-text">
    Agentic AI represents the shift from reactive models to autonomous systems that plan, reason, and act — orchestrating tools, APIs, and sub-agents to complete complex, multi-step objectives. The infrastructure to run agentic workloads demands low-latency, high-throughput compute with intelligent orchestration layers. This is where the physical and digital stack converge.
  </p>

  <div class="agentic-cards">
    <div class="ag-card type-a">
      <span class="ag-num">01</span>
      <div class="ag-title">AUTONOMOUS AGENTS</div>
      <p class="ag-desc">AI systems that perceive their environment, form goals, and execute multi-step plans without continuous human input. Requires robust inference infrastructure with deterministic SLAs.</p>
    </div>
    <div class="ag-card type-b">
      <span class="ag-num">02</span>
      <div class="ag-title">MULTI-AGENT ORCHESTRATION</div>
      <p class="ag-desc">Networks of specialized agents collaborating in real-time — supervisor agents routing tasks to workers, with shared memory and tool access. Demands containerized microservice architectures on GPU-accelerated Kubernetes.</p>
    </div>
    <div class="ag-card type-c">
      <span class="ag-num">03</span>
      <div class="ag-title">TOOL-USE & FUNCTION CALLING</div>
      <p class="ag-desc">Agents equipped with APIs, search, code execution, and external system access. The secure AI factory model — with Cisco's zero-trust networking — ensures agents can act safely within enterprise boundaries.</p>
    </div>
    <div class="ag-card type-a">
      <span class="ag-num">04</span>
      <div class="ag-title">MEMORY ARCHITECTURES</div>
      <p class="ag-desc">Short and long-term memory systems powering persistent agent state. Vector databases, RAG pipelines, and high-speed NVMe storage like VAST Data provide the retrieval backbone.</p>
    </div>
    <div class="ag-card type-b">
      <span class="ag-num">05</span>
      <div class="ag-title">INFERENCE PIPELINES</div>
      <p class="ag-desc">Low-latency inference at the core of every agentic loop. Run:AI GPU scheduling, vLLM serving, and NVIDIA Triton ensure agents respond in milliseconds under heavy concurrent load.</p>
    </div>
    <div class="ag-card type-c">
      <span class="ag-num">06</span>
      <div class="ag-title">HUMAN-IN-THE-LOOP</div>
      <p class="ag-desc">Agentic systems designed with control checkpoints, audit trails, and override mechanisms — critical for enterprise safety. Architectural decisions that make AI explainable and controllable from day one.</p>
    </div>
  </div>
</section>

<div class="cyber-divider"><span class="cyber-divider-inner">DEPLOYMENT_STACK</span></div>

<!-- DEPLOYMENT TIMELINE -->
<section id="skills" class="fade-in-section">
  <div class="section-label">FULL STACK DEPLOYMENT</div>
  <h2 class="section-title">From Silicon to <span>Inference</span></h2>

  <div style="display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:start;">
    <div>
      <div class="skill-group-title">// INFRASTRUCTURE LAYERS</div>
      <div class="skill-bar-row">
        <div class="skill-bar-label">AI Hardware & Compute <span>Expert</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:97%"></div></div>
      </div>
      <div class="skill-bar-row">
        <div class="skill-bar-label">Data Center Networking <span>Expert</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:93%"></div></div>
      </div>
      <div class="skill-bar-row">
        <div class="skill-bar-label">Kubernetes / OpenShift <span>CKA</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:95%"></div></div>
      </div>
      <div class="skill-bar-row">
        <div class="skill-bar-label">NVIDIA BCM / GPU Ops <span>Specialist</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:92%"></div></div>
      </div>
      <div class="skill-bar-row">
        <div class="skill-bar-label">Liquid Cooling (Vertiv) <span>Certified</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:89%"></div></div>
      </div>
      <div class="skill-bar-row">
        <div class="skill-bar-label">VMware vSphere / vSAN <span>VCP-DCV</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:90%"></div></div>
      </div>
    </div>

    <div class="timeline">
      <div class="tl-item">
        <div class="tl-dot"></div>
        <div class="tl-title">LAYER 0 — PHYSICAL</div>
        <p class="tl-desc">Rack design, power distribution, liquid cooling loops, structured cabling. The atoms before the bits.</p>
        <div class="tl-tags">
          <span class="tl-tag">VERTIV CDU</span>
          <span class="tl-tag">SUPERMICRO</span>
          <span class="tl-tag">DELL</span>
          <span class="tl-tag">HPe</span>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-dot"></div>
        <div class="tl-title">LAYER 1 — COMPUTE & STORAGE</div>
        <p class="tl-desc">GPU cluster provisioning, NVMe storage fabric, RAID configuration, DGX OS deployment, NetApp & VAST integration.</p>
        <div class="tl-tags">
          <span class="tl-tag">NVIDIA DGX</span>
          <span class="tl-tag">NETAPP</span>
          <span class="tl-tag">VAST</span>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-dot"></div>
        <div class="tl-title">LAYER 2 — NETWORKING</div>
        <p class="tl-desc">InfiniBand & RoCE fabric, Cisco AI networking, zero-trust Secure AI Factory perimeter, east-west GPU traffic optimization.</p>
        <div class="tl-tags">
          <span class="tl-tag">CISCO</span>
          <span class="tl-tag">INFINIBAND</span>
          <span class="tl-tag">ROCE</span>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-dot"></div>
        <div class="tl-title">LAYER 3 — ORCHESTRATION</div>
        <p class="tl-desc">Kubernetes cluster standup, OpenShift operators, Run:AI scheduler, NVIDIA GPU Operator, namespace isolation, RBAC.</p>
        <div class="tl-tags">
          <span class="tl-tag">OPENSHIFT</span>
          <span class="tl-tag">RUN:AI</span>
          <span class="tl-tag">CKA</span>
        </div>
      </div>
      <div class="tl-item">
        <div class="tl-dot" style="border-color:var(--magenta);box-shadow:var(--glow-mag);"></div>
        <div class="tl-title" style="color:var(--magenta);">LAYER 4 — AI WORKLOADS</div>
        <p class="tl-desc">Model deployment, inference serving with Triton, training pipelines, MLflow, monitoring, and production AI operations.</p>
        <div class="tl-tags">
          <span class="tl-tag">TRITON</span>
          <span class="tl-tag">NVIDIA BCM</span>
          <span class="tl-tag">HPe PRIVATE AI</span>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="cyber-divider"><span class="cyber-divider-inner">CONTACT</span></div>

<!-- CONTACT -->
<section id="contact" style="max-width:100%;padding:0;">
  <div style="max-width:1200px;margin:0 auto;padding:120px 40px;text-align:center;position:relative;">
    <div style="position:absolute;inset:0;background:radial-gradient(ellipse at center, rgba(0,245,255,0.05) 0%, transparent 70%);pointer-events:none;"></div>

    <div class="section-label" style="justify-content:center;">READY TO DEPLOY</div>

    <h2 class="contact-title">
      Let's Build the<br><span>AI Infrastructure</span><br>of Tomorrow
    </h2>

    <p class="contact-sub">
      From a single GPU server to a full-scale AI data center —<br>
      every deployment starts with a conversation.
    </p>

    <div style="display:flex;gap:20px;justify-content:center;flex-wrap:wrap;">
      <a href="mailto:contact@yourdomain.com" class="cta-btn">INITIATE CONTACT</a>
      <a href="https://linkedin.com/in/yourprofile" class="cta-btn" style="border-color:var(--magenta);color:var(--magenta);" onmouseenter="this.style.background='var(--magenta)';this.style.color='var(--dark)';this.style.boxShadow='var(--glow-mag)'" onmouseleave="this.style.background='';this.style.color='var(--magenta)';this.style.boxShadow=''">LINKEDIN</a>
    </div>

    <div style="margin-top:80px;display:flex;flex-wrap:wrap;justify-content:center;gap:40px;">
      <div style="text-align:center;">
        <div style="font-family:'Share Tech Mono',monospace;font-size:10px;color:var(--dim);letter-spacing:3px;margin-bottom:8px;">SPECIALTIES</div>
        <div style="font-family:'Orbitron',monospace;font-size:12px;color:var(--cyan);">AI INFRASTRUCTURE</div>
      </div>
      <div style="width:1px;background:var(--border);"></div>
      <div style="text-align:center;">
        <div style="font-family:'Share Tech Mono',monospace;font-size:10px;color:var(--dim);letter-spacing:3px;margin-bottom:8px;">LOCATION</div>
        <div style="font-family:'Orbitron',monospace;font-size:12px;color:var(--cyan);">AVAILABLE NATIONWIDE</div>
      </div>
      <div style="width:1px;background:var(--border);"></div>
      <div style="text-align:center;">
        <div style="font-family:'Share Tech Mono',monospace;font-size:10px;color:var(--dim);letter-spacing:3px;margin-bottom:8px;">STATUS</div>
        <div style="font-family:'Orbitron',monospace;font-size:12px;color:#00ff88;">● AVAILABLE</div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">AI.ARCHITECT</div>
  <div class="footer-copy">© 2025 · AI SOLUTIONS ARCHITECT · ALL RIGHTS RESERVED</div>
  <div style="font-family:'Share Tech Mono',monospace;font-size:10px;color:var(--dim);letter-spacing:2px;">
    BUILT FOR <span style="color:var(--cyan)">GitHub.io</span>
  </div>
</footer>

<script>
// ── PARTICLES ──
const particleContainer = document.getElementById('particles');
const colors = ['#00f5ff','#ff006e','#ffd700'];
for (let i = 0; i < 30; i++) {
  const p = document.createElement('div');
  p.className = 'particle';
  p.style.left = Math.random() * 100 + 'vw';
  p.style.animationDuration = (8 + Math.random() * 16) + 's';
  p.style.animationDelay = (Math.random() * 20) + 's';
  p.style.background = colors[Math.floor(Math.random() * colors.length)];
  p.style.opacity = Math.random() * 0.5;
  particleContainer.appendChild(p);
}

// ── HAMBURGER ──
document.getElementById('hamburger').addEventListener('click', () => {
  document.getElementById('nav-links').classList.toggle('open');
});

// ── CONCEPT PANEL DATA ──
const conceptData = {
  llm: {
    title: 'LARGE LANGUAGE MODELS',
    body: 'Foundation models trained on massive datasets, capable of understanding and generating human language. The infrastructure behind LLMs — from H100 GPU clusters to high-throughput InfiniBand networking — is where my expertise directly enables their deployment at scale.',
    tags: ['TRANSFORMER','GPU CLUSTER','TENSOR PARALLEL','KV CACHE']
  },
  inference: {
    title: 'INFERENCE OPTIMIZATION',
    body: 'Getting models into production at low latency and high throughput. NVIDIA Triton, vLLM, TensorRT, and custom batching strategies deployed on bare-metal Kubernetes with GPU Operator — squeezing every token per second from the hardware.',
    tags: ['TRITON','vLLM','TensorRT','QUANTIZATION','BATCHING']
  },
  training: {
    title: 'DISTRIBUTED TRAINING',
    body: 'Multi-node, multi-GPU training across NVLink and InfiniBand fabrics. Data parallelism, model parallelism, and pipeline parallelism at scale. The physical infrastructure — network topology, storage throughput, and GPU topology — makes or breaks training runs.',
    tags: ['NVLink','INFINIBAND','DDP','FSDP','MEGATRON']
  },
  rag: {
    title: 'RETRIEVAL AUGMENTED GENERATION',
    body: 'Grounding LLMs with real-time knowledge retrieval. Vector databases on VAST Data or NetApp storage, embedding pipelines, and hybrid search architectures that connect enterprise data to AI without hallucination.',
    tags: ['VECTOR DB','EMBEDDINGS','CHUNKING','HYBRID SEARCH','VAST']
  },
  mlops: {
    title: 'MLOps & AI PIPELINES',
    body: 'The operational backbone of production AI. Model registries, experiment tracking with MLflow, automated retraining pipelines, A/B inference routing, and observability stacks — all running on OpenShift and Kubernetes.',
    tags: ['MLFLOW','KUBEFLOW','ARGO','MONITORING','GITOPS']
  },
  fabric: {
    title: 'AI NETWORKING FABRIC',
    body: 'AI clusters demand ultra-low-latency, high-bandwidth network fabric. InfiniBand HDR/NDR for GPU-to-GPU communication, RoCE v2 over Ethernet, and Cisco AI fabric architecture — the arteries of high-performance compute.',
    tags: ['INFINIBAND','ROCE','CISCO','RDMA','GPUDirect']
  },
  sovereign: {
    title: 'SOVEREIGN AI',
    body: 'On-premises, private AI deployments where data never leaves your control. HPe Private Cloud AI, Run:AI workload orchestration, and VMware-backed virtualization deliver enterprise-grade AI sovereignty without sacrificing capability.',
    tags: ['HPe PRIVATE AI','RUN:AI','ON-PREM','DATA RESIDENCY','VMware']
  }
};

document.getElementById('concept-list').addEventListener('click', e => {
  const item = e.target.closest('.concept-item');
  if (!item) return;
  document.querySelectorAll('.concept-item').forEach(i => i.classList.remove('active'));
  item.classList.add('active');
  const key = item.dataset.concept;
  const d = conceptData[key];
  document.getElementById('cp-title').textContent = d.title;
  document.getElementById('cp-body').textContent = d.body;
  const tagsEl = document.getElementById('cp-tags');
  tagsEl.innerHTML = d.tags.map(t => `<span class="ctag">${t}</span>`).join('');
});

// ── INTERSECTION OBSERVER (fade in) ──
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); }
  });
}, { threshold: 0.1 });
document.querySelectorAll('.fade-in-section').forEach(el => observer.observe(el));
</script>
</body>
</html>
