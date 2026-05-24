# suragouni.github.io
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Suragouni — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --bg2: #111118;
    --card: #16161f;
    --border: rgba(255,255,255,0.07);
    --accent: #00e5c3;
    --accent2: #7b5ea7;
    --accent3: #ff6b4a;
    --text: #e8e8f0;
    --muted: #7a7a90;
    --white: #ffffff;
    --font-display: 'Syne', sans-serif;
    --font-body: 'DM Sans', sans-serif;
    --font-mono: 'Space Mono', monospace;
  }
 
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
 
  html { scroll-behavior: smooth; }
 
  body {
    font-family: var(--font-body);
    background: var(--bg);
    color: var(--text);
    overflow-x: hidden;
    line-height: 1.7;
  }
 
  /* ——— NOISE TEXTURE ——— */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.4;
  }
 
  /* ——— NAV ——— */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 500;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.25rem 3rem;
    background: rgba(10,10,15,0.85);
    backdrop-filter: blur(14px);
    border-bottom: 1px solid var(--border);
  }
 
  .nav-logo {
    font-family: var(--font-mono);
    font-size: 0.85rem;
    color: var(--accent);
    letter-spacing: 0.08em;
    text-decoration: none;
  }
 
  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }
 
  .nav-links a {
    font-family: var(--font-body);
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--muted);
    text-decoration: none;
    letter-spacing: 0.04em;
    text-transform: uppercase;
    transition: color 0.2s;
  }
 
  .nav-links a:hover { color: var(--accent); }
 
  /* ——— HERO ——— */
  #home {
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 8rem 3rem 5rem;
    position: relative;
    overflow: hidden;
  }
 
  /* Mesh gradient blob */
  #home::after {
    content: '';
    position: absolute;
    width: 700px; height: 700px;
    top: -150px; right: -200px;
    background: radial-gradient(ellipse at center, rgba(0,229,195,0.1) 0%, rgba(123,94,167,0.08) 45%, transparent 70%);
    border-radius: 50%;
    pointer-events: none;
  }
 
  .hero-inner {
    max-width: 900px;
    animation: fadeUp 0.9s ease both;
  }
 
  .hero-tag {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-family: var(--font-mono);
    font-size: 0.75rem;
    color: var(--accent);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 1.5rem;
    padding: 0.35rem 0.9rem;
    border: 1px solid rgba(0,229,195,0.3);
    border-radius: 2px;
  }
 
  .hero-tag::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--accent);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }
 
  h1 {
    font-family: var(--font-display);
    font-size: clamp(3rem, 8vw, 6.5rem);
    font-weight: 800;
    line-height: 1.0;
    letter-spacing: -0.02em;
    color: var(--white);
    margin-bottom: 1.5rem;
  }
 
  h1 span {
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
 
  .hero-sub {
    font-size: 1.15rem;
    color: var(--muted);
    max-width: 580px;
    margin-bottom: 2.5rem;
    font-weight: 300;
  }
 
  .hero-sub strong { color: var(--text); font-weight: 500; }
 
  .hero-location {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    font-family: var(--font-mono);
    font-size: 0.78rem;
    color: var(--muted);
    margin-bottom: 2.5rem;
  }
 
  .hero-location svg { color: var(--accent); }
 
  .btn-row {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    align-items: center;
  }
 
  .btn {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.8rem 1.8rem;
    font-family: var(--font-body);
    font-size: 0.85rem;
    font-weight: 500;
    text-decoration: none;
    border-radius: 3px;
    transition: all 0.25s;
    cursor: pointer;
    border: none;
    letter-spacing: 0.02em;
  }
 
  .btn-primary {
    background: var(--accent);
    color: #0a0a0f;
  }
 
  .btn-primary:hover {
    background: #00c9ab;
    transform: translateY(-2px);
    box-shadow: 0 8px 24px rgba(0,229,195,0.25);
  }
 
  .btn-outline {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border);
  }
 
  .btn-outline:hover {
    border-color: var(--accent);
    color: var(--accent);
    transform: translateY(-2px);
  }
 
  /* featured project cards below fold line */
  .hero-projects {
    margin-top: 5rem;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
    animation: fadeUp 1.1s ease both;
    animation-delay: 0.2s;
  }
 
  .hp-card {
    background: var(--card);
    padding: 1.5rem;
    cursor: pointer;
    transition: background 0.2s;
    text-decoration: none;
    color: inherit;
    display: block;
  }
 
  .hp-card:hover { background: #1c1c28; }
 
  .hp-label {
    font-family: var(--font-mono);
    font-size: 0.65rem;
    color: var(--accent);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 0.6rem;
  }
 
  .hp-title {
    font-family: var(--font-display);
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--white);
    line-height: 1.3;
  }
 
  /* ——— SECTION COMMONS ——— */
  section { padding: 6rem 3rem; }
 
  .section-label {
    font-family: var(--font-mono);
    font-size: 0.72rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 0.75rem;
  }
 
  h2 {
    font-family: var(--font-display);
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 800;
    color: var(--white);
    line-height: 1.1;
    letter-spacing: -0.02em;
    margin-bottom: 1rem;
  }
 
  .divider {
    width: 48px; height: 2px;
    background: linear-gradient(90deg, var(--accent), transparent);
    margin-bottom: 3rem;
  }
 
  /* ——— ABOUT ——— */
  #about {
    background: var(--bg2);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }
 
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: start;
  }
 
  .about-text p {
    font-size: 1rem;
    color: var(--muted);
    margin-bottom: 1.2rem;
    font-weight: 300;
  }
 
  .about-text p strong { color: var(--text); font-weight: 500; }
 
  .about-right {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }
 
  .about-block {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 1.5rem;
    position: relative;
    overflow: hidden;
  }
 
  .about-block::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 100%;
    background: var(--accent);
    border-radius: 3px 0 0 3px;
  }
 
  .about-block:nth-child(2)::before { background: var(--accent2); }
  .about-block:nth-child(3)::before { background: var(--accent3); }
 
  .about-block h3 {
    font-family: var(--font-display);
    font-size: 0.95rem;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 0.5rem;
  }
 
  .about-block p {
    font-size: 0.88rem;
    color: var(--muted);
    font-weight: 300;
  }
 
  .cert-list {
    display: flex;
    flex-direction: column;
    gap: 0.4rem;
    margin-top: 0.5rem;
  }
 
  .cert-item {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.85rem;
    color: var(--muted);
  }
 
  .cert-item::before {
    content: '→';
    color: var(--accent);
    font-family: var(--font-mono);
    font-size: 0.75rem;
  }
 
  /* ——— PROJECTS ——— */
  #projects { background: var(--bg); }
 
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 2rem;
  }
 
  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 2.5rem;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 2rem;
    align-items: start;
    transition: border-color 0.3s, transform 0.3s;
    position: relative;
    overflow: hidden;
  }
 
  .project-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }
 
  .project-card:hover { border-color: rgba(0,229,195,0.2); transform: translateY(-3px); }
  .project-card:hover::after { transform: scaleX(1); }
 
  .project-number {
    font-family: var(--font-mono);
    font-size: 0.7rem;
    color: var(--accent);
    letter-spacing: 0.1em;
    margin-bottom: 0.75rem;
  }
 
  .project-card h3 {
    font-family: var(--font-display);
    font-size: 1.35rem;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 0.4rem;
    line-height: 1.2;
  }
 
  .project-date {
    font-family: var(--font-mono);
    font-size: 0.72rem;
    color: var(--muted);
    margin-bottom: 1rem;
  }
 
  .project-desc {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    margin-bottom: 1.5rem;
  }
 
  .project-desc li {
    font-size: 0.9rem;
    color: var(--muted);
    padding-left: 1rem;
    position: relative;
    font-weight: 300;
  }
 
  .project-desc li::before {
    content: '▸';
    position: absolute;
    left: 0;
    color: var(--accent);
    font-size: 0.7rem;
    top: 0.15rem;
  }
 
  .tech-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }
 
  .tech-tag {
    font-family: var(--font-mono);
    font-size: 0.68rem;
    color: var(--accent);
    background: rgba(0,229,195,0.08);
    border: 1px solid rgba(0,229,195,0.2);
    padding: 0.25rem 0.65rem;
    border-radius: 2px;
    letter-spacing: 0.05em;
  }
 
  .project-icon {
    width: 56px; height: 56px;
    background: rgba(0,229,195,0.06);
    border: 1px solid rgba(0,229,195,0.15);
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    flex-shrink: 0;
  }
 
  /* ——— SKILLS ——— */
  #skills {
    background: var(--bg2);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }
 
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
  }
 
  .skill-category {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 1.75rem;
    transition: border-color 0.3s;
  }
 
  .skill-category:hover { border-color: rgba(0,229,195,0.25); }
 
  .skill-cat-header {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    margin-bottom: 1.25rem;
  }
 
  .skill-cat-icon {
    font-size: 1.2rem;
  }
 
  .skill-category h3 {
    font-family: var(--font-display);
    font-size: 0.9rem;
    font-weight: 700;
    color: var(--white);
  }
 
  .skill-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }
 
  .skill-pill {
    font-size: 0.8rem;
    color: var(--muted);
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    padding: 0.3rem 0.75rem;
    border-radius: 100px;
    font-weight: 400;
    transition: all 0.2s;
  }
 
  .skill-pill:hover {
    color: var(--accent);
    border-color: rgba(0,229,195,0.3);
    background: rgba(0,229,195,0.05);
  }
 
  /* ——— CONTACT ——— */
  #contact { background: var(--bg); }
 
  .contact-inner {
    max-width: 680px;
  }
 
  .contact-desc {
    font-size: 1.05rem;
    color: var(--muted);
    margin-bottom: 3rem;
    font-weight: 300;
  }
 
  .contact-links {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin-bottom: 3rem;
  }
 
  .contact-link {
    display: flex;
    align-items: center;
    gap: 1rem;
    padding: 1.25rem 1.5rem;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    text-decoration: none;
    color: var(--text);
    transition: all 0.25s;
  }
 
  .contact-link:hover {
    border-color: rgba(0,229,195,0.3);
    transform: translateX(6px);
    color: var(--accent);
  }
 
  .contact-link-icon {
    width: 40px; height: 40px;
    background: rgba(0,229,195,0.08);
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
  }
 
  .contact-link-info { flex: 1; }
 
  .contact-link-label {
    font-family: var(--font-mono);
    font-size: 0.68rem;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    display: block;
    margin-bottom: 0.15rem;
  }
 
  .contact-link-value {
    font-size: 0.92rem;
    font-weight: 500;
  }
 
  .contact-link-arrow {
    color: var(--muted);
    font-size: 1.1rem;
    transition: transform 0.2s, color 0.2s;
  }
 
  .contact-link:hover .contact-link-arrow {
    transform: translateX(4px);
    color: var(--accent);
  }
 
  /* ——— FOOTER ——— */
  footer {
    padding: 2rem 3rem;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: var(--bg);
  }
 
  footer p {
    font-family: var(--font-mono);
    font-size: 0.72rem;
    color: var(--muted);
    letter-spacing: 0.05em;
  }
 
  footer span { color: var(--accent); }
 
  /* ——— ANIMATIONS ——— */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(28px); }
    to   { opacity: 1; transform: translateY(0); }
  }
 
  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.7); }
  }
 
  .reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
 
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }
 
  /* ——— RESPONSIVE ——— */
  @media (max-width: 768px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { gap: 1.5rem; }
    section { padding: 4rem 1.5rem; }
    #home { padding: 7rem 1.5rem 4rem; }
    .about-grid { grid-template-columns: 1fr; gap: 2.5rem; }
    .project-card { grid-template-columns: 1fr; }
    .project-icon { display: none; }
    .hero-projects { grid-template-columns: 1fr; }
    footer { flex-direction: column; gap: 0.5rem; text-align: center; }
  }
 
  @media (max-width: 480px) {
    h1 { font-size: 2.5rem; }
    .nav-links { display: none; }
  }
