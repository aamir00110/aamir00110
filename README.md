<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Aamir Shehzad · Oracle APEX Developer Portfolio</title>
  <!-- Google Fonts & Tabler Icons (clean, modern icons) -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@3.30.0/dist/tabler-icons.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    /* Premium dark/light adaptive theme – respects GitHub light/dark preference via media */
    :root {
      --color-background-page: #f6f8fa;
      --color-background-primary: #ffffff;
      --color-background-secondary: #f9f9fc;
      --color-background-tertiary: #eaeef2;
      --color-background-info: #e8f0fe;
      --color-text-primary: #1f2d3d;
      --color-text-secondary: #5b6e8c;
      --color-text-info: #0969da;
      --color-border-primary: #e1e4e8;
      --color-border-secondary: #d0d7de;
      --color-border-tertiary: #e2e8f0;
      --border-radius-md: 10px;
      --border-radius-lg: 20px;
      --font-sans: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
      --font-mono: 'SF Mono', 'Menlo', monospace;
    }

    @media (prefers-color-scheme: dark) {
      :root {
        --color-background-page: #0d1117;
        --color-background-primary: #161b22;
        --color-background-secondary: #1f242e;
        --color-background-tertiary: #2d333b;
        --color-background-info: #1c2b3a;
        --color-text-primary: #e6edf3;
        --color-text-secondary: #8b949e;
        --color-text-info: #79c0ff;
        --color-border-primary: #30363d;
        --color-border-secondary: #3d444d;
        --color-border-tertiary: #2d333b;
      }
    }

    body {
      background: var(--color-background-page);
      font-family: var(--font-sans);
      color: var(--color-text-primary);
      line-height: 1.5;
      padding: 2rem 1rem;
    }

    .profile-wrap {
      max-width: 860px;
      margin: 0 auto;
    }

    /* Hero section */
    .hero {
      text-align: center;
      padding: 2rem 1.5rem 2rem;
      border: 1px solid var(--color-border-tertiary);
      border-radius: var(--border-radius-lg);
      background: var(--color-background-primary);
      margin-bottom: 1.5rem;
      position: relative;
      overflow: hidden;
      transition: box-shadow 0.2s;
    }

    .hero-top-bar {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 4px;
      background: linear-gradient(90deg, #c0392b, #e67e22, #f1c40f, #2ecc71, #3498db, #9b59b6);
    }

    .avatar {
      width: 92px;
      height: 92px;
      border-radius: 50%;
      background: linear-gradient(135deg, #1e3a5f, #0f2c47);
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 1rem;
      font-size: 34px;
      font-weight: 600;
      color: #a3c6f0;
      border: 3px solid #378ADD;
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.08);
    }

    .hero h1 {
      font-size: 24px;
      font-weight: 600;
      letter-spacing: -0.3px;
      color: var(--color-text-primary);
      margin-bottom: 8px;
    }

    .hero h3 {
      font-size: 15px;
      font-weight: 500;
      color: var(--color-text-secondary);
      margin-bottom: 1.25rem;
    }

    .typing-line {
      font-family: var(--font-mono);
      font-size: 13px;
      font-weight: 500;
      color: #1D9E75;
      background: var(--color-background-secondary);
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 6px 18px;
      border-radius: 40px;
      border: 1px solid var(--color-border-tertiary);
      backdrop-filter: blur(2px);
    }

    .cursor {
      display: inline-block;
      width: 2px;
      height: 14px;
      background: #1D9E75;
      vertical-align: middle;
      animation: blink 1s step-end infinite;
    }

    @keyframes blink {
      50% { opacity: 0; }
    }

    .socials {
      display: flex;
      justify-content: center;
      gap: 12px;
      margin-top: 1.5rem;
      flex-wrap: wrap;
    }

    .social-btn {
      font-size: 12px;
      font-weight: 500;
      padding: 6px 16px;
      border-radius: 40px;
      border: 1px solid var(--color-border-secondary);
      color: var(--color-text-secondary);
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      cursor: pointer;
      background: var(--color-background-secondary);
      transition: all 0.2s;
    }

    .social-btn:hover {
      background: var(--color-background-tertiary);
      border-color: var(--color-text-info);
      color: var(--color-text-info);
    }

    /* section styling */
    .section {
      margin-bottom: 1.75rem;
    }

    .section-title {
      font-size: 13px;
      font-weight: 600;
      color: var(--color-text-secondary);
      text-transform: uppercase;
      letter-spacing: 0.08em;
      margin-bottom: 0.85rem;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .section-title::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--color-border-tertiary);
    }

    /* about cards */
    .about-card {
      border: 1px solid var(--color-border-tertiary);
      border-radius: var(--border-radius-lg);
      background: var(--color-background-primary);
      padding: 1.25rem;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(210px, 1fr));
      gap: 12px;
    }

    .about-item {
      display: flex;
      align-items: flex-start;
      gap: 12px;
      padding: 12px;
      border-radius: 14px;
      background: var(--color-background-secondary);
      transition: all 0.2s;
    }

    .about-item i {
      font-size: 20px;
      color: #378ADD;
      flex-shrink: 0;
      margin-top: 2px;
    }

    .about-item p {
      font-size: 13px;
      color: var(--color-text-secondary);
      line-height: 1.4;
    }

    .about-item strong {
      font-weight: 600;
      color: var(--color-text-primary);
      display: block;
      font-size: 13px;
      margin-bottom: 2px;
    }

    /* tech stack grid */
    .stack-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 12px;
    }

    .stack-card {
      border: 1px solid var(--color-border-tertiary);
      border-radius: 18px;
      background: var(--color-background-primary);
      padding: 1rem 0.8rem;
      text-align: center;
      transition: transform 0.1s ease;
    }

    .stack-icon {
      width: 44px;
      height: 44px;
      border-radius: 16px;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 10px;
      font-size: 24px;
    }

    .stack-icon.red { background: #fcebeb; color: #E24B4A; }
    .stack-icon.blue { background: #e6f1fb; color: #378ADD; }
    .stack-icon.yellow { background: #faedda; color: #BA7517; }
    .stack-icon.orange { background: #faece7; color: #D85A30; }
    .stack-icon.teal { background: #e1f5ee; color: #1D9E75; }
    @media (prefers-color-scheme: dark) {
      .stack-icon.red { background: #3b2a2a; color: #e67e7e; }
      .stack-icon.blue { background: #1e2f3f; color: #6cb2eb; }
      .stack-icon.yellow { background: #382e22; color: #e2b169; }
      .stack-icon.orange { background: #392b25; color: #e2926c; }
      .stack-icon.teal { background: #1b3930; color: #4bc0a0; }
    }

    .stack-name { font-size: 14px; font-weight: 600; margin-top: 4px; }
    .stack-level { font-size: 11px; color: var(--color-text-secondary); margin-top: 4px; }
    .skill-bar { height: 4px; background: var(--color-background-tertiary); border-radius: 6px; margin-top: 12px; overflow: hidden; }
    .skill-fill { height: 100%; border-radius: 6px; }

    /* stats grid */
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 12px;
    }

    .stat-card {
      border: 1px solid var(--color-border-tertiary);
      border-radius: 20px;
      background: var(--color-background-primary);
      padding: 1rem 1.2rem;
      position: relative;
    }

    .stat-label {
      font-size: 11px;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: var(--color-text-secondary);
      margin-bottom: 8px;
    }

    .stat-value {
      font-size: 28px;
      font-weight: 700;
      color: var(--color-text-primary);
      line-height: 1.2;
    }

    .stat-sub {
      font-size: 11px;
      color: var(--color-text-secondary);
      margin-top: 4px;
    }

    .stat-icon {
      font-size: 20px;
      position: absolute;
      right: 1.2rem;
      top: 1rem;
      opacity: 0.7;
    }

    /* contribution heatmap */
    .activity-wrap {
      border: 1px solid var(--color-border-tertiary);
      border-radius: 22px;
      background: var(--color-background-primary);
      padding: 1.2rem;
    }

    .week-grid {
      display: flex;
      gap: 4px;
      flex-wrap: wrap;
      justify-content: center;
    }

    .day-col {
      display: flex;
      flex-direction: column;
      gap: 3px;
    }

    .day-sq {
      width: 12px;
      height: 12px;
      border-radius: 3px;
      transition: 0.1s;
    }

    .activity-legend {
      display: flex;
      align-items: center;
      justify-content: flex-end;
      gap: 8px;
      margin-top: 14px;
      font-size: 11px;
      color: var(--color-text-secondary);
    }

    .leg-sq {
      width: 11px;
      height: 11px;
      border-radius: 3px;
    }

    /* featured projects */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 14px;
    }

    .proj-card {
      border: 1px solid var(--color-border-tertiary);
      border-radius: 20px;
      background: var(--color-background-primary);
      padding: 1rem 1.2rem;
      cursor: pointer;
      transition: all 0.2s ease;
    }

    .proj-card:hover {
      border-color: var(--color-text-info);
      transform: translateY(-2px);
      background: var(--color-background-secondary);
    }

    .proj-title {
      font-size: 15px;
      font-weight: 600;
      color: #378ADD;
      margin-bottom: 8px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .proj-desc {
      font-size: 12.5px;
      color: var(--color-text-secondary);
      line-height: 1.45;
    }

    .proj-tags {
      display: flex;
      gap: 6px;
      margin-top: 12px;
      flex-wrap: wrap;
    }

    .tag {
      font-size: 10px;
      padding: 3px 10px;
      border-radius: 30px;
      background: var(--color-background-info);
      color: var(--color-text-info);
      font-weight: 500;
    }

    /* connect row */
    .contact-row {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }

    .contact-chip {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 10px 20px;
      border: 1px solid var(--color-border-tertiary);
      border-radius: 60px;
      background: var(--color-background-primary);
      font-size: 13px;
      font-weight: 500;
      color: var(--color-text-secondary);
      cursor: pointer;
      transition: all 0.2s;
    }

    .contact-chip:hover {
      border-color: #378ADD;
      background: var(--color-background-secondary);
      color: #378ADD;
    }

    .contact-chip i {
      font-size: 18px;
    }

    /* footer */
    .footer {
      margin-top: 2.5rem;
      text-align: center;
      font-size: 12px;
      color: var(--color-text-secondary);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
      flex-wrap: wrap;
      border-top: 1px solid var(--color-border-tertiary);
      padding-top: 1.5rem;
    }

    .views-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: var(--color-background-secondary);
      padding: 4px 12px;
      border-radius: 30px;
      font-size: 12px;
    }

    /* extra polish */
    i.ti {
      font-size: 1.1em;
    }
    button, .social-btn, .contact-chip, .proj-card {
      user-select: none;
    }
  </style>
</head>
<body>
<div class="profile-wrap">

  <!-- Hero section -->
  <div class="hero">
    <div class="hero-top-bar"></div>
    <div class="avatar">AS</div>
    <h1>Hi 👋 I'm Aamir Shehzad</h1>
    <h3>Oracle APEX Developer · PL/SQL Expert · UI/UX Enthusiast</h3>
    <div class="typing-line">
      <span id="typed-text"></span><span class="cursor"></span>
    </div>
    <div class="socials">
      <a class="social-btn" onclick="openLink('https://github.com/aamir00110')"><i class="ti ti-brand-github"></i> aamir00110</a>
      <a class="social-btn"><i class="ti ti-map-pin"></i> Lahore, Pakistan</a>
      <a class="social-btn"><i class="ti ti-circle-dot"></i> Open to Work</a>
    </div>
  </div>

  <!-- About Section -->
  <div class="section">
    <div class="section-title"><i class="ti ti-user-circle"></i> About me</div>
    <div class="about-card">
      <div class="about-item"><i class="ti ti-tool"></i><div><strong>Currently working on</strong><p>Oracle APEX enterprise applications & AI chatbots</p></div></div>
      <div class="about-item"><i class="ti ti-school"></i><div><strong>Learning</strong><p>Advanced JavaScript, REST APIs, Vue.js</p></div></div>
      <div class="about-item"><i class="ti ti-message-circle"></i><div><strong>Ask me about</strong><p>PL/SQL, Oracle APEX, interactive grids, plugins</p></div></div>
      <div class="about-item"><i class="ti ti-heart"></i><div><strong>Passion</strong><p>Building dashboards & AI-powered APEX apps</p></div></div>
    </div>
  </div>

  <!-- Tech Stack (Dynamic bars) -->
  <div class="section">
    <div class="section-title"><i class="ti ti-code"></i> Tech stack</div>
    <div class="stack-grid">
      <div class="stack-card"><div class="stack-icon red"><i class="ti ti-database"></i></div><div class="stack-name">Oracle DB</div><div class="stack-level">Expert</div><div class="skill-bar"><div class="skill-fill" style="width:95%;background:#E24B4A;"></div></div></div>
      <div class="stack-card"><div class="stack-icon blue"><i class="ti ti-layout-dashboard"></i></div><div class="stack-name">Oracle APEX</div><div class="stack-level">Expert</div><div class="skill-bar"><div class="skill-fill" style="width:93%;background:#378ADD;"></div></div></div>
      <div class="stack-card"><div class="stack-icon yellow"><i class="ti ti-file-code"></i></div><div class="stack-name">PL/SQL</div><div class="stack-level">Expert</div><div class="skill-bar"><div class="skill-fill" style="width:96%;background:#BA7517;"></div></div></div>
      <div class="stack-card"><div class="stack-icon yellow"><i class="ti ti-brand-javascript"></i></div><div class="stack-name">JavaScript</div><div class="stack-level">Intermediate</div><div class="skill-bar"><div class="skill-fill" style="width:68%;background:#BA7517;"></div></div></div>
      <div class="stack-card"><div class="stack-icon orange"><i class="ti ti-brand-html5"></i></div><div class="stack-name">HTML5/CSS3</div><div class="stack-level">Advanced</div><div class="skill-bar"><div class="skill-fill" style="width:80%;background:#D85A30;"></div></div></div>
      <div class="stack-card"><div class="stack-icon teal"><i class="ti ti-api"></i></div><div class="stack-name">REST APIs</div><div class="stack-level">Advanced</div><div class="skill-bar"><div class="skill-fill" style="width:82%;background:#1D9E75;"></div></div></div>
    </div>
  </div>

  <!-- GitHub stats (interactive numbers) -->
  <div class="section">
    <div class="section-title"><i class="ti ti-chart-bar"></i> GitHub stats</div>
    <div class="stats-grid">
      <div class="stat-card"><div class="stat-label">Total stars <i class="ti ti-star stat-icon"></i></div><div class="stat-value">48</div><div class="stat-sub">Across all repos</div></div>
      <div class="stat-card"><div class="stat-label">Commits (2024) <i class="ti ti-git-commit stat-icon"></i></div><div class="stat-value">312</div><div class="stat-sub">Keep pushing! 🚀</div></div>
      <div class="stat-card"><div class="stat-label">Pull requests <i class="ti ti-git-pull-request stat-icon"></i></div><div class="stat-value">27</div><div class="stat-sub">Merged & closed</div></div>
      <div class="stat-card"><div class="stat-label">Streak <i class="ti ti-flame stat-icon"></i></div><div class="stat-value">14<span style="font-size:14px;font-weight:400"> days</span></div><div class="stat-sub">Current streak</div></div>
    </div>
  </div>

  <!-- Contribution activity heatmap -->
  <div class="section">
    <div class="section-title"><i class="ti ti-calendar-stats"></i> Contribution activity</div>
    <div class="activity-wrap">
      <div class="week-grid" id="contrib-grid"></div>
      <div class="activity-legend">
        Less
        <div class="leg-sq" style="background:var(--color-background-tertiary)"></div>
        <div class="leg-sq" style="background:#B5D4F4"></div>
        <div class="leg-sq" style="background:#85B7EB"></div>
        <div class="leg-sq" style="background:#378ADD"></div>
        <div class="leg-sq" style="background:#185FA5"></div>
        More
      </div>
    </div>
  </div>

  <!-- Featured projects (clickable interactions + in-console demo) -->
  <div class="section">
    <div class="section-title"><i class="ti ti-folder"></i> Featured projects</div>
    <div class="projects-grid">
      <div class="proj-card" onclick="showProjectInfo('APEX AI Chatbot')">
        <div class="proj-title"><i class="ti ti-robot"></i> APEX AI Chatbot</div>
        <div class="proj-desc">DeepSeek-powered conversational AI integrated natively into Oracle APEX using REST APIs and PL/SQL.</div>
        <div class="proj-tags"><span class="tag">APEX</span><span class="tag">PL/SQL</span><span class="tag">DeepSeek</span></div>
      </div>
      <div class="proj-card" onclick="showProjectInfo('Analytics Dashboard')">
        <div class="proj-title"><i class="ti ti-layout-dashboard"></i> Analytics Dashboard</div>
        <div class="proj-desc">Real-time KPI dashboards with dynamic charts, Interactive Grid, and custom APEX plugins.</div>
        <div class="proj-tags"><span class="tag">APEX</span><span class="tag">Oracle DB</span><span class="tag">JS</span></div>
      </div>
      <div class="proj-card" onclick="showProjectInfo('PL/SQL Utilities')">
        <div class="proj-title"><i class="ti ti-database"></i> PL/SQL Utilities</div>
        <div class="proj-desc">Collection of reusable PL/SQL packages for logging, auditing, REST integration, and data processing.</div>
        <div class="proj-tags"><span class="tag">PL/SQL</span><span class="tag">Packages</span></div>
      </div>
      <div class="proj-card" onclick="showProjectInfo('REST API Framework')">
        <div class="proj-title"><i class="ti ti-api"></i> REST API Framework</div>
        <div class="proj-desc">Modular ORDS-based REST framework for Oracle APEX with auth, ACL, and Web Credentials management.</div>
        <div class="proj-tags"><span class="tag">ORDS</span><span class="tag">REST</span><span class="tag">APEX</span></div>
      </div>
    </div>
  </div>

  <!-- Connect section -->
  <div class="section">
    <div class="section-title"><i class="ti ti-mail"></i> Connect</div>
    <div class="contact-row">
      <div class="contact-chip" onclick="openLink('https://github.com/aamir00110')"><i class="ti ti-brand-github"></i> GitHub</div>
      <div class="contact-chip" onclick="openLink('https://linkedin.com/in/aamir-shehzad-apex')"><i class="ti ti-brand-linkedin"></i> LinkedIn</div>
      <div class="contact-chip" onclick="copyEmail()"><i class="ti ti-mail"></i> aamir@apex.dev</div>
      <div class="contact-chip"><i class="ti ti-map-pin"></i> Lahore, PK</div>
    </div>
  </div>

  <div class="footer">
    <div class="views-badge"><i class="ti ti-eye"></i> Profile views: 1.2k</div>
    <span>·</span>
    <span>Made with ❤️ by Aamir Shehzad</span>
  </div>
</div>

<script>
  // ---------- TYPING ANIMATION (exactly same as original but enhanced) ----------
  const phrases = ["Oracle APEX Developer", "PL/SQL Programmer", "Dashboard Designer", "AI Chatbot Builder", "REST API Integrator"];
  let phraseIndex = 0, charIndex = 0, isDeleting = false;
  const typedSpan = document.getElementById('typed-text');
  function typeEffect() {
    const currentPhrase = phrases[phraseIndex];
    if (!isDeleting) {
      typedSpan.textContent = currentPhrase.substring(0, charIndex + 1);
      charIndex++;
      if (charIndex === currentPhrase.length) {
        isDeleting = true;
        setTimeout(typeEffect, 1600);
        return;
      }
    } else {
      typedSpan.textContent = currentPhrase.substring(0, charIndex - 1);
      charIndex--;
      if (charIndex === 0) {
        isDeleting = false;
        phraseIndex = (phraseIndex + 1) % phrases.length;
        setTimeout(typeEffect, 180);
        return;
      }
    }
    setTimeout(typeEffect, isDeleting ? 45 : 90);
  }
  typeEffect();

  // ---------- Contribution Heatmap (realistic random but soft gradient) ----------
  const heatmapColors = [
    'var(--color-background-tertiary)', '#B5D4F4', '#85B7EB', '#378ADD', '#185FA5'
  ];
  // dark mode overrides for darker theme consistency
  if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
    heatmapColors[0] = '#2d333b';
    heatmapColors[1] = '#2b5a7a';
    heatmapColors[2] = '#2b6e9e';
    heatmapColors[3] = '#378ADD';
    heatmapColors[4] = '#5aa9dd';
  }
  const container = document.getElementById('contrib-grid');
  // 36 weeks of contributions (simulated)
  for (let w = 0; w < 36; w++) {
    const col = document.createElement('div');
    col.className = 'day-col';
    for (let d = 0; d < 7; d++) {
      const square = document.createElement('div');
      square.className = 'day-sq';
      // weighted random (more medium & low)
      let rand = Math.random();
      let level = 0;
      if (rand < 0.4) level = 0;
      else if (rand < 0.62) level = 1;
      else if (rand < 0.79) level = 2;
      else if (rand < 0.92) level = 3;
      else level = 4;
      square.style.backgroundColor = heatmapColors[level];
      col.appendChild(square);
    }
    container.appendChild(col);
  }

  // ---------- helper functions (interactive + external) ----------
  window.openLink = function(url) {
    if (url) window.open(url, '_blank');
    else alert('🔗 Link will be updated soon!');
  };

  window.showProjectInfo = function(projectName) {
    let description = '';
    if (projectName === 'APEX AI Chatbot') description = '⚡ DeepSeek AI integrated inside APEX using REST & PL/SQL — dynamic context-aware conversations.';
    else if (projectName === 'Analytics Dashboard') description = '📊 Real-time BI dashboards, custom APEX charts, drill-down grids and Row level security.';
    else if (projectName === 'PL/SQL Utilities') description = '📦 Reusable logging, email queue, audit trail and dynamic SQL utilities.';
    else if (projectName === 'REST API Framework') description = '🔌 ORDS based API framework with OAuth2, web credentials and error handling.';
    alert(`✨ ${projectName}\n\n${description}\n\n⭐ Want source code? Let's connect!`);
  };

  window.copyEmail = function() {
    const email = 'aamir.shehzad@apex.dev';
    navigator.clipboard.writeText(email).then(() => {
      alert('📧 Email copied to clipboard: ' + email);
    }).catch(() => {
      prompt('📋 Copy manually:', email);
    });
  };

  // simple optional console welcome
  console.log("%c✨ Aamir Shehzad | Oracle APEX Dev | Dashboard Expert", "color: #378ADD; font-size: 14px; font-weight: bold;");
</script>
</body>
</html>
