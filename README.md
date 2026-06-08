<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Kali Siri — AI/ML Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0a0a0f; --bg2: #111118; --bg3: #1a1a25;
    --accent: #7ef0c0; --accent2: #4ec9ff; --accent3: #ff7eb3;
    --text: #f0f0f5; --muted: #7a7a8a;
    --border: rgba(255,255,255,0.07); --card: rgba(255,255,255,0.04);
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body { background: var(--bg); color: var(--text); font-family: 'DM Sans', sans-serif; font-size: 16px; line-height: 1.7; overflow-x: hidden; }
  h1,h2,h3,h4 { font-family: 'Syne', sans-serif; line-height: 1.15; }

  nav { position: fixed; top: 0; left: 0; right: 0; z-index: 100; display: flex; align-items: center; justify-content: space-between; padding: 1.2rem 4rem; border-bottom: 1px solid var(--border); backdrop-filter: blur(20px); background: rgba(10,10,15,0.85); }
  .nav-logo { font-family:'Syne',sans-serif; font-size:1.1rem; font-weight:700; letter-spacing:.04em; color:var(--accent); }
  .nav-links { display:flex; gap:2.5rem; list-style:none; }
  .nav-links a { color:var(--muted); text-decoration:none; font-size:.9rem; font-weight:500; letter-spacing:.03em; transition:color .2s; }
  .nav-links a:hover { color:var(--text); }
  .nav-cta { background: transparent; border: 1px solid var(--accent); color: var(--accent); padding: .5rem 1.3rem; border-radius:40px; font-family:'Syne',sans-serif; font-size:.85rem; font-weight:600; cursor:pointer; letter-spacing:.04em; text-decoration:none; transition: background .2s, color .2s; }
  .nav-cta:hover { background:var(--accent); color:var(--bg); }

  .hero { min-height: 100vh; display: flex; flex-direction: column; justify-content: center; padding: 8rem 4rem 4rem; position: relative; overflow: hidden; }
  .hero-grid { position: absolute; inset: 0; z-index: 0; background-image: linear-gradient(rgba(126,240,192,0.04) 1px, transparent 1px), linear-gradient(90deg, rgba(126,240,192,0.04) 1px, transparent 1px); background-size: 60px 60px; }
  .hero-glow { position:absolute; top:-10%; left:-5%; width:50vw; height:50vw; background: radial-gradient(ellipse, rgba(126,240,192,0.07) 0%, transparent 65%); pointer-events:none; z-index:0; }
  .hero-glow2 { position:absolute; bottom:-10%; right:-5%; width:40vw; height:40vw; background: radial-gradient(ellipse, rgba(78,201,255,0.06) 0%, transparent 65%); pointer-events:none; z-index:0; }
  .hero-content { position:relative; z-index:1; max-width:800px; }
  .hero-tag { display:inline-flex; align-items:center; gap:.5rem; font-size:.8rem; font-weight:500; letter-spacing:.1em; text-transform:uppercase; color:var(--accent); border:1px solid rgba(126,240,192,0.25); background:rgba(126,240,192,0.06); padding:.35rem 1rem; border-radius:40px; margin-bottom:1.8rem; animation: fadeUp .6s ease both; }
  .hero-tag .dot { width:6px; height:6px; border-radius:50%; background:var(--accent); animation:pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.3} }
  .hero h1 { font-size: clamp(3rem, 7vw, 5.5rem); font-weight: 800; letter-spacing:-.02em; line-height: 1.05; animation: fadeUp .6s .1s ease both; }
  .hero h1 .line2 { color: var(--accent); }
  .hero-sub { font-size: 1.15rem; color: var(--muted); max-width:520px; margin-top: 1.5rem; font-weight:300; animation: fadeUp .6s .2s ease both; }
  .hero-actions { display:flex; gap:1rem; margin-top:2.5rem; flex-wrap:wrap; animation: fadeUp .6s .3s ease both; }
  .btn-primary { background:var(--accent); color:var(--bg); padding:.75rem 2rem; border-radius:40px; font-family:'Syne',sans-serif; font-weight:700; font-size:.9rem; text-decoration:none; letter-spacing:.03em; transition: transform .2s, box-shadow .2s; }
  .btn-primary:hover { transform:translateY(-2px); box-shadow:0 8px 30px rgba(126,240,192,0.25); }
  .btn-ghost { color:var(--text); padding:.75rem 2rem; border-radius:40px; font-family:'Syne',sans-serif; font-weight:600; font-size:.9rem; text-decoration:none; letter-spacing:.03em; border:1px solid var(--border); transition:border-color .2s, background .2s; }
  .btn-ghost:hover { border-color:rgba(255,255,255,0.2); background:rgba(255,255,255,0.04); }
  .hero-stats { display:flex; gap:3rem; margin-top:4rem; padding-top:2rem; border-top:1px solid var(--border); animation: fadeUp .6s .4s ease both; }
  .stat-num { font-family:'Syne',sans-serif; font-size:2rem; font-weight:800; color:var(--text); }
  .stat-label { font-size:.8rem; color:var(--muted); letter-spacing:.05em; text-transform:uppercase; }
  @keyframes fadeUp { from{opacity:0;transform:translateY(24px)} to{opacity:1;transform:none} }

  section { padding: 6rem 4rem; }
  .section-tag { font-size:.75rem; letter-spacing:.12em; text-transform:uppercase; color:var(--accent); font-weight:600; margin-bottom:1rem; display:block; }
  .section-title { font-size:clamp(2rem,4vw,3rem); font-weight:800; margin-bottom:.75rem; }
  .section-sub { color:var(--muted); max-width:500px; margin-bottom:3.5rem; font-weight:300; }

  .about { background:var(--bg2); }
  .about-grid { display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center; }
  .about-left .big-text { font-family:'Syne',sans-serif; font-size:clamp(1.1rem,2.5vw,1.4rem); font-weight:500; line-height:1.6; color:var(--text); }
  .about-left .big-text span { color:var(--accent); }
  .about-left p { color:var(--muted); margin-top:1.5rem; font-weight:300; }
  .about-right { display:flex; flex-direction:column; gap:1rem; }
  .info-row { display:flex; justify-content:space-between; align-items:center; padding:.9rem 1.2rem; background:var(--card); border:1px solid var(--border); border-radius:10px; }
  .info-label { font-size:.8rem; color:var(--muted); letter-spacing:.05em; text-transform:uppercase; }
  .info-val { font-family:'Syne',sans-serif; font-size:.95rem; font-weight:600; color:var(--text); }

  .skills-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(260px,1fr)); gap:1.5rem; }
  .skill-card { padding:1.75rem; background:var(--card); border:1px solid var(--border); border-radius:14px; transition:border-color .25s, transform .25s; position:relative; overflow:hidden; }
  .skill-card:hover { border-color:rgba(126,240,192,0.25); transform:translateY(-4px); }
  .skill-card::before { content:''; position:absolute; inset:0; background:linear-gradient(135deg,rgba(126,240,192,0.04),transparent); opacity:0; transition:opacity .25s; }
  .skill-card:hover::before { opacity:1; }
  .skill-icon { font-size:1.8rem; margin-bottom:1rem; }
  .skill-title { font-family:'Syne',sans-serif; font-size:1rem; font-weight:700; margin-bottom:.5rem; }
  .skill-tags { display:flex; flex-wrap:wrap; gap:.4rem; margin-top:.75rem; }
  .tag { font-size:.75rem; padding:.2rem .65rem; border-radius:20px; background:rgba(255,255,255,0.06); border:1px solid var(--border); color:var(--muted); }

  .projects { background:var(--bg2); }
  .projects-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(300px,1fr)); gap:1.5rem; }
  .project-card { padding:2rem; background:var(--bg3); border:1px solid var(--border); border-radius:16px; transition:border-color .25s, transform .25s; position:relative; overflow:hidden; display:flex; flex-direction:column; }
  .project-card:hover { border-color:rgba(126,240,192,0.2); transform:translateY(-5px); }
  .project-card.featured { border-color:rgba(126,240,192,0.15); grid-column:span 2; }
  .project-accent { width:40px; height:3px; border-radius:2px; background:var(--accent); margin-bottom:1.25rem; }
  .project-card.blue .project-accent { background:var(--accent2); }
  .project-card.pink .project-accent { background:var(--accent3); }
  .project-badge { display:inline-block; font-size:.7rem; letter-spacing:.08em; text-transform:uppercase; color:var(--accent); background:rgba(126,240,192,0.08); border:1px solid rgba(126,240,192,0.2); padding:.2rem .7rem; border-radius:20px; margin-bottom:1rem; font-weight:600; }
  .project-badge.blue { color:var(--accent2); background:rgba(78,201,255,0.08); border-color:rgba(78,201,255,0.2); }
  .project-badge.pink { color:var(--accent3); background:rgba(255,126,179,0.08); border-color:rgba(255,126,179,0.2); }
  .project-title { font-family:'Syne',sans-serif; font-size:1.3rem; font-weight:800; margin-bottom:.6rem; }
  .project-desc { color:var(--muted); font-size:.95rem; line-height:1.65; font-weight:300; flex:1; }
  .project-tech { display:flex; flex-wrap:wrap; gap:.4rem; margin-top:1.25rem; }
  .project-tech span { font-size:.75rem; padding:.2rem .65rem; border-radius:20px; background:rgba(255,255,255,0.05); border:1px solid var(--border); color:var(--muted); }
  .project-link { display:inline-flex; align-items:center; gap:.4rem; margin-top:1.5rem; font-family:'Syne',sans-serif; font-size:.85rem; font-weight:600; color:var(--accent); text-decoration:none; transition:gap .2s; }
  .project-link:hover { gap:.7rem; }

  .certs-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(220px,1fr)); gap:1rem; }
  .cert-card { padding:1.4rem 1.5rem; background:var(--card); border:1px solid var(--border); border-radius:12px; display:flex; align-items:flex-start; gap:1rem; transition:border-color .2s; }
  .cert-card:hover { border-color:rgba(126,240,192,0.2); }
  .cert-icon { font-size:1.5rem; flex-shrink:0; margin-top:.1rem; }
  .cert-name { font-family:'Syne',sans-serif; font-size:.9rem; font-weight:700; }
  .cert-issuer { font-size:.8rem; color:var(--muted); margin-top:.2rem; }

  .achievements { background:var(--bg2); }
  .ach-list { display:flex; flex-direction:column; gap:1rem; max-width:700px; }
  .ach-item { display:flex; gap:1.25rem; align-items:flex-start; padding:1.4rem 1.5rem; background:var(--card); border:1px solid var(--border); border-radius:12px; }
  .ach-emoji { font-size:1.5rem; flex-shrink:0; }
  .ach-title { font-family:'Syne',sans-serif; font-size:1rem; font-weight:700; }
  .ach-desc { font-size:.9rem; color:var(--muted); margin-top:.2rem; }

  .contact { text-align:center; }
  .contact .section-sub { margin-left:auto; margin-right:auto; }
  .contact-links { display:flex; justify-content:center; gap:1rem; flex-wrap:wrap; margin-top:1rem; }
  .contact-btn { display:inline-flex; align-items:center; gap:.6rem; padding:.75rem 1.75rem; border-radius:40px; font-family:'Syne',sans-serif; font-size:.9rem; font-weight:600; text-decoration:none; border:1px solid var(--border); color:var(--text); transition:border-color .2s, background .2s, transform .2s; }
  .contact-btn:hover { border-color:var(--accent); color:var(--accent); transform:translateY(-2px); }
  .contact-btn svg { width:18px; height:18px; }

  footer { text-align:center; padding:2rem 4rem; border-top:1px solid var(--border); font-size:.85rem; color:var(--muted); }

  @media(max-width:900px) {
    nav { padding:1rem 1.5rem; }
    .nav-links { display:none; }
    section { padding:4rem 1.5rem; }
    .hero { padding:7rem 1.5rem 3rem; }
    .hero-stats { gap:2rem; flex-wrap:wrap; }
    .about-grid { grid-template-columns:1fr; }
    .project-card.featured { grid-column:span 1; }
    footer { padding:2rem 1.5rem; }
  }