</style>
</head>
<body>
 
<!-- NAV -->
<nav>
  <a href="#home" class="nav-logo">SL</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
 
<!-- HERO -->
<section id="home">
  <div style="width:100%">
    <div class="hero-inner">
      <div class="hero-tag">Available for opportunities</div>
      <h1>S Sai Lakshman<br><span>Goud</span></h1>
      <p class="hero-sub">
        <strong>Data Scientist</strong> · Event Management · Cybersecurity &amp; Networking —<br>
        Bridging technical depth with strategic leadership.
      </p>
      <div class="hero-location">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
        Hyderabad, India
      </div>
      <div class="btn-row">
        <a href="#contact" class="btn btn-primary">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg>
          Let's Connect
        </a>
        <a href="#projects" class="btn btn-outline">View Projects →</a>
        <a href="https://www.linkedin.com/in/sailakshmangoud17/" target="_blank" class="btn btn-outline">LinkedIn</a>
        <a href="https://github.com/Sailakshmangoud" target="_blank" class="btn btn-outline">GitHub</a>
      </div>
    </div>
 
    <div class="hero-projects">
      <a href="#projects" class="hp-card">
        <div class="hp-label">01 · Networking</div>
        <div class="hp-title">Hotel Management Network Design</div>
      </a>
      <a href="#projects" class="hp-card">
        <div class="hp-label">02 · IoT</div>
        <div class="hp-title">Health Monitoring System</div>
      </a>
      <a href="#projects" class="hp-card">
        <div class="hp-label">03 · Machine Learning</div>
        <div class="hp-title">Telecom Customer Churn Prediction</div>
      </a>
    </div>
  </div>
