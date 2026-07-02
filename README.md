
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Surya Varathan — Software Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
  :root{
    --white:#ffffff;
    --offwhite:#f5f5f7;
    --black:#000000;
    --ink:#1d1d1f;
    --ink-dim:#86868b;
    --ink-dim2:#6e6e73;
    --blue:#0071e3;
    --blue-dark:#0059b3;
    --line:#d2d2d7;
    --font: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Inter', -apple-system, sans-serif;
  }
 
  *{ margin:0; padding:0; box-sizing:border-box; }
  html{ scroll-behavior:smooth; }
  @media (prefers-reduced-motion: reduce){
    html{ scroll-behavior:auto; }
    *{ animation-duration:0.01ms !important; transition-duration:0.01ms !important; }
  }
 
  body{
    font-family:var(--font);
    color:var(--ink);
    background:var(--white);
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
  }
 
  a{ color:inherit; text-decoration:none; }
  :focus-visible{ outline:2px solid var(--blue); outline-offset:3px; }
 
  /* ---------- NAV ---------- */
  nav{
    position:fixed; top:0; left:0; right:0; z-index:200;
    height:44px; display:flex; align-items:center; justify-content:center;
    background:rgba(255,255,255,0.8); backdrop-filter:saturate(180%) blur(20px);
    border-bottom:1px solid rgba(0,0,0,0.06);
    transition: background .3s ease, border-color .3s ease;
  }
  nav.dark{ background:rgba(0,0,0,0.8); border-bottom-color:rgba(255,255,255,0.08); }
  .nav-inner{
    width:100%; max-width:1024px; padding:0 22px;
    display:flex; align-items:center; justify-content:space-between;
  }
  .nav-logo{ font-size:15px; font-weight:600; letter-spacing:-0.01em; }
  nav.dark .nav-logo{ color:#f5f5f7; }
  .nav-links{ display:flex; gap:30px; }
  .nav-links a{ font-size:12px; font-weight:400; color:var(--ink); opacity:0.85; transition:opacity .2s ease; }
  .nav-links a:hover{ opacity:1; }
  nav.dark .nav-links a{ color:#f5f5f7; }
  @media (max-width:680px){ .nav-links{ gap:16px; } .nav-links a{ font-size:11px; } }
 
  /* ---------- HERO ---------- */
  .hero{
    min-height:100svh; display:flex; flex-direction:column; align-items:center; justify-content:center;
    text-align:center; padding:140px 24px 80px; position:relative; overflow:hidden;
  }
  .orb{
    position:absolute; top:50%; left:50%; width:900px; height:900px;
    transform:translate(-50%,-50%);
    background: conic-gradient(from 0deg, #ff6b6b, #f7b733, #34d399, #4facfe, #a17fe0, #ff6b6b);
    filter: blur(140px); opacity:0.28; border-radius:50%;
    animation: orbit 22s linear infinite;
    z-index:0;
  }
  @keyframes orbit{ 100%{ transform:translate(-50%,-50%) rotate(360deg); } }
 
  .hero-content{ position:relative; z-index:1; }
  .hero .eyebrow{
    font-size:19px; font-weight:600; color:var(--ink-dim2); margin-bottom:8px;
  }
  .hero h1{
    font-size:clamp(46px, 9vw, 104px); font-weight:700; letter-spacing:-0.03em; line-height:1.02;
    background:linear-gradient(180deg, #1d1d1f 0%, #1d1d1f 60%, #6e6e73 100%);
    -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent;
  }
  .hero .sub{
    font-size:clamp(19px, 2.4vw, 27px); font-weight:400; color:var(--ink-dim2);
    margin-top:14px; letter-spacing:-0.01em;
  }
  .hero-cta{ display:flex; gap:16px; margin-top:34px; flex-wrap:wrap; justify-content:center; }
  .pill{
    font-size:17px; font-weight:400; padding:12px 24px; border-radius:980px;
    transition: transform .2s ease, background .2s ease, box-shadow .2s ease;
    display:inline-flex; align-items:center; gap:4px;
  }
  .pill-solid{ background:var(--blue); color:#fff; }
  .pill-solid:hover{ background:var(--blue-dark); transform:scale(1.02); }
  .pill-link{ color:var(--blue); }
  .pill-link:hover{ text-decoration:underline; }
  .pill-link::after{ content:'›'; margin-left:2px; }
 
  .scroll-cue{
    position:absolute; bottom:34px; left:50%; transform:translateX(-50%);
    font-size:12px; color:var(--ink-dim); display:flex; flex-direction:column; align-items:center; gap:8px;
    animation: bob 2s ease-in-out infinite; z-index:1;
  }
  @keyframes bob{ 0%,100%{ transform:translate(-50%,0);} 50%{ transform:translate(-50%,6px);} }
  .scroll-cue .chevron{ width:10px; height:10px; border-right:1.5px solid var(--ink-dim); border-bottom:1.5px solid var(--ink-dim); transform:rotate(45deg); }
 
  /* ---------- STAT SECTION (dark) ---------- */
  .stat-section{
    background:var(--black); color:#f5f5f7; padding:180px 24px;
    text-align:center; position:relative;
  }
  .stat-eyebrow{ font-size:19px; font-weight:600; color:#98989d; margin-bottom:18px; }
  .stat-number{
    font-size:clamp(80px,16vw,220px); font-weight:700; letter-spacing:-0.04em; line-height:0.95;
    display:flex; justify-content:center; align-items:baseline; gap:6px;
  }
  .stat-number .plus{ font-size:0.4em; color:var(--blue); }
  .stat-caption{ font-size:clamp(19px,2.4vw,27px); color:#98989d; margin-top:18px; max-width:640px; margin-left:auto; margin-right:auto; }
  .stat-topics{ display:flex; flex-wrap:wrap; justify-content:center; gap:12px; margin-top:44px; }
  .stat-topics span{
    font-size:14px; color:#d2d2d7; border:1px solid #3a3a3c; padding:9px 18px; border-radius:980px;
  }
 
  /* fade-in reveal used across page */
  .reveal{ opacity:0; transform:translateY(28px); transition:opacity .9s cubic-bezier(.19,1,.22,1), transform .9s cubic-bezier(.19,1,.22,1); }
  .reveal.in{ opacity:1; transform:translateY(0); }
 
  /* ---------- STICKY FEATURE SECTION ---------- */
  .sticky-wrap{ position:relative; height:300vh; background:var(--offwhite); }
  .sticky-inner{
    position:sticky; top:0; height:100svh; display:flex; align-items:center; justify-content:center;
    overflow:hidden; padding:0 24px;
  }
  .sticky-grid{ max-width:900px; width:100%; text-align:center; }
  .sticky-eyebrow{ font-size:19px; font-weight:600; color:var(--ink-dim2); margin-bottom:20px; }
  .feature-panel{
    display:none; opacity:0; transform:translateY(24px) scale(0.98);
    transition:opacity .5s ease, transform .5s ease;
  }
  .feature-panel.active{ display:block; opacity:1; transform:translateY(0) scale(1); }
  .feature-panel .num{ font-size:15px; font-weight:600; color:var(--blue); margin-bottom:14px; }
  .feature-panel h3{ font-size:clamp(36px,6vw,64px); font-weight:700; letter-spacing:-0.02em; }
  .feature-panel p{ font-size:clamp(18px,2vw,22px); color:var(--ink-dim2); margin-top:16px; max-width:600px; margin-left:auto; margin-right:auto; }
  .progress-dots{ display:flex; gap:8px; justify-content:center; margin-top:48px; }
  .progress-dots span{ width:7px; height:7px; border-radius:50%; background:var(--line); transition:background .3s ease, transform .3s ease; }
  .progress-dots span.active{ background:var(--blue); transform:scale(1.3); }
 
  /* ---------- STACK GRID ---------- */
  .stack-section{ padding:160px 24px; max-width:1024px; margin:0 auto; }
  .sec-head{ text-align:center; margin-bottom:70px; }
  .sec-head .eyebrow{ font-size:19px; font-weight:600; color:var(--ink-dim2); margin-bottom:10px; }
  .sec-head h2{ font-size:clamp(34px,5vw,56px); font-weight:700; letter-spacing:-0.02em; }
 
  .spec-grid{ display:grid; grid-template-columns:repeat(4,1fr); gap:1px; background:var(--line); border:1px solid var(--line); border-radius:18px; overflow:hidden; }
  @media (max-width:760px){ .spec-grid{ grid-template-columns:repeat(2,1fr); } }
  .spec-item{ background:#fff; padding:34px 20px; text-align:center; transition:background .2s ease; }
  .spec-item:hover{ background:var(--offwhite); }
  .spec-item img{ width:40px; height:40px; margin-bottom:14px; }
  .spec-item .name{ font-size:14px; font-weight:500; color:var(--ink); }
  .spec-item .cat{ font-size:11px; color:var(--ink-dim); margin-top:3px; text-transform:uppercase; letter-spacing:.05em; }
 
  /* ---------- PHILOSOPHY (dark) ---------- */
  .philo-section{
    background:var(--black); color:#f5f5f7; padding:200px 24px; text-align:center;
  }
  .philo-quote{
    font-size:clamp(32px,6vw,68px); font-weight:600; letter-spacing:-0.02em; line-height:1.15;
    max-width:900px; margin:0 auto;
    background:linear-gradient(180deg, #fff 0%, #98989d 100%);
    -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent;
  }
  .philo-principles{ display:flex; flex-wrap:wrap; justify-content:center; gap:12px; margin-top:52px; }
  .philo-principles span{ font-size:14px; color:#d2d2d7; border:1px solid #3a3a3c; padding:10px 20px; border-radius:980px; }
 
  /* ---------- ACHIEVEMENT STRIP ---------- */
  .about-band{ padding:160px 24px; max-width:820px; margin:0 auto; text-align:center; }
  .about-band .eyebrow{ font-size:19px; font-weight:600; color:var(--ink-dim2); margin-bottom:16px; }
  .about-band p{ font-size:clamp(22px,3vw,34px); font-weight:500; letter-spacing:-0.015em; line-height:1.4; color:var(--ink); }
  .about-band p b{ color:var(--blue); font-weight:600; }
 
  /* ---------- CONNECT (final CTA) ---------- */
  .connect-section{ background:var(--offwhite); padding:160px 24px; text-align:center; }
  .connect-section h2{ font-size:clamp(36px,6vw,64px); font-weight:700; letter-spacing:-0.02em; }
  .connect-section .sub{ font-size:clamp(18px,2.2vw,24px); color:var(--ink-dim2); margin-top:14px; }
  .connect-cards{ display:flex; gap:16px; justify-content:center; margin-top:52px; flex-wrap:wrap; }
  .connect-card{
    background:#fff; border:1px solid var(--line); border-radius:18px; padding:32px 30px;
    width:250px; text-align:left; transition: transform .3s ease, box-shadow .3s ease;
  }
  .connect-card:hover{ transform:translateY(-6px); box-shadow:0 24px 50px -20px rgba(0,0,0,0.18); }
  .connect-card .label{ font-size:12px; color:var(--ink-dim); text-transform:uppercase; letter-spacing:.06em; margin-bottom:10px; }
  .connect-card .name{ font-size:22px; font-weight:600; letter-spacing:-0.01em; }
  .connect-card .go{ margin-top:20px; font-size:14px; color:var(--blue); }
 
  footer{ padding:40px 24px 50px; text-align:center; border-top:1px solid var(--line); }
  footer p{ font-size:12px; color:var(--ink-dim); }
  footer p + p{ margin-top:6px; }
</style>
</head>
<body>
 
<nav id="mainNav">
  <div class="nav-inner">
    <div class="nav-logo">Surya Varathan</div>
    <div class="nav-links">
      <a href="#stat">LeetCode</a>
      <a href="#build">Work</a>
      <a href="#stack">Stack</a>
      <a href="#philosophy">Philosophy</a>
      <a href="#connect">Contact</a>
    </div>
  </div>
</nav>
 
<!-- HERO -->
<header class="hero">
  <div class="orb"></div>
  <div class="hero-content">
    <div class="eyebrow">Software Engineer</div>
    <h1>Surya Varathan.</h1>
    <p class="sub">Full-stack developer. Problem solver.<br>Built for scale, designed for clarity.</p>
    <div class="hero-cta">
      <a class="pill pill-solid" href="https://www.linkedin.com/mwlite/profile/in/surya-v-47b61a383" target="_blank" rel="noopener">Connect on LinkedIn</a>
      <a class="pill pill-link" href="https://github.com/suryavarathan" target="_blank" rel="noopener">View GitHub</a>
      <a class="pill pill-link" href="https://leetcode.com/u/710723243115/" target="_blank" rel="noopener">LeetCode Profile</a>
    </div>
  </div>
  <div class="scroll-cue"><span>Scroll to explore</span><span class="chevron"></span></div>
</header>
 
<!-- STAT -->
<section class="stat-section" id="stat">
  <div class="stat-eyebrow reveal">LeetCode</div>
  <div class="stat-number reveal"><span id="statNum">0</span><span class="plus">+</span></div>
  <p class="stat-caption reveal">Problems solved. A consistent, ongoing practice in algorithmic thinking — optimized for clarity, not shortcuts.</p>
  <div class="stat-topics reveal">
    <span>Dynamic Programming</span><span>Graphs</span><span>Trees</span>
    <span>Greedy Algorithms</span><span>Backtracking</span><span>Binary Search</span>
  </div>
</section>
 
<!-- ABOUT BAND -->
<section class="about-band">
  <div class="eyebrow reveal">About</div>
  <p class="reveal">I build systems that are <b>scalable</b>, <b>efficient</b>, and production-ready — with a bias toward clarity over cleverness. Backend and system design first, full-stack always, and a growing focus on where AI genuinely removes work.</p>
</section>
 
<!-- STICKY FEATURE SECTION -->
<div class="sticky-wrap" id="build">
  <div class="sticky-inner">
    <div class="sticky-grid">
      <div class="sticky-eyebrow">What I Build</div>
 
      <div class="feature-panel active" data-panel="0">
        <div class="num">01</div>
        <h3>Scalable Web Apps.</h3>
        <p>Production-ready full-stack systems designed to grow with real users, not just pass a demo.</p>
      </div>
      <div class="feature-panel" data-panel="1">
        <div class="num">02</div>
        <h3>Intelligent Systems.</h3>
        <p>AI-powered tools and automation workflows that remove repetitive work from the pipeline.</p>
      </div>
      <div class="feature-panel" data-panel="2">
        <div class="num">03</div>
        <h3>Developer Tools.</h3>
        <p>Utilities built for productivity — the small things that make engineering faster and cleaner.</p>
      </div>
 
      <div class="progress-dots">
        <span class="active" data-dot="0"></span>
        <span data-dot="1"></span>
        <span data-dot="2"></span>
      </div>
    </div>
  </div>
</div>
 
<!-- STACK -->
<section class="stack-section" id="stack">
  <div class="sec-head">
    <div class="eyebrow reveal">Engineered With</div>
    <h2 class="reveal">Tech Stack.</h2>
  </div>
  <div class="spec-grid reveal">
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=java" alt=""><div class="name">Java</div><div class="cat">Language</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=python" alt=""><div class="name">Python</div><div class="cat">Language</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=javascript" alt=""><div class="name">JavaScript</div><div class="cat">Language</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=typescript" alt=""><div class="name">TypeScript</div><div class="cat">Language</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=react" alt=""><div class="name">React</div><div class="cat">Frontend</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=nextjs" alt=""><div class="name">Next.js</div><div class="cat">Frontend</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=nodejs" alt=""><div class="name">Node.js</div><div class="cat">Backend</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=express" alt=""><div class="name">Express</div><div class="cat">Backend</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=mongodb" alt=""><div class="name">MongoDB</div><div class="cat">Database</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=mysql" alt=""><div class="name">MySQL</div><div class="cat">Database</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=docker" alt=""><div class="name">Docker</div><div class="cat">DevOps</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=linux" alt=""><div class="name">Linux</div><div class="cat">DevOps</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=git" alt=""><div class="name">Git</div><div class="cat">Tooling</div></div>
    <div class="spec-item"><img src="https://skillicons.dev/icons?i=github" alt=""><div class="name">GitHub</div><div class="cat">Tooling</div></div>
  </div>
</section>
 
<!-- PHILOSOPHY -->
<section class="philo-section" id="philosophy">
  <div class="stat-eyebrow reveal">Philosophy</div>
  <div class="philo-quote reveal">"Simplicity scales.<br>Complexity fails."</div>
  <div class="philo-principles reveal">
    <span>Build systems, not features</span>
    <span>Optimize for clarity</span>
    <span>Think long-term architecture</span>
    <span>Stay consistent, keep improving</span>
  </div>
</section>
 
<!-- CONNECT -->
<section class="connect-section" id="connect">
  <div class="eyebrow reveal" style="font-size:19px;font-weight:600;color:var(--ink-dim2);margin-bottom:10px;">Get in Touch</div>
  <h2 class="reveal">Let's build something.</h2>
  <p class="sub reveal">Open to opportunities, collaboration, and good problems.</p>
  <div class="connect-cards">
    <a class="connect-card reveal" href="https://github.com/suryavarathan" target="_blank" rel="noopener">
      <div class="label">Code</div>
      <div class="name">GitHub</div>
      <div class="go">View repositories ›</div>
    </a>
    <a class="connect-card reveal" href="https://www.linkedin.com/mwlite/profile/in/surya-v-47b61a383" target="_blank" rel="noopener">
      <div class="label">Professional</div>
      <div class="name">LinkedIn</div>
      <div class="go">Connect ›</div>
    </a>
    <a class="connect-card reveal" href="https://leetcode.com/u/710723243115/" target="_blank" rel="noopener">
      <div class="label">Practice</div>
      <div class="name">LeetCode</div>
      <div class="go">View profile ›</div>
    </a>
  </div>
</section>
 
<footer>
  <p>Built with discipline, consistency, and passion for engineering.</p>
  <p>© Surya Varathan</p>
</footer>
 
<script>
  /* ---------- Nav dark mode toggle based on section bg ---------- */
  const nav = document.getElementById('mainNav');
  const darkSections = document.querySelectorAll('.stat-section, .philo-section');
  const navIO = new IntersectionObserver((entries)=>{
    entries.forEach(entry=>{
      if(entry.isIntersecting && entry.intersectionRatio > 0.4){
        nav.classList.add('dark');
      }
    });
  }, { threshold:[0,0.4,1] });
  darkSections.forEach(s=>navIO.observe(s));
 
  const lightSections = document.querySelectorAll('.hero, .about-band, .stack-section, .connect-section');
  const navLightIO = new IntersectionObserver((entries)=>{
    entries.forEach(entry=>{
      if(entry.isIntersecting && entry.intersectionRatio > 0.5){
        nav.classList.remove('dark');
      }
    });
  }, { threshold:[0,0.5,1] });
  lightSections.forEach(s=>navLightIO.observe(s));
 
  /* ---------- Reveal on scroll ---------- */
  const revealEls = document.querySelectorAll('.reveal');
  const revealIO = new IntersectionObserver((entries)=>{
    entries.forEach(entry=>{
      if(entry.isIntersecting){ entry.target.classList.add('in'); revealIO.unobserve(entry.target); }
    });
  }, { threshold:0.15 });
  revealEls.forEach(el=>revealIO.observe(el));
 
  /* ---------- Animated stat counter ---------- */
  const statNum = document.getElementById('statNum');
  let counted = false;
  const counterIO = new IntersectionObserver((entries)=>{
    entries.forEach(entry=>{
      if(entry.isIntersecting && !counted){
        counted = true;
        let n = 0; const target = 1000;
        const step = ()=>{
          n += 22;
          if(n >= target){ statNum.textContent = target; return; }
          statNum.textContent = n;
          requestAnimationFrame(step);
        };
        step();
      }
    });
  }, { threshold:0.5 });
  counterIO.observe(statNum);
 
  /* ---------- Sticky feature panel scroll-through ---------- */
  const stickyWrap = document.querySelector('.sticky-wrap');
  const panels = document.querySelectorAll('.feature-panel');
  const dots = document.querySelectorAll('.progress-dots span');
 
  function updateSticky(){
    const rect = stickyWrap.getBoundingClientRect();
    const total = stickyWrap.offsetHeight - window.innerHeight;
    let progress = (-rect.top) / total;
    progress = Math.max(0, Math.min(1, progress));
    const idx = Math.min(panels.length - 1, Math.floor(progress * panels.length));
    panels.forEach((p,i)=> p.classList.toggle('active', i === idx));
    dots.forEach((d,i)=> d.classList.toggle('active', i === idx));
  }
  window.addEventListener('scroll', updateSticky, { passive:true });
  updateSticky();
</script>
 
</body>
</html>
 