</style>
</head>
<body>

<nav>
  <span class="nav-logo">KS</span>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#certs">Certs</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="mailto:siris4077@gmail.com" class="nav-cta">Hire me</a>
</nav>

<section class="hero" id="home">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>
  <div class="hero-content">
    <div class="hero-tag"><span class="dot"></span>Available for opportunities</div>
    <h1>Kali Siri<br><span class="line2">AI/ML Developer</span></h1>
    <p class="hero-sub">Final-year CSE student building intelligent systems — from self-healing AI agents to IoT safety hardware. Turning research into real-world solutions.</p>
    <div class="hero-actions">
      <a href="#projects" class="btn-primary">View Projects</a>
      <a href="#contact" class="btn-ghost">Get in touch</a>
    </div>
    <div class="hero-stats">
      <div><div class="stat-num">8.04</div><div class="stat-label">CGPA</div></div>
      <div><div class="stat-num">4+</div><div class="stat-label">Projects</div></div>
      <div><div class="stat-num">🏆</div><div class="stat-label">Hackathon Winner</div></div>
      <div><div class="stat-num">6+</div><div class="stat-label">Certifications</div></div>
    </div>
  </div>
</section>

<section class="about" id="about">
  <span class="section-tag">About me</span>
  <div class="about-grid">
    <div class="about-left">
      <p class="big-text">I build <span>intelligent systems</span> that solve real-world problems — from AI agents that self-heal Kubernetes clusters to smart helmets that protect workers in the field.</p>
      <p>Currently a final-year B.Tech CSE student at Ramachandra College of Engineering, Eluru . Interning at SmartBridge in AI/ML and actively exploring Agentic AI, LLMs, and real-time monitoring systems.</p>
      <p style="margin-top:.75rem;">I love combining AI with hardware, data, and cloud to build end-to-end solutions that actually matter.</p>
    </div>
    <div class="about-right">
      <div class="info-row"><span class="info-label">Degree</span><span class="info-val">B.Tech CSE </span></div>
      <div class="info-row"><span class="info-label">College</span><span class="info-val">Ramachandra College of Engineering</span></div>
      <div class="info-row"><span class="info-label">CGPA</span><span class="info-val">8.04 / 10.0</span></div>
      <div class="info-row"><span class="info-label">Location</span><span class="info-val">Andhra Pradesh, India</span></div>
      <div class="info-row"><span class="info-label">Status</span><span class="info-val" style="color:var(--accent);">Open to work ✦</span></div>
      <div class="info-row"><span class="info-label">Email</span><span class="info-val">siris4077@gmail.com</span></div>
    </div>
  </div>
