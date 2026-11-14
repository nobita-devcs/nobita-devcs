
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#070910">
<meta name="description" content="Nobita | Creative Developer, Digital Explorer and Builder.">
<title>NOBITA.exe | Digital Experience</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">

<style>
:root {
  --bg: #070910;
  --panel: #0d111c;
  --blue: #38bdf8;
  --cyan: #67e8f9;
  --purple: #8b5cf6;
  --text: #f1f5f9;
  --muted: #8793a8;
  --border: rgba(148,163,184,.14);
  --mono: "DM Mono", monospace;
  --font: "Inter", sans-serif;
}

* { margin:0; padding:0; box-sizing:border-box; }

html {
  scroll-behavior:smooth;
  scroll-padding-top:90px;
}

body {
  background:var(--bg);
  color:var(--text);
  font-family:var(--font);
  overflow-x:hidden;
  cursor:none;
}

a { color:inherit; text-decoration:none; }
button { font:inherit; }

::selection {
  background:var(--blue);
  color:#06101a;
}

#progress {
  position:fixed;
  top:0; left:0;
  height:2px;
  width:0%;
  background:linear-gradient(90deg,var(--blue),var(--purple));
  z-index:1000;
  box-shadow:0 0 12px var(--blue);
}

/* BACKGROUND */

.background {
  position:fixed;
  inset:0;
  z-index:-3;
  overflow:hidden;
  pointer-events:none;
  background:
    radial-gradient(ellipse at 15% 20%,rgba(14,165,233,.09),transparent 38%),
    radial-gradient(ellipse at 85% 65%,rgba(124,58,237,.09),transparent 40%),
    #070910;
}

.grid {
  position:absolute;
  inset:0;
  background-image:
    linear-gradient(rgba(148,163,184,.035) 1px,transparent 1px),
    linear-gradient(90deg,rgba(148,163,184,.035) 1px,transparent 1px);
  background-size:55px 55px;
  mask-image:linear-gradient(to bottom,black,transparent 90%);
}

.orb {
  position:absolute;
  width:420px;
  height:420px;
  border-radius:50%;
  filter:blur(110px);
  opacity:.14;
  animation:float 12s ease-in-out infinite alternate;
}

