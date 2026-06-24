<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mohammed Ayman — Frontend Developer</title>
<meta name="description" content="Mohammed Ayman — Frontend Developer specializing in Next.js, React & TypeScript. Building high-performance, production-ready web applications.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0b0d10;
    --surface:#13161b;
    --surface-2:#171b21;
    --border:#1f242c;
    --border-soft:#1a1e25;
    --amber:#e7b249;
    --amber-dim:#9a7836;
    --text:#f0f2f5;
    --text-dim:#8b95a3;
    --text-faint:#565f6b;
    --green:#6fcf97;
    --font-display:'Space Grotesk', sans-serif;
    --font-body:'Inter', sans-serif;
    --font-mono:'JetBrains Mono', monospace;
  }

  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}

  @media (prefers-reduced-motion: reduce){
    html{scroll-behavior:auto;}
    *{animation-duration:0.01ms !important; animation-iteration-count:1 !important; transition-duration:0.01ms !important;}
  }

  body{
    background:var(--bg);
    color:var(--text);
    font-family:var(--font-body);
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
  }

  body::before{
    content:'';
    position:fixed;
    inset:0;
    background-image:
      linear-gradient(rgba(231,178,73,0.025) 1px, transparent 1px),
      linear-gradient(90deg, rgba(231,178,73,0.025) 1px, transparent 1px);
    background-size:64px 64px;
    pointer-events:none;
    z-index:0;
    mask-image:radial-gradient(ellipse 80% 50% at 50% 0%, black 40%, transparent 90%);
  }

  a{color:inherit; text-decoration:none;}
  ::selection{background:var(--amber); color:#000;}

  :focus-visible{
    outline:2px solid var(--amber);
    outline-offset:3px;
    border-radius:2px;
  }

  .wrap{
    max-width:920px;
    margin:0 auto;
    padding:0 28px;
    position:relative;
    z-index:1;
  }

  /* ---------- NAV ---------- */
  nav{
    position:sticky;
    top:0;
    z-index:50;
    background:rgba(11,13,16,0.82);
    backdrop-filter:blur(10px);
    border-bottom:1px solid var(--border-soft);
  }
  .nav-inner{
    max-width:920px;
    margin:0 auto;
    padding:18px 28px;
    display:flex;
    align-items:center;
    justify-content:space-between;
  }
  .logo{
    font-family:var(--font-mono);
    font-size:14px;
    font-weight:500;
    color:var(--text);
    display:flex;
    align-items:center;
    gap:8px;
  }
  .logo .dot{
    width:7px; height:7px;
    border-radius:50%;
    background:var(--green);
    box-shadow:0 0 8px rgba(111,207,151,0.7);
    flex-shrink:0;
  }
  .nav-links{
    display:flex;
    gap:28px;
    font-family:var(--font-mono);
    font-size:13px;
    color:var(--text-dim);
  }
  .nav-links a{transition:color .15s ease;}
  .nav-links a:hover{color:var(--amber);}
  .nav-links .num{color:var(--text-faint); margin-right:4px;}

  @media (max-width:640px){
    .nav-links{display:none;}
  }

  /* ---------- HERO ---------- */
  header.hero{
    padding:88px 0 64px;
    position:relative;
  }
  .eyebrow{
    font-family:var(--font-mono);
    font-size:13px;
    color:var(--amber);
    letter-spacing:0.02em;
    margin-bottom:22px;
    display:flex;
    align-items:center;
    gap:10px;
  }
  .eyebrow .path{color:var(--text-faint);}

  .terminal{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:8px;
    overflow:hidden;
    margin-bottom:36px;
    box-shadow:0 20px 60px -20px rgba(0,0,0,0.6);
  }
  .terminal-bar{
    display:flex;
    align-items:center;
    gap:8px;
    padding:11px 16px;
    background:var(--surface-2);
    border-bottom:1px solid var(--border);
  }
  .terminal-bar span{width:10px; height:10px; border-radius:50%; display:inline-block;}
  .terminal-bar span:nth-child(1){background:#4a4f57;}
  .terminal-bar span:nth-child(2){background:#4a4f57;}
  .terminal-bar span:nth-child(3){background:#4a4f57;}
  .terminal-bar .title{
    font-family:var(--font-mono);
    font-size:12px;
    color:var(--text-faint);
    margin-left:6px;
  }
  .terminal-body{
    padding:22px 24px 26px;
    font-family:var(--font-mono);
    font-size:14px;
    line-height:1.85;
  }
  .t-line{color:var(--text-dim); opacity:0; animation:reveal 0.4s ease forwards;}
  .t-line .prompt{color:var(--green); margin-right:8px;}
  .t-line .key{color:var(--text-faint);}
  .t-line .val{color:var(--text);}
  .t-line.delay1{animation-delay:0.15s;}
  .t-line.delay2{animation-delay:0.45s;}
  .t-line.delay3{animation-delay:0.75s;}
  .t-line.delay4{animation-delay:1.05s;}
  .t-line.delay5{animation-delay:1.35s;}
  .t-line.delay6{animation-delay:1.65s;}
  @keyframes reveal{
    from{opacity:0; transform:translateY(3px);}
    to{opacity:1; transform:translateY(0);}
  }
  @media (prefers-reduced-motion: reduce){
    .t-line{opacity:1; animation:none;}
  }

  .name-block h1{
    font-family:var(--font-display);
    font-size:clamp(38px, 6vw, 58px);
    font-weight:700;
    letter-spacing:-0.02em;
    line-height:1.05;
    color:var(--text);
    margin-bottom:14px;
  }
  .name-block h1 .accent{color:var(--amber);}
  .name-block p.role{
    font-size:18px;
    color:var(--text-dim);
    max-width:560px;
    margin-bottom:32px;
  }
  .name-block p.role strong{color:var(--text); font-weight:600;}

  .hero-actions{
    display:flex;
    gap:14px;
    flex-wrap:wrap;
    margin-bottom:40px;
  }
  .btn{
    font-family:var(--font-mono);
    font-size:13px;
    padding:11px 20px;
    border-radius:6px;
    border:1px solid var(--border);
    transition:all .15s ease;
    display:inline-flex;
    align-items:center;
    gap:8px;
  }
  .btn-primary{
    background:var(--amber);
    color:#16140c;
    border-color:var(--amber);
    font-weight:600;
  }
  .btn-primary:hover{background:#f3c264; transform:translateY(-1px);}
  .btn-ghost{
    color:var(--text-dim);
    background:transparent;
  }
  .btn-ghost:hover{border-color:var(--amber-dim); color:var(--text);}

  .meta-row{
    display:flex;
    gap:22px;
    flex-wrap:wrap;
    font-family:var(--font-mono);
    font-size:13px;
    color:var(--text-faint);
  }
  .meta-row span{display:flex; align-items:center; gap:7px;}

  /* ---------- SECTION LABELS ---------- */
  .section{padding:64px 0;}
  .section + .section{border-top:1px solid var(--border-soft);}
  .section-head{
    display:flex;
    align-items:baseline;
    gap:14px;
    margin-bottom:40px;
  }
  .section-tag{
    font-family:var(--font-mono);
    font-size:13px;
    color:var(--text-faint);
    white-space:nowrap;
  }
  .section-tag .slash{color:var(--amber-dim);}
  .section-head h2{
    font-family:var(--font-display);
    font-size:28px;
    font-weight:600;
    color:var(--text);
  }
  .section-head .rule{
    flex:1;
    height:1px;
    background:var(--border);
  }

  /* ---------- ABOUT ---------- */
  .about-grid{
    display:grid;
    grid-template-columns:1.4fr 1fr;
    gap:48px;
  }
  @media (max-width:720px){
    .about-grid{grid-template-columns:1fr;}
  }
  .about-text p{
    color:var(--text-dim);
    font-size:15.5px;
    margin-bottom:16px;
    max-width:520px;
  }
  .about-text strong{color:var(--text); font-weight:600;}

  .focus-list{
    display:flex;
    flex-direction:column;
    gap:14px;
  }
  .focus-item{
    border:1px solid var(--border);
    border-radius:8px;
    padding:14px 16px;
    background:var(--surface);
  }
  .focus-item .f-label{
    font-family:var(--font-mono);
    font-size:11px;
    color:var(--amber);
    letter-spacing:0.04em;
    margin-bottom:4px;
  }
  .focus-item .f-val{
    font-size:14px;
    color:var(--text-dim);
  }

  /* ---------- STACK ---------- */
  .stack-grid{
    display:grid;
    grid-template-columns:repeat(3, 1fr);
    gap:1px;
    background:var(--border);
    border:1px solid var(--border);
    border-radius:10px;
    overflow:hidden;
  }
  @media (max-width:720px){
    .stack-grid{grid-template-columns:repeat(2, 1fr);}
  }
  @media (max-width:480px){
    .stack-grid{grid-template-columns:1fr;}
  }
  .stack-cell{
    background:var(--surface);
    padding:22px 22px 24px;
  }
  .stack-cell .s-num{
    font-family:var(--font-mono);
    font-size:11px;
    color:var(--text-faint);
    margin-bottom:10px;
    display:block;
  }
  .stack-cell h3{
    font-family:var(--font-display);
    font-size:16px;
    font-weight:600;
    color:var(--text);
    margin-bottom:12px;
  }
  .tag-row{
    display:flex;
    flex-wrap:wrap;
    gap:6px;
  }
  .tag{
    font-family:var(--font-mono);
    font-size:12px;
    color:var(--text-dim);
    background:var(--surface-2);
    border:1px solid var(--border);
    padding:4px 9px;
    border-radius:5px;
  }

  /* ---------- EXPERIENCE ---------- */
  .exp-item{
    border-left:2px solid var(--border);
    padding-left:28px;
    position:relative;
    margin-bottom:48px;
  }
  .exp-item:last-child{margin-bottom:0;}
  .exp-item::before{
    content:'';
    position:absolute;
    left:-5px;
    top:4px;
    width:8px;
    height:8px;
    border-radius:50%;
    background:var(--amber);
    box-shadow:0 0 0 4px var(--bg), 0 0 12px rgba(231,178,73,0.5);
  }
  .exp-head{
    display:flex;
    justify-content:space-between;
    align-items:flex-start;
    gap:16px;
    margin-bottom:6px;
    flex-wrap:wrap;
  }
  .exp-head h3{
    font-family:var(--font-display);
    font-size:19px;
    font-weight:600;
    color:var(--text);
  }
  .exp-head .exp-date{
    font-family:var(--font-mono);
    font-size:12px;
    color:var(--amber);
    white-space:nowrap;
    padding-top:3px;
  }
  .exp-org{
    font-size:14px;
    color:var(--text-dim);
    margin-bottom:6px;
  }
  .exp-stack{
    font-family:var(--font-mono);
    font-size:12px;
    color:var(--text-faint);
    margin-bottom:16px;
  }
  .exp-list{
    list-style:none;
    display:flex;
    flex-direction:column;
    gap:10px;
  }
  .exp-list li{
    font-size:14.5px;
    color:var(--text-dim);
    padding-left:18px;
    position:relative;
  }
  .exp-list li::before{
    content:'→';
    position:absolute;
    left:0;
    color:var(--amber-dim);
    font-size:13px;
  }
  .exp-list li strong{color:var(--text); font-weight:600;}

  /* ---------- PROJECTS ---------- */
  .project-card{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:10px;
    padding:28px;
    margin-bottom:24px;
    transition:border-color .15s ease;
  }
  .project-card:hover{border-color:var(--amber-dim);}
  .project-card:last-child{margin-bottom:0;}
  .project-top{
    display:flex;
    justify-content:space-between;
    align-items:flex-start;
    gap:16px;
    margin-bottom:6px;
    flex-wrap:wrap;
  }
  .project-top h3{
    font-family:var(--font-display);
    font-size:21px;
    font-weight:600;
    color:var(--text);
  }
  .project-links{
    display:flex;
    gap:10px;
    flex-shrink:0;
  }
  .project-links a{
    font-family:var(--font-mono);
    font-size:12px;
    color:var(--text-dim);
    border:1px solid var(--border);
    padding:6px 12px;
    border-radius:5px;
    transition:all .15s ease;
    display:inline-flex;
    align-items:center;
    gap:6px;
  }
  .project-links a:hover{color:var(--amber); border-color:var(--amber-dim);}
  .project-tagline{
    font-size:14px;
    color:var(--amber);
    font-family:var(--font-mono);
    margin-bottom:14px;
  }
  .project-card ul{
    list-style:none;
    display:flex;
    flex-direction:column;
    gap:9px;
    margin-bottom:16px;
  }
  .project-card ul li{
    font-size:14.5px;
    color:var(--text-dim);
    padding-left:18px;
    position:relative;
  }
  .project-card ul li::before{
    content:'·';
    position:absolute;
    left:2px;
    color:var(--text-faint);
    font-size:20px;
    line-height:0.6;
  }
  .project-card ul li strong{color:var(--text); font-weight:600;}
  .project-stack{
    display:flex;
    flex-wrap:wrap;
    gap:6px;
  }

  /* ---------- EDUCATION + CERTS ---------- */
  .edu-cert-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:40px;
  }
  @media (max-width:720px){
    .edu-cert-grid{grid-template-columns:1fr;}
  }
  .edu-block h3{
    font-family:var(--font-display);
    font-size:17px;
    font-weight:600;
    color:var(--text);
    margin-bottom:6px;
  }
  .edu-block .edu-org{font-size:14px; color:var(--text-dim); margin-bottom:4px;}
  .edu-block .edu-meta{font-family:var(--font-mono); font-size:12px; color:var(--text-faint);}
  .edu-block .gpa{
    display:inline-block;
    margin-top:12px;
    font-family:var(--font-mono);
    font-size:12px;
    color:var(--amber);
    border:1px solid var(--amber-dim);
    padding:4px 10px;
    border-radius:5px;
  }

  .cert-list{display:flex; flex-direction:column; gap:16px;}
  .cert-item{
    display:flex;
    justify-content:space-between;
    align-items:baseline;
    gap:12px;
    padding-bottom:14px;
    border-bottom:1px solid var(--border-soft);
  }
  .cert-item:last-child{border-bottom:none; padding-bottom:0;}
  .cert-name{font-size:14px; color:var(--text);}
  .cert-org{font-size:12.5px; color:var(--text-faint); display:block; margin-top:2px;}
  .cert-date{
    font-family:var(--font-mono);
    font-size:11.5px;
    color:var(--text-faint);
    white-space:nowrap;
  }

  /* ---------- CONTACT / FOOTER ---------- */
  footer{
    padding:72px 0 48px;
    text-align:center;
  }
  footer .f-eyebrow{
    font-family:var(--font-mono);
    font-size:13px;
    color:var(--amber);
    margin-bottom:18px;
  }
  footer h2{
    font-family:var(--font-display);
    font-size:clamp(28px, 4vw, 40px);
    font-weight:700;
    color:var(--text);
    margin-bottom:18px;
    letter-spacing:-0.01em;
  }
  footer p{
    color:var(--text-dim);
    max-width:440px;
    margin:0 auto 32px;
    font-size:15px;
  }
  .contact-row{
    display:flex;
    justify-content:center;
    gap:14px;
    flex-wrap:wrap;
    margin-bottom:44px;
  }
  .footer-meta{
    font-family:var(--font-mono);
    font-size:12px;
    color:var(--text-faint);
    border-top:1px solid var(--border-soft);
    padding-top:28px;
  }
  .footer-meta .dot{color:var(--amber-dim); margin:0 8px;}

  @media (max-width:600px){
    header.hero{padding:56px 0 44px;}
    .section{padding:48px 0;}
    .terminal-body{font-size:12.5px; padding:18px 16px 20px;}
    .name-block h1{font-size:34px;}
  }
</style>
</head>
<body>

<nav>
  <div class="nav-inner">
    <div class="logo"><span class="dot"></span>mohammed.ayman</div>
    <div class="nav-links">
      <a href="#about"><span class="num">01</span>about</a>
      <a href="#stack"><span class="num">02</span>stack</a>
      <a href="#experience"><span class="num">03</span>experience</a>
      <a href="#projects"><span class="num">04</span>projects</a>
      <a href="#contact"><span class="num">05</span>contact</a>
    </div>
  </div>
</nav>

<div class="wrap">

  <header class="hero">
    <div class="eyebrow"><span class="path">~/portfolio</span> — frontend engineer, cairo eg</div>

    <div class="terminal">
      <div class="terminal-bar">
        <span></span><span></span><span></span>
        <span class="title">profile.sh</span>
      </div>
      <div class="terminal-body">
        <div class="t-line delay1"><span class="prompt">$</span> whoami --verbose</div>
        <div class="t-line delay2"><span class="key">name:</span> <span class="val">Mohammed Ayman</span></div>
        <div class="t-line delay3"><span class="key">role:</span> <span class="val">Frontend Developer — React / Next.js</span></div>
        <div class="t-line delay4"><span class="key">status:</span> <span class="val">open to freelance &amp; full-time roles</span></div>
        <div class="t-line delay5"><span class="key">stack:</span> <span class="val">TypeScript · Prisma · PostgreSQL · Tailwind</span></div>
        <div class="t-line delay6"><span class="prompt">$</span> <span style="opacity:0.6">_</span></div>
      </div>
    </div>

    <div class="name-block">
      <h1>Building interfaces<br>that <span class="accent">don't break</span> under pressure.</h1>
      <p class="role">Frontend specialist focused on <strong>Next.js</strong> and <strong>TypeScript</strong>, with a full-stack foundation in <strong>Prisma</strong> and <strong>PostgreSQL</strong>. I care about what happens when two users click "book" at the same time.</p>
    </div>

    <div class="hero-actions">
      <a class="btn btn-primary" href="#contact">Get in touch</a>
      <a class="btn btn-ghost" href="https://github.com/m7medA" target="_blank" rel="noopener">View GitHub ↗</a>
      <a class="btn btn-ghost" href="https://www.linkedin.com/in/mohammed-ayman-910706268/" target="_blank" rel="noopener">LinkedIn ↗</a>
    </div>

    <div class="meta-row">
      <span>📍 Cairo, Egypt</span>
      <span>✉️ mohammedayman2534@gmail.com</span>
      <span>🎓 CS &amp; AI, Benha University — 2026</span>
    </div>
  </header>

  <section class="section" id="about">
    <div class="section-head">
      <span class="section-tag"><span class="slash">/</span>01</span>
      <h2>About</h2>
      <span class="rule"></span>
    </div>
    <div class="about-grid">
      <div class="about-text">
        <p>I'm a Computer Science &amp; AI graduate from Benha University and a frontend developer who ended up doing a lot of backend thinking along the way. Most of my work lives in <strong>Next.js and TypeScript</strong>, but the problems I enjoy most sit at the seams — booking systems that can't double-sell a room, payment flows that can't be tampered with after the fact, caches that have to be right or invisible.</p>
        <p>Currently building <strong>CallMe Mobility</strong>, a car rental &amp; sales platform for a client in Spain, where I'm responsible for performance, concurrency, and the booking pipeline end to end. Before that, I led a cross-functional team during the <strong>Dragon Tech</strong> internship program to a "Best Performing Team" award.</p>
      </div>
      <div class="focus-list">
        <div class="focus-item">
          <div class="f-label">CURRENTLY</div>
          <div class="f-val">Freelance full-stack dev, remote (Spain)</div>
        </div>
        <div class="focus-item">
          <div class="f-label">FOCUSED ON</div>
          <div class="f-val">Performance, concurrency, clean architecture</div>
        </div>
        <div class="focus-item">
          <div class="f-label">GRADUATING</div>
          <div class="f-val">June 2026 — GPA 3.3</div>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="stack">
    <div class="section-head">
      <span class="section-tag"><span class="slash">/</span>02</span>
      <h2>Stack</h2>
      <span class="rule"></span>
    </div>
    <div class="stack-grid">
      <div class="stack-cell">
        <span class="s-num">001</span>
        <h3>Core Languages</h3>
        <div class="tag-row">
          <span class="tag">TypeScript</span>
          <span class="tag">JavaScript ES6+</span>
          <span class="tag">Python</span>
          <span class="tag">C++</span>
        </div>
      </div>
      <div class="stack-cell">
        <span class="s-num">010</span>
        <h3>Frontend</h3>
        <div class="tag-row">
          <span class="tag">React.js</span>
          <span class="tag">Next.js</span>
          <span class="tag">Tailwind CSS</span>
          <span class="tag">Framer Motion</span>
          <span class="tag">shadcn/ui</span>
        </div>
      </div>
      <div class="stack-cell">
        <span class="s-num">011</span>
        <h3>State &amp; Data</h3>
        <div class="tag-row">
          <span class="tag">Redux Toolkit</span>
          <span class="tag">React Query</span>
          <span class="tag">Context API</span>
        </div>
      </div>
      <div class="stack-cell">
        <span class="s-num">100</span>
        <h3>Backend &amp; Data</h3>
        <div class="tag-row">
          <span class="tag">Prisma ORM</span>
          <span class="tag">PostgreSQL</span>
          <span class="tag">Supabase</span>
          <span class="tag">Zod</span>
          <span class="tag">Stripe</span>
        </div>
      </div>
      <div class="stack-cell">
        <span class="s-num">101</span>
        <h3>UI / UX</h3>
        <div class="tag-row">
          <span class="tag">Accessibility (ARIA)</span>
          <span class="tag">Responsive Design</span>
          <span class="tag">Figma</span>
          <span class="tag">Typography</span>
        </div>
      </div>
      <div class="stack-cell">
        <span class="s-num">110</span>
        <h3>Tooling</h3>
        <div class="tag-row">
          <span class="tag">Git</span>
          <span class="tag">GitHub</span>
          <span class="tag">Vite</span>
          <span class="tag">ESLint</span>
          <span class="tag">Postman</span>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="experience">
    <div class="section-head">
      <span class="section-tag"><span class="slash">/</span>03</span>
      <h2>Experience</h2>
      <span class="rule"></span>
    </div>

    <div class="exp-item">
      <div class="exp-head">
        <h3>Freelance Full-Stack Developer</h3>
        <span class="exp-date">12/2025 — Present</span>
      </div>
      <div class="exp-org">CallMe Mobility — Car Rental &amp; Sales Platform · Remote (Spain)</div>
      <div class="exp-stack">Next.js · TypeScript · Prisma · PostgreSQL · Stripe · Redis</div>
      <ul class="exp-list">
        <li><strong>Performance &amp; ROI:</strong> Integrated Upstash Redis for global caching, added lazy loading, swapped heavy libraries for vanilla JS, and converted assets to WebP — clearing all target Core Web Vitals benchmarks under heavy ad-driven traffic.</li>
        <li><strong>Concurrency control:</strong> Designed a state-driven booking system with a 7-minute server-side resource lock to eliminate race conditions, so two users can never book the same vehicle.</li>
        <li><strong>Booking &amp; payments:</strong> Built a secure booking-session pipeline with Stripe Webhooks that converts temporary sessions into immutable bookings on successful payment, preventing post-booking tampering.</li>
        <li><strong>Reliability:</strong> Resolved email-delivery failures with end-to-end Zod type safety and a reconfigured transactional mailing pipeline — 100% deliverability for confirmations and password resets.</li>
        <li><strong>i18n:</strong> Shipped a production-ready English/Spanish localization layer with memoized rendering (useMemo, useCallback) holding 60fps for the European market.</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-head">
        <h3>Software Engineer Intern — Team Lead</h3>
        <span class="exp-date">08/2025 — 10/2025</span>
      </div>
      <div class="exp-org">Dragon Tech Internship Program</div>
      <div class="exp-stack">React.js · Next.js · Redux Toolkit · TypeScript · Tailwind CSS</div>
      <ul class="exp-list">
        <li><strong>Leadership:</strong> Selected as Team Lead for a cross-functional squad; won "Best Performing Team" by holding the line on code quality and milestone delivery.</li>
        <li><strong>Full-stack range:</strong> Built type-safe frontend layers while extending into backend logic with PostgreSQL and Zod schema validation.</li>
        <li><strong>Collaboration:</strong> Partnered with backend engineers on RESTful API integration and used TanStack Query for efficient data fetching.</li>
      </ul>
    </div>
  </section>

  <section class="section" id="projects">
    <div class="section-head">
      <span class="section-tag"><span class="slash">/</span>04</span>
      <h2>Projects</h2>
      <span class="rule"></span>
    </div>

    <div class="project-card">
      <div class="project-top">
        <h3>WIKIMASTERS</h3>
        <div class="project-links">
          <a href="https://github.com/m7medA" target="_blank" rel="noopener">GitHub ↗</a>
        </div>
      </div>
      <div class="project-tagline">Full-stack article publishing platform</div>
      <ul>
        <li><strong>Independent architecture:</strong> Rebuilt the core stack from a template baseline with Prisma, NextAuth, and LangChain to own the data flow end to end.</li>
        <li><strong>AI pipeline:</strong> Integrated LangChain + Google Gemini to auto-generate semantic summaries for new articles and feed them into the discovery feed.</li>
        <li><strong>Caching:</strong> Cache-first landing pages via Upstash Redis with TTL handling to cut serverless database round-trips.</li>
        <li><strong>Authorization:</strong> Server-side, ownership-based access control so users can only edit their own content.</li>
        <li><strong>Notifications:</strong> Event-driven view-count tracking via Resend API, triggering real-time author emails at engagement thresholds.</li>
      </ul>
      <div class="project-stack">
        <span class="tag">Next.js (App Router)</span>
        <span class="tag">TypeScript</span>
        <span class="tag">Prisma</span>
        <span class="tag">PostgreSQL</span>
        <span class="tag">Redis</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-top">
        <h3>The Wild Oasis</h3>
        <div class="project-links">
          <a href="https://github.com/m7medA" target="_blank" rel="noopener">GitHub ↗</a>
        </div>
      </div>
      <div class="project-tagline">Hotel reservation platform</div>
      <ul>
        <li><strong>Modern architecture:</strong> Built on Next.js 15 with React Server Components and Server Actions for fast renders and clean mutations.</li>
        <li><strong>Optimistic UI:</strong> Used <code>useOptimistic</code> and <code>useFormStatus</code> for instant feedback during booking flows.</li>
        <li><strong>Cache control:</strong> Programmatic invalidation via <code>revalidatePath</code> to keep cabin availability accurate in real time.</li>
        <li><strong>Auth:</strong> Auth.js with Google OAuth for personalized, isolated guest dashboards.</li>
      </ul>
      <div class="project-stack">
        <span class="tag">Next.js 15</span>
        <span class="tag">TypeScript</span>
        <span class="tag">Supabase</span>
        <span class="tag">Auth.js</span>
        <span class="tag">Tailwind CSS</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-top">
        <h3>CallMe Mobility</h3>
        <div class="project-links">
          <a href="https://www.callmemobility.com/en" target="_blank" rel="noopener">Live ↗</a>
        </div>
      </div>
      <div class="project-tagline">Car rental &amp; sales platform — production client work</div>
      <ul>
        <li>Live freelance engagement covering performance, concurrency-safe booking, and Stripe-backed payment automation. Full details in the <a href="#experience" style="color:var(--amber); text-decoration:underline;">Experience</a> section above.</li>
      </ul>
      <div class="project-stack">
        <span class="tag">Next.js</span>
        <span class="tag">TypeScript</span>
        <span class="tag">Prisma</span>
        <span class="tag">PostgreSQL</span>
        <span class="tag">Stripe</span>
      </div>
    </div>
  </section>

  <section class="section" id="education">
    <div class="section-head">
      <span class="section-tag"><span class="slash">/</span>05</span>
      <h2>Education &amp; Certifications</h2>
      <span class="rule"></span>
    </div>
    <div class="edu-cert-grid">
      <div class="edu-block">
        <h3>B.Sc. Computer Science &amp; Artificial Intelligence</h3>
        <div class="edu-org">Benha University — Faculty of Computers and AI</div>
        <div class="edu-meta">Department of Computer Science · 08/2022 — 06/2026</div>
        <span class="gpa">GPA 3.3</span>
      </div>
      <div class="cert-list">
        <div class="cert-item">
          <div>
            <div class="cert-name">Advanced Frontend Specializations</div>
            <span class="cert-org">Frontend Masters</span>
          </div>
          <span class="cert-date">2026</span>
        </div>
        <div class="cert-item">
          <div>
            <div class="cert-name">Professional Front-End Web Engineer</div>
            <span class="cert-org">ALX Africa</span>
          </div>
          <span class="cert-date">04 — 08/2025</span>
        </div>
        <div class="cert-item">
          <div>
            <div class="cert-name">Professional Foundation Program</div>
            <span class="cert-org">ALX Africa</span>
          </div>
          <span class="cert-date">02 — 04/2025</span>
        </div>
        <div class="cert-item">
          <div>
            <div class="cert-name">The Ultimate React Course 2025</div>
            <span class="cert-org">Udemy · Jonas Schmedtmann</span>
          </div>
          <span class="cert-date">2025</span>
        </div>
        <div class="cert-item">
          <div>
            <div class="cert-name">The Complete JavaScript Course 2025</div>
            <span class="cert-org">Udemy · Jonas Schmedtmann</span>
          </div>
          <span class="cert-date">2025</span>
        </div>
        <div class="cert-item">
          <div>
            <div class="cert-name">UI/UX Design Fundamentals</div>
            <span class="cert-org">Yanfa</span>
          </div>
          <span class="cert-date">2025</span>
        </div>
      </div>
    </div>
  </section>

  <footer id="contact">
    <div class="f-eyebrow">~/contact</div>
    <h2>Let's build something<br>that holds up.</h2>
    <p>Open to freelance work and full-time frontend roles. If it involves Next.js, a tricky data layer, or a UI that needs to feel instant — I'm interested.</p>
    <div class="contact-row">
      <a class="btn btn-primary" href="mailto:mohammedayman2534@gmail.com">✉️ mohammedayman2534@gmail.com</a>
      <a class="btn btn-ghost" href="https://github.com/m7medA" target="_blank" rel="noopener">GitHub ↗</a>
      <a class="btn btn-ghost" href="https://www.linkedin.com/in/mohammed-ayman-910706268/" target="_blank" rel="noopener">LinkedIn ↗</a>
    </div>
    <div class="footer-meta">
      Mohammed Ayman <span class="dot">·</span> Cairo, Egypt <span class="dot">·</span> 01130539162
    </div>
  </footer>

</div>

</body>
</html>