</section>

<section id="skills">
  <span class="section-tag">Technical Skills</span>
  <h2 class="section-title">What I work with</h2>
  <p class="section-sub">A blend of AI/ML, full-stack development, and IoT hardware integration.</p>
  <div class="skills-grid">
    <div class="skill-card"><div class="skill-icon">🤖</div><div class="skill-title">AI / Machine Learning</div><p style="font-size:.9rem;color:var(--muted);font-weight:300;">Building intelligent agents, ML pipelines, and LLM-powered applications.</p><div class="skill-tags"><span class="tag">Python</span><span class="tag">Gemini API</span><span class="tag">Agentic AI</span><span class="tag">NLP</span></div></div>
    <div class="skill-card"><div class="skill-icon">🌐</div><div class="skill-title">Full-Stack Development</div><p style="font-size:.9rem;color:var(--muted);font-weight:300;">End-to-end web applications from backend APIs to polished frontends.</p><div class="skill-tags"><span class="tag">JavaScript</span><span class="tag">HTML/CSS</span><span class="tag">Flask</span><span class="tag">SQL</span></div></div>
    <div class="skill-card"><div class="skill-icon">🔧</div><div class="skill-title">IoT & Hardware</div><p style="font-size:.9rem;color:var(--muted);font-weight:300;">Sensor integration, real-time monitoring and cloud dashboards for physical systems.</p><div class="skill-tags"><span class="tag">ESP32</span><span class="tag">ThingsBoard</span><span class="tag">DHT22</span><span class="tag">GPS</span></div></div>
    <div class="skill-card"><div class="skill-icon">☁️</div><div class="skill-title">Cloud & DevOps</div><p style="font-size:.9rem;color:var(--muted);font-weight:300;">Container orchestration and real-time resource monitoring at scale.</p><div class="skill-tags"><span class="tag">Kubernetes</span><span class="tag">Minikube</span><span class="tag">Prometheus</span><span class="tag">cAdvisor</span></div></div>
    <div class="skill-card"><div class="skill-icon">📊</div><div class="skill-title">Data Analysis</div><p style="font-size:.9rem;color:var(--muted);font-weight:300;">Turning raw data into actionable insights for operational decisions.</p><div class="skill-tags"><span class="tag">Python</span><span class="tag">Excel</span><span class="tag">SQL</span><span class="tag">C</span></div></div>
    <div class="skill-card"><div class="skill-icon">💡</div><div class="skill-title">Soft Skills</div><p style="font-size:.9rem;color:var(--muted);font-weight:300;">Leadership, communication, and teamwork refined through hackathons and community work.</p><div class="skill-tags"><span class="tag">Leadership</span><span class="tag">Teamwork</span><span class="tag">Critical Thinking</span></div></div>
  </div>
