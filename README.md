
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: var(--font-sans); }
  .profile-wrap { max-width: 780px; margin: 0 auto; padding: 1.5rem 1rem; }

  .hero { text-align: center; padding: 2.5rem 1rem 2rem; border: 0.5px solid var(--color-border-tertiary); border-radius: var(--border-radius-lg); background: var(--color-background-primary); margin-bottom: 1.25rem; position: relative; overflow: hidden; }
  .hero-top-bar { position: absolute; top: 0; left: 0; right: 0; height: 4px; background: linear-gradient(90deg, #c0392b, #e74c3c, #f39c12, #27ae60, #2980b9, #8e44ad); }
  .avatar { width: 88px; height: 88px; border-radius: 50%; background: #1e3a5f; display: flex; align-items: center; justify-content: center; margin: 0 auto 1rem; font-size: 32px; font-weight: 500; color: #85B7EB; border: 3px solid #378ADD; }
  .hero h1 { font-size: 22px; font-weight: 500; color: var(--color-text-primary); margin-bottom: 6px; }
  .hero h3 { font-size: 14px; font-weight: 400; color: var(--color-text-secondary); margin-bottom: 1.25rem; }
  .typing-line { font-family: var(--font-mono); font-size: 13px; color: #1D9E75; background: var(--color-background-secondary); display: inline-block; padding: 5px 14px; border-radius: 20px; border: 0.5px solid var(--color-border-tertiary); }
  .cursor { display: inline-block; width: 2px; height: 13px; background: #1D9E75; vertical-align: middle; margin-left: 2px; animation: blink 1s step-end infinite; }
  @keyframes blink { 50% { opacity: 0; } }
  .socials { display: flex; justify-content: center; gap: 10px; margin-top: 1.25rem; flex-wrap: wrap; }
  .social-btn { font-size: 12px; padding: 5px 14px; border-radius: 20px; border: 0.5px solid var(--color-border-secondary); color: var(--color-text-secondary); text-decoration: none; display: flex; align-items: center; gap: 6px; cursor: pointer; background: var(--color-background-secondary); }
  .social-btn:hover { background: var(--color-background-tertiary); }

  .section { margin-bottom: 1.25rem; }
  .section-title { font-size: 13px; font-weight: 500; color: var(--color-text-secondary); text-transform: uppercase; letter-spacing: 0.08em; margin-bottom: 0.75rem; display: flex; align-items: center; gap: 8px; }
  .section-title::after { content: ''; flex: 1; height: 0.5px; background: var(--color-border-tertiary); }

  .about-card { border: 0.5px solid var(--color-border-tertiary); border-radius: var(--border-radius-lg); background: var(--color-background-primary); padding: 1.25rem; display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  .about-item { display: flex; align-items: flex-start; gap: 10px; padding: 10px; border-radius: var(--border-radius-md); background: var(--color-background-secondary); }
  .about-item i { font-size: 18px; color: #378ADD; margin-top: 1px; flex-shrink: 0; }
  .about-item p { font-size: 13px; color: var(--color-text-secondary); line-height: 1.5; }
  .about-item strong { color: var(--color-text-primary); font-weight: 500; display: block; font-size: 13px; }

  .stack-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(130px, 1fr)); gap: 10px; }
  .stack-card { border: 0.5px solid var(--color-border-tertiary); border-radius: var(--border-radius-lg); background: var(--color-background-primary); padding: 1rem; text-align: center; }
  .stack-icon { width: 40px; height: 40px; border-radius: var(--border-radius-md); display: flex; align-items: center; justify-content: center; margin: 0 auto 8px; font-size: 20px; }
  .stack-icon.red { background: #FCEBEB; color: #E24B4A; }
  .stack-icon.blue { background: #E6F1FB; color: #378ADD; }
  .stack-icon.yellow { background: #FAEEDA; color: #BA7517; }
  .stack-icon.orange { background: #FAECE7; color: #D85A30; }
  .stack-icon.teal { background: #E1F5EE; color: #1D9E75; }
  .stack-name { font-size: 13px; font-weight: 500; color: var(--color-text-primary); }
  .stack-level { font-size: 11px; color: var(--color-text-secondary); margin-top: 4px; }
  .skill-bar { height: 3px; border-radius: 2px; background: var(--color-background-tertiary); margin-top: 8px; overflow: hidden; }
  .skill-fill { height: 100%; border-radius: 2px; }

  .stats-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 10px; }
  .stat-card { border: 0.5px solid var(--color-border-tertiary); border-radius: var(--border-radius-lg); background: var(--color-background-primary); padding: 1rem 1.25rem; }
  .stat-label { font-size: 11px; color: var(--color-text-secondary); text-transform: uppercase; letter-spacing: 0.06em; margin-bottom: 6px; }
  .stat-value { font-size: 24px; font-weight: 500; color: var(--color-text-primary); }
  .stat-sub { font-size: 12px; color: var(--color-text-secondary); margin-top: 3px; }
  .stat-icon { font-size: 18px; float: right; margin-top: -2px; }

  .contrib-bar { display: flex; height: 8px; border-radius: 4px; overflow: hidden; margin-top: 10px; gap: 2px; }
  .cb { border-radius: 2px; }

  .projects-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  .proj-card { border: 0.5px solid var(--color-border-tertiary); border-radius: var(--border-radius-lg); background: var(--color-background-primary); padding: 1rem 1.25rem; cursor: pointer; transition: border-color 0.2s; }
  .proj-card:hover { border-color: var(--color-border-secondary); }
  .proj-title { font-size: 14px; font-weight: 500; color: #378ADD; margin-bottom: 4px; display: flex; align-items: center; gap: 6px; }
  .proj-desc { font-size: 12px; color: var(--color-text-secondary); line-height: 1.5; }
  .proj-tags { display: flex; gap: 5px; margin-top: 8px; flex-wrap: wrap; }
  .tag { font-size: 11px; padding: 2px 8px; border-radius: 10px; background: var(--color-background-info); color: var(--color-text-info); }

  .activity-wrap { border: 0.5px solid var(--color-border-tertiary); border-radius: var(--border-radius-lg); background: var(--color-background-primary); padding: 1.25rem; }
  .week-grid { display: flex; gap: 3px; flex-wrap: wrap; }
  .day-col { display: flex; flex-direction: column; gap: 3px; }
  .day-sq { width: 11px; height: 11px; border-radius: 2px; }
  .activity-legend { display: flex; align-items: center; gap: 6px; justify-content: flex-end; margin-top: 10px; font-size: 11px; color: var(--color-text-secondary); }
  .leg-sq { width: 10px; height: 10px; border-radius: 2px; }

  .contact-row { display: flex; gap: 10px; flex-wrap: wrap; }
  .contact-chip { display: flex; align-items: center; gap: 8px; padding: 10px 16px; border: 0.5px solid var(--color-border-tertiary); border-radius: 30px; background: var(--color-background-primary); font-size: 13px; color: var(--color-text-secondary); cursor: pointer; }
  .contact-chip:hover { border-color: var(--color-border-secondary); }
  .contact-chip i { font-size: 16px; color: #378ADD; }

  .footer { text-align: center; margin-top: 2rem; font-size: 12px; color: var(--color-text-secondary); display: flex; align-items: center; justify-content: center; gap: 8px; }
  .views-badge { display: inline-flex; align-items: center; gap: 5px; padding: 4px 12px; border-radius: 12px; background: var(--color-background-secondary); border: 0.5px solid var(--color-border-tertiary); font-size: 12px; color: var(--color-text-secondary); }
</style>

<div class="profile-wrap">

  <div class="hero">
    <div class="hero-top-bar"></div>
    <div class="avatar">AS</div>
    <h1>Hi 👋 I'm Aamir Shehzad</h1>
    <h3>Oracle APEX Developer · PL/SQL Expert · UI/UX Enthusiast</h3>
    <div class="typing-line">
      <span id="typed-text"></span><span class="cursor"></span>
    </div>
    <div class="socials">
      <a class="social-btn" onclick="openLink('https://github.com/aamir00110')"><i class="ti ti-brand-github" aria-hidden="true"></i> aamir00110</a>
      <a class="social-btn"><i class="ti ti-map-pin" aria-hidden="true"></i> Lahore, Pakistan</a>
      <a class="social-btn"><i class="ti ti-circle-dot" aria-hidden="true"></i> Open to Work</a>
    </div>
  </div>

  <div class="section">
    <div class="section-title"><i class="ti ti-user" aria-hidden="true" style="font-size:14px"></i> About me</div>
    <div class="about-card">
      <div class="about-item"><i class="ti ti-tool" aria-hidden="true"></i><div><strong>Currently working on</strong><p>Oracle APEX enterprise applications</p></div></div>
      <div class="about-item"><i class="ti ti-school" aria-hidden="true"></i><div><strong>Learning</strong><p>Advanced JavaScript & REST APIs</p></div></div>
      <div class="about-item"><i class="ti ti-message-circle" aria-hidden="true"></i><div><strong>Ask me about</strong><p>PL/SQL, Oracle APEX, APEX plugins</p></div></div>
      <div class="about-item"><i class="ti ti-heart" aria-hidden="true"></i><div><strong>Passion</strong><p>Building interactive dashboards & AI chatbots</p></div></div>
    </div>
  </div>

  <div class="section">
    <div class="section-title"><i class="ti ti-code" aria-hidden="true" style="font-size:14px"></i> Tech stack</div>
    <div class="stack-grid">
      <div class="stack-card">
        <div class="stack-icon red"><i class="ti ti-database" aria-hidden="true"></i></div>
        <div class="stack-name">Oracle DB</div>
        <div class="stack-level">Expert</div>
        <div class="skill-bar"><div class="skill-fill" style="width:95%;background:#E24B4A;"></div></div>
      </div>
      <div class="stack-card">
        <div class="stack-icon blue"><i class="ti ti-layout-dashboard" aria-hidden="true"></i></div>
        <div class="stack-name">Oracle APEX</div>
        <div class="stack-level">Expert</div>
        <div class="skill-bar"><div class="skill-fill" style="width:93%;background:#378ADD;"></div></div>
      </div>
      <div class="stack-card">
        <div class="stack-icon yellow"><i class="ti ti-file-code" aria-hidden="true"></i></div>
        <div class="stack-name">PL/SQL</div>
        <div class="stack-level">Expert</div>
        <div class="skill-bar"><div class="skill-fill" style="width:95%;background:#BA7517;"></div></div>
      </div>
      <div class="stack-card">
        <div class="stack-icon yellow"><i class="ti ti-brand-javascript" aria-hidden="true"></i></div>
        <div class="stack-name">JavaScript</div>
        <div class="stack-level">Intermediate</div>
        <div class="skill-bar"><div class="skill-fill" style="width:65%;background:#BA7517;"></div></div>
      </div>
      <div class="stack-card">
        <div class="stack-icon orange"><i class="ti ti-brand-html5" aria-hidden="true"></i></div>
        <div class="stack-name">HTML5</div>
        <div class="stack-level">Advanced</div>
        <div class="skill-bar"><div class="skill-fill" style="width:80%;background:#D85A30;"></div></div>
      </div>
      <div class="stack-card">
        <div class="stack-icon teal"><i class="ti ti-api" aria-hidden="true"></i></div>
        <div class="stack-name">REST APIs</div>
        <div class="stack-level">Advanced</div>
        <div class="skill-bar"><div class="skill-fill" style="width:82%;background:#1D9E75;"></div></div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-title"><i class="ti ti-chart-bar" aria-hidden="true" style="font-size:14px"></i> GitHub stats</div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-label">Total stars <i class="ti ti-star stat-icon" style="color:#BA7517" aria-hidden="true"></i></div>
        <div class="stat-value">48</div>
        <div class="stat-sub">Across all repos</div>
      </div>
      <div class="stat-card">
        <div class="stat-label">Commits (2024) <i class="ti ti-git-commit stat-icon" style="color:#378ADD" aria-hidden="true"></i></div>
        <div class="stat-value">312</div>
        <div class="stat-sub">Keep pushing! 🚀</div>
      </div>
      <div class="stat-card">
        <div class="stat-label">Pull requests <i class="ti ti-git-pull-request stat-icon" style="color:#1D9E75" aria-hidden="true"></i></div>
        <div class="stat-value">27</div>
        <div class="stat-sub">Merged & closed</div>
      </div>
      <div class="stat-card">
        <div class="stat-label">Streak <i class="ti ti-flame stat-icon" style="color:#E24B4A" aria-hidden="true"></i></div>
        <div class="stat-value">14<span style="font-size:14px;font-weight:400"> days</span></div>
        <div class="stat-sub">Current streak</div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-title"><i class="ti ti-calendar-stats" aria-hidden="true" style="font-size:14px"></i> Contribution activity</div>
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

  <div class="section">
    <div class="section-title"><i class="ti ti-folder" aria-hidden="true" style="font-size:14px"></i> Featured projects</div>
    <div class="projects-grid">
      <div class="proj-card" onclick="sendPrompt('Tell me more about an Oracle APEX AI Chatbot project')">
        <div class="proj-title"><i class="ti ti-robot" aria-hidden="true" style="font-size:16px"></i> APEX AI Chatbot</div>
        <div class="proj-desc">DeepSeek-powered conversational AI integrated natively into Oracle APEX using REST APIs and PL/SQL.</div>
        <div class="proj-tags"><span class="tag">APEX</span><span class="tag">PL/SQL</span><span class="tag">DeepSeek</span></div>
      </div>
      <div class="proj-card" onclick="sendPrompt('Tell me more about Oracle APEX interactive dashboard projects')">
        <div class="proj-title"><i class="ti ti-layout-dashboard" aria-hidden="true" style="font-size:16px"></i> Analytics Dashboard</div>
        <div class="proj-desc">Real-time KPI dashboards with dynamic charts, Interactive Grid, and custom APEX plugins.</div>
        <div class="proj-tags"><span class="tag">APEX</span><span class="tag">Oracle DB</span><span class="tag">JS</span></div>
      </div>
      <div class="proj-card">
        <div class="proj-title"><i class="ti ti-database" aria-hidden="true" style="font-size:16px"></i> PL/SQL Utilities</div>
        <div class="proj-desc">Collection of reusable PL/SQL packages for logging, auditing, REST integration, and data processing.</div>
        <div class="proj-tags"><span class="tag">PL/SQL</span><span class="tag">Packages</span></div>
      </div>
      <div class="proj-card">
        <div class="proj-title"><i class="ti ti-api" aria-hidden="true" style="font-size:16px"></i> REST API Framework</div>
        <div class="proj-desc">Modular ORDS-based REST framework for Oracle APEX with auth, ACL, and Web Credentials management.</div>
        <div class="proj-tags"><span class="tag">ORDS</span><span class="tag">REST</span><span class="tag">APEX</span></div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-title"><i class="ti ti-mail" aria-hidden="true" style="font-size:14px"></i> Connect</div>
    <div class="contact-row">
      <div class="contact-chip" onclick="openLink('https://github.com/aamir00110')"><i class="ti ti-brand-github" aria-hidden="true"></i> GitHub</div>
      <div class="contact-chip"><i class="ti ti-brand-linkedin" aria-hidden="true"></i> LinkedIn</div>
      <div class="contact-chip"><i class="ti ti-mail" aria-hidden="true"></i> Email</div>
      <div class="contact-chip"><i class="ti ti-map-pin" aria-hidden="true"></i> Lahore, PK</div>
    </div>
  </div>

  <div class="footer">
    <div class="views-badge"><i class="ti ti-eye" aria-hidden="true" style="font-size:13px"></i> Profile views: 1.2k</div>
    <span>·</span>
    <span>Made with ❤️ by Aamir Shehzad</span>
  </div>

</div>

<script>
const phrases = ["Oracle APEX Developer", "PL/SQL Programmer", "Dashboard Designer", "AI Chatbot Builder", "REST API Integrator"];
let pi = 0, ci = 0, del = false;
const el = document.getElementById('typed-text');
function type() {
  const cur = phrases[pi];
  if (!del) { el.textContent = cur.slice(0, ++ci); if (ci === cur.length) { del = true; setTimeout(type, 1400); return; } }
  else { el.textContent = cur.slice(0, --ci); if (ci === 0) { del = false; pi = (pi + 1) % phrases.length; } }
  setTimeout(type, del ? 45 : 90);
}
type();

const colors = ['var(--color-background-tertiary)', '#B5D4F4', '#85B7EB', '#378ADD', '#185FA5'];
const grid = document.getElementById('contrib-grid');
for (let w = 0; w < 36; w++) {
  const col = document.createElement('div');
  col.className = 'day-col';
  for (let d = 0; d < 7; d++) {
    const sq = document.createElement('div');
    sq.className = 'day-sq';
    const r = Math.random();
    const lvl = r < 0.38 ? 0 : r < 0.58 ? 1 : r < 0.74 ? 2 : r < 0.88 ? 3 : 4;
    sq.style.background = colors[lvl];
    col.appendChild(sq);
  }
  grid.appendChild(col);
}
</script>