</section>
 
<!-- ABOUT -->
<section id="about">
  <div class="section-label">// About Me</div>
  <h2>Blending data, security,<br>and leadership.</h2>
  <div class="divider"></div>
 
  <div class="about-grid reveal">
    <div class="about-text">
      <p>I'm an <strong>ambitious and proactive professional</strong> offering a strong blend of technical expertise and leadership experience. As a fresher with hands-on project experience, I've demonstrated initiative, execution, and strategic thinking across cybersecurity, event management, and business development.</p>
      <p>I organized and directed <strong>70+ university-level events</strong> and 3 flagship programs — demonstrating team management, execution of high-impact projects, and driving large-scale participation.</p>
      <p>My technical work was recognized during a networking project at <strong>Career TiQ</strong>, receiving outstanding feedback for its innovation and simplicity.</p>
      <p>Selected for the exclusive <strong>McKinsey Forward Program</strong>, where I'm developing future-proof capabilities in problem-solving, leadership, and digitalization.</p>
    </div>
 
    <div class="about-right">
      <div class="about-block">
        <h3>🏆 Certifications</h3>
        <div class="cert-list">
          <div class="cert-item">Automation Anywhere — RPA</div>
          <div class="cert-item">Fortinet Certified Cybersecurity Associate</div>
          <div class="cert-item">AWS Certified Cloud Practitioner</div>
          </div>
          <div class="cert-item">Salesforce AI Associate</div>
        </div>
      </div>
      <div class="about-block">
        <h3>🎯 McKinsey Forward Program</h3>
        <p>Selected for this exclusive program developing future-proof capabilities in problem-solving, leadership, and digitalization.</p>
      </div>
      <div class="about-block">
        <h3>💼 Looking For</h3>
        <p>Data Scientist, Event Manager or coordinator, or high-growth startup roles where I can contribute and grow from day one.</p>
      </div>
    </div>
  </div>