</section>

<section class="projects" id="projects">
  <span class="section-tag">Projects</span>
  <h2 class="section-title">Things I've built</h2>
  <p class="section-sub">Real-world systems built with a focus on intelligence, safety, and scalability.</p>
  <div class="projects-grid">
    <div class="project-card featured">
      <div class="project-accent"></div>
      <span class="project-badge">ABB Accelerator 2026</span>
      <div class="project-title">UNIVISION AI — Agentic AI System</div>
      <p class="project-desc">Kubernetes-based AI monitoring agent for student portals built with Team SparkTech. Features real-time pod resource discovery, dependency mapping, and self-healing capabilities. Integrated Prometheus and cAdvisor for observability, with ThingsBoard for visualization.</p>
      <div class="project-tech"><span>Minikube</span><span>Prometheus</span><span>cAdvisor</span><span>ThingsBoard</span><span>Kubernetes</span><span>Python</span></div>
      <a href="https://github.com/siri-k08" class="project-link">View on GitHub →</a>
    </div>
    <div class="project-card blue">
      <div class="project-accent"></div>
      <span class="project-badge blue">IoT + Cloud</span>
      <div class="project-title">IntelliGuard Helmet</div>
      <p class="project-desc">Smart safety helmet for industrial workers using ESP32, MQ gas sensor, DHT22, and GPS. Real-time environment tracking with automated safety alerts streamed to a ThingsBoard cloud dashboard.</p>
      <div class="project-tech"><span>ESP32</span><span>MQ Sensor</span><span>DHT22</span><span>GPS</span><span>ThingsBoard</span></div>
      <a href="https://github.com/siri-k08" class="project-link">View on GitHub →</a>
    </div>
    <div class="project-card pink">
      <div class="project-accent"></div>
      <span class="project-badge pink">Data Analysis</span>
      <div class="project-title">Supply Chain Management</div>
      <p class="project-desc">Analysed inventory and logistics data to derive actionable insights. Built a data-driven model to track stock levels, optimise goods flow, and identify cost reduction opportunities.</p>
      <div class="project-tech"><span>Python</span><span>Flask</span><span>SQL</span><span>Data Analysis</span></div>
      <a href="https://github.com/siri-k08" class="project-link">View on GitHub →</a>
    </div>
    <div class="project-card">
      <div class="project-accent"></div>
      <span class="project-badge">System Design</span>
      <div class="project-title">Triaging System</div>
      <p class="project-desc">Client prioritisation system that sorts tasks and requests by urgency, improving response time and decision-making efficiency for support workflows.</p>
      <div class="project-tech"><span>Python</span><span>Logic Design</span><span>SQL</span></div>
      <a href="https://github.com/siri-k08" class="project-link">View on GitHub →</a>
    </div>
  </div>