.orb.one { background:#0284c7; top:10%; left:-180px; }
.orb.two { background:#7c3aed; bottom:5%; right:-180px; animation-delay:-5s; }

@keyframes float {
  from { transform:translate(0,0) scale(1); }
  to { transform:translate(90px,70px) scale(1.25); }
}

#particles {
  position:fixed;
  inset:0;
  width:100%;
  height:100%;
  z-index:-1;
  pointer-events:none;
}

/* CURSOR */

.cursor, .cursor-dot {
  position:fixed;
  top:0; left:0;
  pointer-events:none;
  z-index:2000;
  border-radius:50%;
  transform:translate(-50%,-50%);
}

.cursor {
  width:34px;
  height:34px;
  border:1px solid rgba(56,189,248,.7);
  transition:width .2s,height .2s,background .2s;
}

.cursor-dot {
  width:5px;
  height:5px;
  background:var(--cyan);
  box-shadow:0 0 12px var(--blue);
}

.cursor.active {
  width:55px;
  height:55px;
  background:rgba(56,189,248,.08);
}

@media (hover:none) {
  body { cursor:auto; }
  .cursor,.cursor-dot { display:none; }
}

/* NAVBAR */

header {
  position:fixed;
  top:0;
  left:0;
  width:100%;
  z-index:100;
  border-bottom:1px solid transparent;
  transition:.3s;
}

header.scrolled {
  background:rgba(7,9,16,.82);
  backdrop-filter:blur(18px);
  border-color:var(--border);
}

.nav {
  max-width:1200px;
  height:78px;
  margin:auto;
  padding:0 28px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.logo {
  font-size:19px;
  font-weight:900;
  letter-spacing:3px;
}

.logo span { color:var(--blue); }

.nav-links {
  display:flex;
  align-items:center;
  gap:32px;
}

.nav-links a {
  color:var(--muted);
  font-size:12px;
  font-family:var(--mono);
  transition:.25s;
}

.nav-links a:hover,
.nav-links a.active { color:var(--blue); }

.nav-actions {
  display:flex;
  align-items:center;
  gap:12px;
}

.sound-btn,.menu-btn {
  background:rgba(255,255,255,.035);
  border:1px solid var(--border);
  color:var(--text);
  padding:10px 13px;
  border-radius:9px;
  cursor:pointer;
  font-size:11px;
  font-family:var(--mono);
}

.sound-btn:hover,.menu-btn:hover {
  border-color:var(--blue);
  color:var(--blue);
}

.menu-btn { display:none; }

/* GENERAL */

.container {
  max-width:1120px;
  margin:auto;
  padding:0 28px;
}

.section {
  padding:125px 0;
  position:relative;
}

.eyebrow {
  color:var(--blue);
  font-family:var(--mono);
  font-size:11px;
  letter-spacing:3px;
  text-transform:uppercase;
  display:flex;
  align-items:center;
  gap:12px;
}

.eyebrow:before {
  content:"";
  width:25px;
  height:1px;
  background:var(--blue);
}

.section-title {
  font-size:clamp(34px,5vw,58px);
  font-weight:800;
  letter-spacing:-2.5px;
  margin:17px 0;
}

.section-desc {
  max-width:550px;
  color:var(--muted);
  line-height:1.9;
  font-size:14px;
}

/* HERO */

.hero {
  min-height:100vh;
  display:flex;
  align-items:center;
  padding-top:100px;
  position:relative;
}

.hero-content { max-width:850px; }

.status {
  display:inline-flex;
  align-items:center;
  gap:10px;
  padding:9px 14px;
  border:1px solid var(--border);
  background:rgba(255,255,255,.025);
  border-radius:30px;
  font-family:var(--mono);
  font-size:10px;
  color:#b8c4d5;
  margin-bottom:35px;
}

.status-dot {
  width:7px;
  height:7px;
  border-radius:50%;
  background:#4ade80;
  box-shadow:0 0 12px #4ade80;
  animation:pulse 1.5s infinite;
}

@keyframes pulse {
  50% { opacity:.35; }
}

.hero h1 {
  font-size:clamp(55px,10vw,112px);
  line-height:.98;
  letter-spacing:-8px;
  font-weight:900;
}

.gradient-text {
  background:linear-gradient(100deg,#fff 5%,#7dd3fc 45%,#818cf8 90%);
  -webkit-background-clip:text;
  background-clip:text;
  color:transparent;
  background-size:200% auto;
  animation:shine 5s linear infinite;
}

@keyframes shine {
  to { background-position:200% center; }
}

.hero-role {
  margin-top:28px;
  color:#cbd5e1;
  font-size:clamp(15px,2vw,19px);
  letter-spacing:.3px;
}

.hero-description {
  color:var(--muted);
  max-width:550px;
  line-height:1.9;
  margin-top:18px;
  font-size:14px;
}

.hero-buttons {
  display:flex;
  flex-wrap:wrap;
  gap:13px;
  margin-top:38px;
}

.btn {
  display:inline-flex;
  align-items:center;
  justify-content:center;
  gap:10px;
  padding:15px 21px;
  border-radius:8px;
  font-size:12px;
  font-weight:700;
  transition:transform .25s,box-shadow .25s,border .25s;
}

.btn:hover { transform:translateY(-4px); }

.btn-primary {
  background:linear-gradient(110deg,#0284c7,#2563eb);
  box-shadow:0 8px 30px rgba(37,99,235,.22);
}

.btn-primary:hover { box-shadow:0 10px 40px rgba(37,99,235,.4); }

.btn-outline {
  border:1px solid var(--border);
  background:rgba(255,255,255,.025);
}

.btn-outline:hover { border-color:var(--blue); }

.hero-meta {
  margin-top:65px;
  display:flex;
  gap:35px;
  flex-wrap:wrap;
}

.meta-item { font-family:var(--mono); }

.meta-item strong {
  display:block;
  font-size:17px;
  color:#e2e8f0;
  margin-bottom:6px;
}

.meta-item span {
  color:var(--muted);
  font-size:10px;
  letter-spacing:1px;
}

/* SCROLL INDICATOR */

.scroll-indicator {
  position:absolute;
  right:35px;
  bottom:45px;
  writing-mode:vertical-rl;
  font:10px var(--mono);
  color:var(--muted);
  letter-spacing:3px;
}

.scroll-indicator:after {
  content:"";
  display:inline-block;
  width:1px;
  height:55px;
  margin-top:15px;
  background:linear-gradient(var(--blue),transparent);
}

/* ABOUT */

.about-grid {
  display:grid;
  grid-template-columns:1.15fr .85fr;
  gap:65px;
  align-items:center;
  margin-top:55px;
}

.about-text {
  color:#a6b2c5;
  line-height:2;
  font-size:14px;
}

.about-text p + p { margin-top:18px; }

.terminal {
  border:1px solid var(--border);
  background:rgba(13,17,28,.8);
  border-radius:13px;
  overflow:hidden;
  box-shadow:0 20px 70px rgba(0,0,0,.25);
}

.terminal-head {
  padding:15px 18px;
  border-bottom:1px solid var(--border);
  display:flex;
  align-items:center;
  gap:7px;
}

.terminal-head i {
  width:8px;
  height:8px;
  border-radius:50%;
  background:#475569;
}

.terminal-head i:first-child { background:#fb7185; }
.terminal-head i:nth-child(2) { background:#fbbf24; }
.terminal-head i:nth-child(3) { background:#4ade80; }

.terminal-label {
  margin-left:auto;
  color:var(--muted);
  font:10px var(--mono);
}

.terminal-body {
  padding:25px;
  font:12px/2.3 var(--mono);
  color:#a5b4c7;
}

.terminal-body .command { color:var(--cyan); }
.terminal-body .value { color:#c4b5fd; }
.terminal-body .success { color:#4ade80; }

/* SKILLS */

.skills-grid {
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:16px;
  margin-top:50px;
}

.skill-card {
  border:1px solid var(--border);
  background:linear-gradient(145deg,rgba(255,255,255,.045),rgba(255,255,255,.012));
  border-radius:12px;
  padding:25px;
  transition:.3s;
}

.skill-card:hover {
  transform:translateY(-7px);
  border-color:rgba(56,189,248,.5);
  box-shadow:0 15px 45px rgba(14,165,233,.07);
}

.skill-icon {
  font-size:22px;
  margin-bottom:18px;
  color:var(--blue);
}

.skill-card h3 { font-size:15px; margin-bottom:9px; }

.skill-card p {
  font-size:12px;
  line-height:1.8;
  color:var(--muted);
}

/* PROJECTS */

.projects-grid {
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:18px;
  margin-top:50px;
}

.project-card {
  position:relative;
  min-height:230px;
  padding:28px;
  border:1px solid var(--border);
  border-radius:13px;
  background:
    radial-gradient(circle at 100% 0%,rgba(37,99,235,.11),transparent 45%),
    rgba(255,255,255,.018);
  overflow:hidden;
  transition:.35s;
}

.project-card:hover {
  transform:translateY(-6px);
  border-color:rgba(56,189,248,.5);
}

.project-number {
  color:var(--blue);
  font:11px var(--mono);
  letter-spacing:2px;
}

.project-card h3 {
  margin-top:28px;
  font-size:21px;
}

.project-card p {
  margin-top:12px;
  max-width:390px;
  color:var(--muted);
  font-size:12px;
  line-height:1.8;
}

.project-tags {
  display:flex;
  gap:8px;
  flex-wrap:wrap;
  margin-top:22px;
}

.project-tags span {
  font:10px var(--mono);
  color:#9caec5;
  padding:6px 9px;
  border:1px solid var(--border);
  border-radius:5px;
}

.project-arrow {
  position:absolute;
  right:25px;
  top:24px;
  color:var(--blue);
  font-size:20px;
}

/* TIMELINE */

.timeline {
  margin-top:50px;
  border-left:1px solid rgba(56,189,248,.35);
  margin-left:7px;
}

.timeline-item {
  position:relative;
  padding:0 0 35px 30px;
}

.timeline-item:before {
  content:"";
  position:absolute;
  left:-5px;
  top:5px;
  width:9px;
  height:9px;
  background:var(--blue);
  border-radius:50%;
  box-shadow:0 0 15px var(--blue);
}

.timeline-item span {
  font:10px var(--mono);
  color:var(--blue);
  letter-spacing:1px;
}

.timeline-item h3 { font-size:16px; margin-top:9px; }

.timeline-item p {
  color:var(--muted);
  font-size:12px;
  margin-top:8px;
  line-height:1.8;
}

/* CONTACT */

.contact-box {
  margin-top:50px;
  padding:60px 35px;
  text-align:center;
  border:1px solid rgba(56,189,248,.23);
  border-radius:17px;
  background:
    radial-gradient(ellipse at center top,rgba(37,99,235,.15),transparent 70%),
    rgba(255,255,255,.015);
}

.contact-box h3 {
  font-size:clamp(27px,5vw,43px);
  letter-spacing:-1.5px;
}

.contact-box p {
  max-width:480px;
  margin:18px auto 28px;
  color:var(--muted);
  font-size:13px;
  line-height:1.8;
}

/* FOOTER */

footer {
  border-top:1px solid var(--border);
  padding:28px 0;
}

.footer-inner {
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:15px;
  flex-wrap:wrap;
}

.footer-inner p {
  color:var(--muted);
  font:10px var(--mono);
}

.footer-links { display:flex; gap:18px; }

.footer-links a {
  color:var(--muted);
  font:10px var(--mono);
}

.footer-links a:hover { color:var(--blue); }

/* REVEAL */

.reveal {
  opacity:0;
  transform:translateY(30px);
  transition:opacity .8s ease,transform .8s ease;
}

.reveal.visible {
  opacity:1;
  transform:translateY(0);
}

/* TOAST */

.toast {
  position:fixed;
  bottom:25px;
  left:50%;
  transform:translate(-50%,20px);
  opacity:0;
  pointer-events:none;
  background:#111827;
  border:1px solid rgba(56,189,248,.4);
  padding:13px 20px;
  border-radius:8px;
  font:11px var(--mono);
  z-index:3000;
  transition:.3s;
}

.toast.show {
  opacity:1;
  transform:translate(-50%,0);
}

/* MOBILE */

@media(max-width:800px) {
  .nav-links {
    position:absolute;
    top:78px;
    left:0;
    right:0;
    display:none;
    flex-direction:column;
    gap:0;
    background:rgba(7,9,16,.97);
    border-bottom:1px solid var(--border);
    padding:15px 25px;
  }

  .nav-links.open { display:flex; }

  .nav-links a {
    width:100%;
    padding:16px 0;
    border-bottom:1px solid var(--border);
  }

  .menu-btn { display:block; }
  .about-grid { grid-template-columns:1fr; gap:35px; }
  .skills-grid { grid-template-columns:repeat(2,1fr); }
  .scroll-indicator { display:none; }
}

@media(max-width:560px) {
  .container { padding:0 21px; }
  .nav { padding:0 20px; }
  .hero h1 { letter-spacing:-4px; }
  .section { padding:90px 0; }
  .skills-grid,.projects-grid { grid-template-columns:1fr; }
  .hero-meta { gap:23px; }
  .contact-box { padding:45px 20px; }
  .footer-inner { justify-content:center; text-align:center; }
}

@media(prefers-reduced-motion:reduce) {
  *,*::before,*::after {
    scroll-behavior:auto !important;
    animation-duration:.01ms !important;
    animation-iteration-count:1 !important;
    transition-duration:.01ms !important;
  }
}
</style>
</head>

<body>

<div id="progress"></div>

<div class="background">
  <div class="grid"></div>
  <div class="orb one"></div>
  <div class="orb two"></div>
</div>

<canvas id="particles"></canvas>

<div class="cursor"></div>
<div class="cursor-dot"></div>

<header id="header">
  <nav class="nav">

    <a href="#home" class="logo">NOBITA<span>.</span></a>

    <div class="nav-links" id="navLinks">
      <a href="#home">HOME</a>
      <a href="#about">ABOUT</a>
      <a href="#skills">SKILLS</a>
      <a href="#projects">PROJECTS</a>
      <a href="#journey">JOURNEY</a>
      <a href="#contact">CONTACT</a>
    </div>

    <div class="nav-actions">
      <button class="sound-btn" id="soundBtn">♪ SOUND OFF</button>
      <button class="menu-btn" id="menuBtn">☰</button>
    </div>

  </nav>
</header>

<main>

<!-- HERO -->

<section class="hero container" id="home">

  <div class="hero-content">

    <div class="status">
      <span class="status-dot"></span>
      AVAILABLE FOR LEARNING & BUILDING
    </div>

    <div class="eyebrow">INDEPENDENT DIGITAL CREATOR</div>

    <h1>
      BUILDING<br>
      <span class="gradient-text">THE FUTURE.</span>
    </h1>

    <p class="hero-role">
      Creative Developer <span style="color:#38bdf8">/</span>
      Digital Explorer <span style="color:#38bdf8">/</span>
      Problem Solver
    </p>

    <p class="hero-description">
      I turn curiosity into creativity and ideas into digital experiences.
      Exploring technology, experimenting with design and building something
      better every day.
    </p>

    <div class="hero-buttons">
      <a href="#projects" class="btn btn-primary magnetic">
        EXPLORE PROJECTS <span>↗</span>
      </a>

      <a href="#about" class="btn btn-outline magnetic">
        DISCOVER MORE <span>↓</span>
      </a>
    </div>

    <div class="hero-meta">

      <div class="meta-item">
        <strong>01</strong>
        <span>MINDSET / CREATE</span>
      </div>

      <div class="meta-item">
        <strong>∞</strong>
        <span>CURIOSITY / LEVEL</span>
      </div>

      <div class="meta-item">
        <strong id="clock">--:--:--</strong>
        <span>LOCAL TIME</span>
      </div>

    </div>

  </div>

  <div class="scroll-indicator">SCROLL TO EXPLORE</div>

</section>

<!-- ABOUT -->

<section class="section container" id="about">

  <div class="reveal">
    <div class="eyebrow">01 / ABOUT ME</div>
    <h2 class="section-title">Beyond the <span class="gradient-text">ordinary.</span></h2>
    <p class="section-desc">
      A mindset built around curiosity, creativity and continuous improvement.
    </p>
  </div>

  <div class="about-grid">

    <div class="about-text reveal">

      <p>
        Hello, I'm <strong style="color:#fff">Nobita</strong>.
        I'm passionate about technology and the endless possibilities
        that come with creating something from nothing.
      </p>

      <p>
        My journey is about learning how things work, experimenting
        with new ideas and developing the skills to build meaningful
        digital experiences.
      </p>

      <p>
        I believe great work comes from curiosity, consistency and
        the courage to keep improving.
      </p>

    </div>

    <div class="terminal reveal">

      <div class="terminal-head">
        <i></i><i></i><i></i>
        <span class="terminal-label">nobita@digital-world ~</span>
      </div>

      <div class="terminal-body">
        <div><span class="command">visitor@world:</span> whoami</div>
        <div class="value">Creative Developer</div>
        <br>
        <div><span class="command">visitor@world:</span> mission</div>
        <div class="value">Build. Learn. Improve.</div>
        <br>
        <div><span class="command">visitor@world:</span> status</div>
        <div class="success">● Online & Learning</div>
        <br>
        <div><span class="command">visitor@world:</span> _</div>
      </div>

    </div>

  </div>

</section>

<!-- SKILLS -->

<section class="section container" id="skills">

  <div class="reveal">
    <div class="eyebrow">02 / EXPERTISE</div>
    <h2 class="section-title">My digital <span class="gradient-text">toolkit.</span></h2>
    <p class="section-desc">
      Technologies and creative disciplines I'm exploring and developing.
    </p>
  </div>

  <div class="skills-grid">

    <div class="skill-card reveal">
      <div class="skill-icon">⌘</div>
      <h3>Frontend Development</h3>
      <p>Creating responsive interfaces and interactive web experiences.</p>
    </div>

    <div class="skill-card reveal">
      <div class="skill-icon">◈</div>
      <h3>Web Design</h3>
      <p>Exploring modern layouts, typography, visual systems and usability.</p>
    </div>

    <div class="skill-card reveal">
      <div class="skill-icon">⟨/⟩</div>
      <h3>Programming</h3>
      <p>Learning programming concepts and building logical solutions.</p>
    </div>

    <div class="skill-card reveal">
      <div class="skill-icon">✳</div>
      <h3>Creative Thinking</h3>
      <p>Turning ideas into structured concepts and digital products.</p>
    </div>

    <div class="skill-card reveal">
      <div class="skill-icon">⌬</div>
      <h3>Problem Solving</h3>
      <p>Breaking complex challenges into smaller, manageable steps.</p>
    </div>

    <div class="skill-card reveal">
      <div class="skill-icon">↗</div>
      <h3>Continuous Learning</h3>
      <p>Exploring new tools, technologies and better ways to work.</p>
    </div>

  </div>

</section>

<!-- PROJECTS -->

<section class="section container" id="projects">

  <div class="reveal">
    <div class="eyebrow">03 / SELECTED WORK</div>
    <h2 class="section-title">Ideas into <span class="gradient-text">reality.</span></h2>
    <p class="section-desc">
      A collection of experiments, concepts and projects.
    </p>
  </div>

  <div class="projects-grid">

    <a class="project-card reveal" href="https://github.com/nobita-devcs">
      <span class="project-number">PROJECT / 001</span>
      <span class="project-arrow">↗</span>
      <h3>Digital Experience</h3>
      <p>A creative space for exploring modern web design and interactive experiences.</p>
      <div class="project-tags">
        <span>HTML</span><span>CSS</span><span>DESIGN</span>
      </div>
    </a>

    <a class="project-card reveal" href="https://github.com/nobita-devcs">
      <span class="project-number">PROJECT / 002</span>
      <span class="project-arrow">↗</span>
      <h3>Creative Experiments</h3>
      <p>Exploring new concepts, creative ideas and frontend possibilities.</p>
      <div class="project-tags">
        <span>JAVASCRIPT</span><span>UI</span><span>EXPERIMENTAL</span>
      </div>
    </a>

    <a class="project-card reveal" href="https://github.com/nobita-devcs">
      <span class="project-number">PROJECT / 003</span>
      <span class="project-arrow">↗</span>
      <h3>Developer Toolkit</h3>
      <p>A collection of learning projects and useful development experiments.</p>
      <div class="project-tags">
        <span>TOOLS</span><span>CODE</span><span>LEARNING</span>
      </div>
    </a>

    <a class="project-card reveal" href="https://github.com/nobita-devcs">
      <span class="project-number">PROJECT / 004</span>
      <span class="project-arrow">↗</span>
      <h3>Future Projects</h3>
      <p>More ideas are in progress. The next creation is always around the corner.</p>
      <div class="project-tags">
        <span>COMING SOON</span><span>BUILDING</span>
      </div>
    </a>

  </div>

  <div class="reveal" style="margin-top:30px">
    <a class="btn btn-outline" href="https://github.com/nobita-devcs?tab=repositories">
      VIEW ALL REPOSITORIES ↗
    </a>
  </div>

</section>

<!-- JOURNEY -->

<section class="section container" id="journey">

  <div class="reveal">
    <div class="eyebrow">04 / THE JOURNEY</div>
    <h2 class="section-title">Always <span class="gradient-text">evolving.</span></h2>
    <p class="section-desc">
      Every step forward is part of the process.
    </p>
  </div>

  <div class="timeline reveal">

    <div class="timeline-item">
      <span>PHASE / 01</span>
      <h3>Discover</h3>
      <p>Exploring technology and discovering the world of development.</p>
    </div>

    <div class="timeline-item">
      <span>PHASE / 02</span>
      <h3>Learn</h3>
      <p>Building foundations through experimentation and practice.</p>
    </div>

    <div class="timeline-item">
      <span>PHASE / 03</span>
      <h3>Create</h3>
      <p>Turning concepts into real projects and digital experiences.</p>
    </div>

    <div class="timeline-item">
      <span>PHASE / 04</span>
      <h3>Keep Growing</h3>
      <p>Improving, exploring and creating what comes next.</p>
    </div>

  </div>

</section>

<!-- CONTACT -->

<section class="section container" id="contact">

  <div class="reveal">
    <div class="eyebrow">05 / GET IN TOUCH</div>
  </div>

  <div class="contact-box reveal">

    <h3>Let's create something <span class="gradient-text">great.</span></h3>

    <p>
      Have an interesting idea or want to explore my work?
      Visit my GitHub profile and discover what I'm building.
    </p>

    <a class="btn btn-primary" href="https://github.com/nobita-devcs">
      CONNECT ON GITHUB ↗
    </a>

  </div>

</section>

</main>

<footer>
  <div class="container footer-inner">

    <p>© <span id="year"></span> NOBITA. DESIGNED WITH INTENTION.</p>

    <div class="footer-links">
      <a href="#home">BACK TO TOP ↑</a>
      <a href="https://github.com/nobita-devcs">GITHUB ↗</a>
    </div>

  </div>
</footer>

<div class="toast" id="toast">INTERACTION ACTIVATED</div>

<script>
/* NAVIGATION */

const header = document.getElementById("header");
const menuBtn = document.getElementById("menuBtn");
const navLinks = document.getElementById("navLinks");

menuBtn.addEventListener("click", () => {
  navLinks.classList.toggle("open");
  menuBtn.textContent = navLinks.classList.contains("open") ? "✕" : "☰";
});

document.querySelectorAll(".nav-links a").forEach(link => {
  link.addEventListener("click", () => {
    navLinks.classList.remove("open");
    menuBtn.textContent = "☰";
  });
});

/* SCROLL PROGRESS + HEADER */

window.addEventListener("scroll", () => {
  const scrollable = document.documentElement.scrollHeight - window.innerHeight;
  const progress = scrollable > 0 ? (window.scrollY / scrollable) * 100 : 0;

  document.getElementById("progress").style.width = progress + "%";
  header.classList.toggle("scrolled", window.scrollY > 30);
});

/* REVEAL ANIMATIONS */

const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if(entry.isIntersecting) {
      entry.target.classList.add("visible");
      observer.unobserve(entry.target);
    }
  });
}, { threshold:0.12 });

document.querySelectorAll(".reveal").forEach(el => observer.observe(el));

/* LIVE CLOCK */

function updateClock() {
  document.getElementById("clock").textContent =
    new Date().toLocaleTimeString();
}

setInterval(updateClock,1000);
updateClock();

document.getElementById("year").textContent = new Date().getFullYear();

/* CUSTOM CURSOR */

const cursor = document.querySelector(".cursor");
const dot = document.querySelector(".cursor-dot");

let mouseX = 0, mouseY = 0;
let cursorX = 0, cursorY = 0;

window.addEventListener("mousemove", e => {
  mouseX = e.clientX;
  mouseY = e.clientY;
  dot.style.left = mouseX + "px";
  dot.style.top = mouseY + "px";
});

function animateCursor() {
  cursorX += (mouseX - cursorX) * .16;
  cursorY += (mouseY - cursorY) * .16;
  cursor.style.left = cursorX + "px";
  cursor.style.top = cursorY + "px";
  requestAnimationFrame(animateCursor);
}

animateCursor();

document.querySelectorAll("a,button").forEach(el => {
  el.addEventListener("mouseenter", () => cursor.classList.add("active"));
  el.addEventListener("mouseleave", () => cursor.classList.remove("active"));
});

/* PARTICLE NETWORK */

const canvas = document.getElementById("particles");
const ctx = canvas.getContext("2d");

let particles = [];
let width = 0;
let height = 0;

function resizeCanvas() {
  const dpr = Math.min(window.devicePixelRatio || 1, 2);
  width = window.innerWidth;
  height = window.innerHeight;

  canvas.width = width * dpr;
  canvas.height = height * dpr;
  canvas.style.width = width + "px";
  canvas.style.height = height + "px";

  ctx.setTransform(dpr,0,0,dpr,0,0);

  const count = Math.min(65, Math.floor(width / 18));

  particles = Array.from({length:count}, () => ({
    x:Math.random()*width,
    y:Math.random()*height,
    vx:(Math.random()-.5)*.35,
    vy:(Math.random()-.5)*.35,
    radius:Math.random()*1.5+.5
  }));
}

function drawParticles() {
  ctx.clearRect(0,0,width,height);

  for(let i=0;i<particles.length;i++) {
    const p = particles[i];

    p.x += p.vx;
    p.y += p.vy;

    if(p.x < 0 || p.x > width) p.vx *= -1;
    if(p.y < 0 || p.y > height) p.vy *= -1;

    ctx.beginPath();
    ctx.arc(p.x,p.y,p.radius,0,Math.PI*2);
    ctx.fillStyle = "rgba(103,232,249,.55)";
    ctx.fill();

    for(let j=i+1;j<particles.length;j++) {
      const q = particles[j];
      const dx = p.x-q.x;
      const dy = p.y-q.y;
      const distance = Math.sqrt(dx*dx+dy*dy);

      if(distance < 115) {
        ctx.beginPath();
        ctx.moveTo(p.x,p.y);
        ctx.lineTo(q.x,q.y);
        ctx.strokeStyle = `rgba(56,189,248,${.12*(1-distance/115)})`;
        ctx.lineWidth = .7;
        ctx.stroke();
      }
    }
  }

  requestAnimationFrame(drawParticles);
}

resizeCanvas();
drawParticles();

window.addEventListener("resize",resizeCanvas);

/* OPTIONAL SYNTHETIC SOUND EFFECTS */

let soundEnabled = false;
let audioContext = null;

const soundBtn = document.getElementById("soundBtn");

soundBtn.addEventListener("click", async () => {
  soundEnabled = !soundEnabled;

  if(soundEnabled) {
    const AudioContext = window.AudioContext || window.webkitAudioContext;

    if(!AudioContext) {
      soundEnabled = false;
      showToast("AUDIO NOT SUPPORTED");
      return;
    }

    audioContext = audioContext || new AudioContext();
    await audioContext.resume();

    soundBtn.textContent = "♪ SOUND ON";
    playTone(620,.07);
  } else {
    soundBtn.textContent = "♪ SOUND OFF";
  }
});

function playTone(frequency,duration) {
  if(!soundEnabled || !audioContext) return;

  const oscillator = audioContext.createOscillator();
  const gain = audioContext.createGain();

  oscillator.type = "sine";
  oscillator.frequency.value = frequency;

  gain.gain.setValueAtTime(.025,audioContext.currentTime);
  gain.gain.exponentialRampToValueAtTime(.001,audioContext.currentTime+duration);

  oscillator.connect(gain);
  gain.connect(audioContext.destination);

  oscillator.start();
  oscillator.stop(audioContext.currentTime+duration);
}

document.querySelectorAll(".btn,.project-card,.nav-links a").forEach(el => {
  el.addEventListener("click", () => playTone(480,.045));
});

/* TOAST */

let toastTimer;

function showToast(message) {
  const toast = document.getElementById("toast");
  toast.textContent = message;
  toast.classList.add("show");

  clearTimeout(toastTimer);

  toastTimer = setTimeout(() => {
    toast.classList.remove("show");
  },1800);
}

/* MAGNETIC BUTTON EFFECT */

document.querySelectorAll(".magnetic").forEach(button => {
  button.addEventListener("mousemove",e => {
    if(window.matchMedia("(hover: none)").matches) return;

    const rect = button.getBoundingClientRect();
    const x = e.clientX - rect.left - rect.width/2;
    const y = e.clientY - rect.top - rect.height/2;

    button.style.transform = `translate(${x*.12}px,${y*.12}px)`;
  });

  button.addEventListener("mouseleave",() => {
    button.style.transform = "";
  });
});

/* ACTIVE NAVIGATION */

const sections = document.querySelectorAll("main section[id]");
const navItems = document.querySelectorAll(".nav-links a");

const sectionObserver = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if(entry.isIntersecting) {
      navItems.forEach(link => {
        link.classList.toggle(
          "active",
          link.getAttribute("href") === "#" + entry.target.id
        );
      });
    }
  });
},{rootMargin:"-35% 0px -55% 0px"});

sections.forEach(section => sectionObserver.observe(section));

/* REDUCED MOTION SUPPORT */

if(window.matchMedia("(prefers-reduced-motion: reduce)").matches) {
  canvas.style.display = "none";
}
</script>

</body>
</html>

