</section>
 
<!-- PROJECTS -->
<section id="projects">
  <div class="section-label">// Featured Projects</div>
  <h2>Things I've built.</h2>
  <div class="divider"></div>
 
  <div class="projects-grid">
 
    <div class="project-card reveal">
      <div>
        <div class="project-number">01 / Cisco Packet Tracer</div>
        <h3>Hotel Management Network Design &amp; Implementation</h3>
        <div class="project-date">July 2024 – August 2024</div>
        <ul class="project-desc">
          <li>Designed and simulated a complete Hotel Network System using Cisco Packet Tracer</li>
          <li>Built enterprise-grade network architecture tailored for hotel operations</li>
          <li>Implemented VLANs and Inter-VLAN Routing for network segmentation and seamless communication</li>
        </ul>
        <div class="tech-stack">
          <span class="tech-tag">Cisco Packet Tracer</span>
          <span class="tech-tag">VLANs</span>
          <span class="tech-tag">Inter-VLAN Routing</span>
          <span class="tech-tag">Network Design</span>
        </div>
      </div>
      <div class="project-icon">🌐</div>
    </div>
 
    <div class="project-card reveal">
      <div>
        <div class="project-number">02 / Arduino · IoT</div>
        <h3>Health Monitoring System</h3>
        <div class="project-date">January 2024 – May 2024</div>
        <ul class="project-desc">
          <li>Developed an end-to-end IoT system for real-time health condition monitoring</li>
          <li>Integrated heartbeat sensor, ECG module, and ESP8266 for multi-parameter tracking</li>
          <li>Ensured reliable monitoring output with optimized system performance</li>
        </ul>
        <div class="tech-stack">
          <span class="tech-tag">Arduino</span>
          <span class="tech-tag">IoT</span>
          <span class="tech-tag">Heartbeat Sensor</span>
          <span class="tech-tag">ECG Module</span>
          <span class="tech-tag">ESP8266</span>
        </div>
      </div>
      <div class="project-icon">❤️</div>
    </div>
 
    <div class="project-card reveal">
      <div>
        <div class="project-number">03 / Machine Learning</div>
        <h3>Telecom Customer Churn Prediction</h3>
        <div class="project-date">April 2026 – June 2026</div>
        <ul class="project-desc">
          <li>Developed an ML classification system to predict telecommunications customer churn</li>
          <li>Conducted EDA and feature engineering to improve model understanding and accuracy</li>
          <li>Built predictive models using Random Forest and XGBoost ensemble methods</li>
          <li>Created high-risk customer identification to support proactive retention strategies</li>
        </ul>
        <div class="tech-stack">
          <span class="tech-tag">Machine Learning</span>
          <span class="tech-tag">EDA</span>
          <span class="tech-tag">Feature Engineering</span>
          <span class="tech-tag">Random Forest</span>
          <span class="tech-tag">XGBoost</span>
        </div>
      </div>
      <div class="project-icon">📊</div>
    </div>
 
  </div>