</section>

<section id="certs">
  <span class="section-tag">Certifications</span>
  <h2 class="section-title">Credentials</h2>
  <p class="section-sub">Verified learning across AI, development, and professional skills.</p>
  <div class="certs-grid">
    <div class="cert-card"><div class="cert-icon">🐍</div><div><div class="cert-name">Python for Beginners</div><div class="cert-issuer">Simplilearn</div></div></div>
    <div class="cert-card"><div class="cert-icon">⚙️</div><div><div class="cert-name">C Programming</div><div class="cert-issuer">Simplilearn</div></div></div>
    <div class="cert-card"><div class="cert-icon">🌐</div><div><div class="cert-name">Full Stack Development</div><div class="cert-issuer">Simplilearn</div></div></div>
    <div class="cert-card"><div class="cert-icon">🤖</div><div><div class="cert-name">AI for Beginners</div><div class="cert-issuer">HP Life</div></div></div>
    <div class="cert-card"><div class="cert-icon">💼</div><div><div class="cert-name">Career Edge: Young Professional</div><div class="cert-issuer">TCS iON</div></div></div>
    <div class="cert-card"><div class="cert-icon">✅</div><div><div class="cert-name">Problem Solving (Intermediate)</div><div class="cert-issuer">HackerRank · ID: B195F6468E1D</div></div></div>
  </div>
</section>

<section class="achievements">
  <span class="section-tag">Achievements</span>
  <h2 class="section-title">Highlights</h2>
  <p class="section-sub">Recognition, learning, and giving back.</p>
  <div class="ach-list">
    <div class="ach-item"><div class="ach-emoji">🏆</div><div><div class="ach-title">National-Level Agentic AI Hackathon — Consolation Prize</div><div class="ach-desc">24-hour hackathon (Prakalp 2026) at Ramachandra College of Engineering, Eluru.</div></div></div>
    <div class="ach-item"><div class="ach-emoji">🔬</div><div><div class="ach-title">Cutting Edges Workshop</div><div class="ach-desc">Attended an emerging technologies workshop covering latest trends in AI, IoT, and software engineering.</div></div></div>
    <div class="ach-item"><div class="ach-emoji">🎓</div><div><div class="ach-title">Community Mentorship</div><div class="ach-desc">Guided 10th-grade students on career choices in technology and higher education paths.</div></div></div>
    <div class="ach-item"><div class="ach-emoji">🤖</div><div><div class="ach-title">SmartBridge AI/ML Internship</div><div class="ach-desc">Short-Term Virtual Internship in AI/ML (2026), working on applied ML projects.</div></div></div>
  </div>
</section>

<section id="contact">
  <span class="section-tag">Contact</span>
  <h2 class="section-title">Let's connect</h2>
  <p class="section-sub">Open to internships, collaborations, and full-time opportunities in AI/ML and software development.</p>
  <div class="contact-links">
    <a href="mailto:siris4077@gmail.com" class="contact-btn"><svg fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,12 2,6"/></svg>siris4077@gmail.com</a>
    <a href="https://www.linkedin.com/in/sirikali08" target="_blank" class="contact-btn"><svg fill="currentColor" viewBox="0 0 24 24"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>LinkedIn</a>
    <a href="https://www.github.com/siri-k08" target="_blank" class="contact-btn"><svg fill="currentColor" viewBox="0 0 24 24"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>GitHub</a>
    <a href="tel:9391643055" class="contact-btn"><svg fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12a19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 3.6 1.27h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.91a16 16 0 0 0 6.18 6.18l1.8-1.8a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg>+91 9391643055</a>
  </div>
</section>

<footer>
  <p>© 2026 Kali Siri · Built with ❤️ · Andhra Pradesh, India</p>
</footer>

</body>
</html>