</section>
 
<!-- SKILLS -->
<section id="skills">
  <div class="section-label">// Skills & Expertise</div>
  <h2>What I work with.</h2>
  <div class="divider"></div>
 
  <div class="skills-grid reveal">
    <div class="skill-category">
      <div class="skill-cat-header">
        <span class="skill-cat-icon">🧠</span>
        <h3>Data Science & Analytics</h3>
      </div>
      <div class="skill-pills">
        <span class="skill-pill">Data Science</span>
        <span class="skill-pill">EDA</span>
        <span class="skill-pill">Machine Learning</span>
        <span class="skill-pill">Risk Management</span>
        <span class="skill-pill">Critical Thinking</span>
        <span class="skill-pill">Decision Making</span>
      </div>
    </div>
 
    <div class="skill-category">
      <div class="skill-cat-header">
        <span class="skill-cat-icon">🔒</span>
        <h3>Network Security & Cybersecurity</h3>
      </div>
      <div class="skill-pills">
        <span class="skill-pill">Network Security</span>
        <span class="skill-pill">Cybersecurity</span>
        <span class="skill-pill">Application Control</span>
        <span class="skill-pill">VPN</span>
      </div>
    </div>
 
    <div class="skill-category">
      <div class="skill-cat-header">
        <span class="skill-cat-icon">🏗️</span>
        <h3>Architecture & Planning</h3>
      </div>
      <div class="skill-pills">
        <span class="skill-pill">Architecture Design</span>
        <span class="skill-pill">Strategic Planning</span>
        <span class="skill-pill">Project Planning</span>
        <span class="skill-pill">Project Management</span>
      </div>
    </div>
 
    <div class="skill-category">
      <div class="skill-cat-header">
        <span class="skill-cat-icon">⚙️</span>
        <h3>Operations & Finance</h3>
      </div>
      <div class="skill-pills">
        <span class="skill-pill">Operation Management</span>
        <span class="skill-pill">Financial Literacy</span>
      </div>
    </div>
 
    <div class="skill-category">
      <div class="skill-cat-header">
        <span class="skill-cat-icon">🎯</span>
        <h3>Leadership & Events</h3>
      </div>
      <div class="skill-pills">
        <span class="skill-pill">Leadership Development</span>
        <span class="skill-pill">Event Management</span>
        <span class="skill-pill">Event Budgeting</span>
        <span class="skill-pill">Event Planning</span>
      </div>
    </div>
  </div>
</section>
 
<!-- CONTACT -->
<section id="contact">
  <div class="section-label">// Get In Touch</div>
  <h2>Let's connect.</h2>
  <div class="divider"></div>
 
  <div class="contact-inner reveal">
    <p class="contact-desc">I'm open to <strong style="color:var(--text)">Data Scientist</strong>, <strong style="color:var(--text)">Event Management</strong>, and high-growth startup opportunities where I can contribute and grow with the team. Reach out anytime.</p>
 
    <div class="contact-links">
      <a href="mailto:suragounisailakshmangoud@gmail.com" class="contact-link">
        <div class="contact-link-icon">✉️</div>
        <div class="contact-link-info">
          <span class="contact-link-label">Email</span>
          <span class="contact-link-value">suragounisailakshmangoud@gmail.com</span>
        </div>
        <span class="contact-link-arrow">→</span>
      </a>
 
      <a href="https://www.linkedin.com/in/sailakshmangoud17/" target="_blank" class="contact-link">
        <div class="contact-link-icon">💼</div>
        <div class="contact-link-info">
          <span class="contact-link-label">LinkedIn</span>
          <span class="contact-link-value">linkedin.com/in/sailakshmangoud17</span>
        </div>
        <span class="contact-link-arrow">→</span>
      </a>
 
      <a href="https://github.com/Sailakshmangoud" target="_blank" class="contact-link">
        <div class="contact-link-icon">🐙</div>
        <div class="contact-link-info">
          <span class="contact-link-label">GitHub</span>
          <span class="contact-link-value">github.com/Sailakshmangoud</span>
        </div>
        <span class="contact-link-arrow">→</span>
      </a>
    </div>
 
    <a href="mailto:suragounisailakshmangoud@gmail.com" class="btn btn-primary" style="font-size:0.95rem; padding: 1rem 2.2rem;">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg>
      Let's Connect
    </a>
  </div>
</section>
 
<!-- FOOTER -->
<footer>
  <p>all rights © 2026 <span>Suragouni Sai Lakshman Goud</span> — Hyderabad, India</p>
  <p>Built with care &amp; <span>precision</span></p>
</footer>
 
<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
        io.unobserve(e.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => io.observe(el));
 
  // Active nav link on scroll
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-links a');
  window.addEventListener('scroll', () => {
    let cur = '';
    sections.forEach(sec => {
      if (window.scrollY >= sec.offsetTop - 120) cur = sec.id;
    });
    navLinks.forEach(a => {
      a.style.color = a.getAttribute('href') === `#${cur}` ? 'var(--accent)' : '';
    });
  });
</script>
</body>
</html>
