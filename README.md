<style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@200;300;400;500;600;700&display=swap');

  :root {
    --bg: #09090B;
    --surface: #18181B;
    --border: rgba(255,255,255,0.06);
    --border-hover: rgba(255,255,255,0.12);
    --text-primary: #FAFAFA;
    --text-secondary: #A1A1AA;
    --text-muted: #52525B;
    --accent: #10B981;
    --accent-dim: rgba(16,185,129,0.12);
    --accent-glow: rgba(16,185,129,0.25);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  .profile-readme {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    background: var(--bg);
    color: var(--text-primary);
    max-width: 960px;
    margin: 0 auto;
    padding: 0;
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }

  /* ── Hero ── */
  .hero {
    position: relative;
    padding: 80px 60px 60px;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent-glow), transparent);
  }

  .hero-grid {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background-image: radial-gradient(circle, rgba(255,255,255,0.03) 1px, transparent 1px);
    background-size: 24px 24px;
    animation: gridDrift 40s linear infinite;
  }

  @keyframes gridDrift {
    from { transform: translateY(0); }
    to { transform: translateY(24px); }
  }

  .hero-brand {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 48px;
    position: relative;
    z-index: 1;
  }

  .hero-brand-mark {
    font-size: 11px;
    font-weight: 600;
    color: var(--text-muted);
    letter-spacing: 0.3em;
  }

  .hero-brand-sep {
    width: 1px;
    height: 12px;
    background: var(--border);
  }

  .hero-brand-role {
    font-size: 10px;
    font-weight: 500;
    color: var(--text-muted);
    letter-spacing: 0.25em;
    text-transform: uppercase;
  }

  .hero-name {
    font-size: 84px;
    font-weight: 200;
    letter-spacing: -0.05em;
    line-height: 1;
    color: var(--text-primary);
    position: relative;
    z-index: 1;
    animation: fadeInUp 0.8s ease-out both;
  }

  .hero-name em {
    font-style: normal;
    font-weight: 700;
  }

  .hero-name .accent {
    color: var(--accent);
  }

  .hero-role {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-top: 24px;
    font-size: 13px;
    font-weight: 400;
    color: var(--text-secondary);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    position: relative;
    z-index: 1;
    animation: fadeInUp 0.8s ease-out 0.1s both;
  }

  .hero-role .sep {
    color: var(--text-muted);
    font-weight: 300;
  }

  .hero-tagline {
    margin-top: 20px;
    font-size: 17px;
    font-weight: 300;
    color: var(--text-muted);
    max-width: 520px;
    line-height: 1.7;
    position: relative;
    z-index: 1;
    animation: fadeInUp 0.8s ease-out 0.2s both;
  }

  /* Status */
  .hero-status {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 36px;
    position: relative;
    z-index: 1;
    animation: fadeInUp 0.8s ease-out 0.3s both;
  }

  .status-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--accent);
    position: relative;
  }

  .status-dot::after {
    content: '';
    position: absolute;
    inset: -4px;
    border-radius: 50%;
    background: var(--accent);
    animation: pulse 3s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 0; transform: scale(1); }
    50% { opacity: 0.3; transform: scale(1.8); }
  }

  .status-text {
    font-size: 12px;
    font-weight: 500;
    color: var(--text-secondary);
    letter-spacing: 0.02em;
  }

  /* CTAs */
  .hero-cta {
    display: flex;
    gap: 12px;
    margin-top: 40px;
    position: relative;
    z-index: 1;
    animation: fadeInUp 0.8s ease-out 0.4s both;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 12px 24px;
    border-radius: 8px;
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    text-decoration: none;
    transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
    cursor: pointer;
    border: none;
  }

  .btn-primary {
    background: var(--accent);
    color: #000;
  }

  .btn-primary:hover {
    background: #34D399;
    transform: translateY(-1px);
    box-shadow: 0 4px 20px var(--accent-glow);
  }

  .btn-secondary {
    background: transparent;
    color: var(--text-muted);
    border: 1px solid var(--border);
  }

  .btn-secondary:hover {
    color: var(--text-secondary);
    border-color: var(--border-hover);
    transform: translateY(-1px);
  }

  /* ── Section shared ── */
  .section {
    padding: 60px;
    position: relative;
  }

  .section-divider {
    height: 1px;
    background: var(--border);
    margin: 0 60px;
    position: relative;
  }

  .section-divider::after {
    content: '';
    position: absolute;
    left: 0; top: 0;
    width: 80px;
    height: 100%;
    background: linear-gradient(90deg, var(--accent-glow), transparent);
    animation: scanLine 8s ease-in-out infinite;
  }

  @keyframes scanLine {
    0%, 100% { left: 0; }
    50% { left: calc(100% - 80px); }
  }

  .section-label {
    font-size: 10px;
    font-weight: 500;
    color: var(--accent);
    letter-spacing: 0.3em;
    text-transform: uppercase;
    margin-bottom: 32px;
  }

  /* ── About ── */
  .about-text {
    font-size: 16px;
    font-weight: 300;
    color: var(--text-secondary);
    max-width: 640px;
    line-height: 1.8;
  }

  .about-text strong {
    color: var(--text-primary);
    font-weight: 500;
  }

  .about-meta {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 40px;
    margin-top: 48px;
  }

  .about-meta-group h4 {
    font-size: 9px;
    font-weight: 500;
    color: var(--text-muted);
    letter-spacing: 0.25em;
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .about-meta-group p {
    font-size: 13px;
    color: var(--text-secondary);
    line-height: 1.8;
  }

  .about-meta-group .accent {
    color: var(--accent);
    font-weight: 500;
  }

  .tech-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 12px;
  }

  .tech-pill {
    display: inline-block;
    padding: 4px 12px;
    border-radius: 6px;
    font-size: 12px;
    font-weight: 400;
    color: var(--text-secondary);
    background: var(--surface);
    border: 1px solid var(--border);
    transition: all 0.2s ease;
  }

  .tech-pill:hover {
    border-color: var(--border-hover);
    color: var(--text-primary);
  }

  /* ── Skills ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
  }

  .skill-group {
    background: var(--bg);
    padding: 32px 28px;
    transition: background 0.3s ease;
  }

  .skill-group:hover {
    background: var(--surface);
  }

  .skill-group-num {
    font-size: 10px;
    font-weight: 600;
    color: var(--text-muted);
    letter-spacing: 0.1em;
    margin-bottom: 8px;
  }

  .skill-group-title {
    font-size: 13px;
    font-weight: 600;
    color: var(--text-primary);
    margin-bottom: 4px;
  }

  .skill-group-line {
    width: 24px;
    height: 2px;
    background: var(--accent);
    border-radius: 1px;
    margin: 12px 0 16px;
    opacity: 0.6;
  }

  .skill-group ul {
    list-style: none;
  }

  .skill-group li {
    font-size: 12px;
    color: var(--text-muted);
    padding: 3px 0;
    transition: color 0.2s ease;
  }

  .skill-group:hover li {
    color: var(--text-secondary);
  }

  .skill-group li strong {
    color: var(--text-secondary);
    font-weight: 500;
  }

  .skill-group:hover li strong {
    color: var(--text-primary);
  }

  /* ── Projects ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 32px;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent-glow), transparent);
    opacity: 0;
    transition: opacity 0.3s ease;
  }

  .project-card:hover {
    border-color: var(--border-hover);
    transform: translateY(-2px);
    box-shadow: 0 8px 32px rgba(0,0,0,0.3);
  }

  .project-card:hover::before {
    opacity: 1;
  }

  .project-num {
    font-size: 10px;
    font-weight: 600;
    color: var(--text-muted);
    letter-spacing: 0.1em;
    margin-bottom: 16px;
  }

  .project-title {
    font-size: 20px;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.02em;
    margin-bottom: 12px;
  }

  .project-desc {
    font-size: 13px;
    color: var(--text-muted);
    line-height: 1.7;
    margin-bottom: 20px;
  }

  .project-tech {
    font-size: 9px;
    font-weight: 500;
    color: var(--text-muted);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .project-tags {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }

  .project-tag {
    font-size: 11px;
    color: var(--text-secondary);
    background: rgba(255,255,255,0.04);
    padding: 3px 10px;
    border-radius: 4px;
  }

  .project-links {
    display: flex;
    gap: 16px;
    margin-top: 20px;
    padding-top: 16px;
    border-top: 1px solid var(--border);
  }

  .project-link {
    font-size: 11px;
    font-weight: 500;
    color: var(--text-muted);
    text-decoration: none;
    letter-spacing: 0.05em;
    transition: color 0.2s ease;
    display: flex;
    align-items: center;
    gap: 4px;
  }

  .project-link:hover {
    color: var(--accent);
  }

  .project-link svg {
    width: 12px;
    height: 12px;
  }

  /* ── Footer ── */
  .footer {
    padding: 60px;
    text-align: center;
  }

  .footer-statement {
    font-size: 22px;
    font-weight: 300;
    color: var(--text-primary);
    letter-spacing: 0.12em;
    margin-bottom: 32px;
  }

  .footer-statement .accent {
    color: var(--accent);
  }

  .footer-links {
    display: flex;
    justify-content: center;
    gap: 32px;
    margin-bottom: 40px;
  }

  .footer-link {
    font-size: 11px;
    font-weight: 500;
    color: var(--text-muted);
    text-decoration: none;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: color 0.2s ease;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .footer-link:hover {
    color: var(--text-secondary);
  }

  .footer-link svg {
    width: 14px;
    height: 14px;
    opacity: 0.6;
  }

  .footer-brand {
    font-size: 8px;
    font-weight: 500;
    color: var(--text-muted);
    letter-spacing: 0.3em;
    opacity: 0.4;
  }

  /* ── Animations ── */
  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(16px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .fade-in { animation: fadeInUp 0.6s ease-out both; }
  .fade-in-d1 { animation: fadeInUp 0.6s ease-out 0.1s both; }
  .fade-in-d2 { animation: fadeInUp 0.6s ease-out 0.2s both; }
  .fade-in-d3 { animation: fadeInUp 0.6s ease-out 0.3s both; }
  .fade-in-d4 { animation: fadeInUp 0.6s ease-out 0.4s both; }
  .fade-in-d5 { animation: fadeInUp 0.6s ease-out 0.5s both; }
</style>

<div class="profile-readme">

  <!-- ═══ HERO ═══ -->
  <div class="hero">
    <div class="hero-grid"></div>

    <div class="hero-brand">
      <span class="hero-brand-mark">FK</span>
      <div class="hero-brand-sep"></div>
      <span class="hero-brand-role">Detection Engineer</span>
    </div>

    <h1 class="hero-name">
      Faiz <em>Khan</em><span class="accent">.</span>
    </h1>

    <div class="hero-role">
      <span>Detection Engineering</span>
      <span class="sep">/</span>
      <span>Blue Team</span>
      <span class="sep">/</span>
      <span>Threat Hunting</span>
    </div>

    <p class="hero-tagline">
      Building production-quality security tools that detect, protect, and respond.
    </p>

    <div class="hero-status">
      <div class="status-dot"></div>
      <span class="status-text">Available for collaboration</span>
    </div>

    <div class="hero-cta">
      <a href="#projects" class="btn btn-primary">View Projects</a>
      <a href="mailto:khanfaizmumbai@gmail.com" class="btn btn-secondary">Get in Touch</a>
    </div>
  </div>

  <div class="section-divider"></div>

  <!-- ═══ ABOUT ═══ -->
  <div class="section">
    <div class="section-label">About</div>

    <p class="about-text fade-in">
      Security engineer focused on <strong>detection engineering</strong>,
      <strong>threat hunting</strong>, and building tools that protect
      endpoints at scale. I work across the detection lifecycle — from log
      ingestion and parsing to rule creation, tuning, and automated response.
    </p>

    <div class="about-meta">
      <div class="about-meta-group fade-in-d1">
        <h4>Focus Areas</h4>
        <p>
          <span class="accent">Detection Engineering</span> · Threat Hunting ·
          Security Automation · SOC Operations · Incident Response
        </p>
      </div>

      <div class="about-meta-group fade-in-d2">
        <h4>Primary Stack</h4>
        <div class="tech-row">
          <span class="tech-pill">Python</span>
          <span class="tech-pill">Splunk</span>
          <span class="tech-pill">Elastic</span>
          <span class="tech-pill">Sigma</span>
          <span class="tech-pill">YARA</span>
          <span class="tech-pill">Sysmon</span>
          <span class="tech-pill">FastAPI</span>
          <span class="tech-pill">Docker</span>
          <span class="tech-pill">Git</span>
        </div>
      </div>
    </div>
  </div>

  <div class="section-divider"></div>

  <!-- ═══ SKILLS ═══ -->
  <div class="section">
    <div class="section-label">Capabilities</div>

    <div class="skills-grid">
      <div class="skill-group">
        <div class="skill-group-num">01</div>
        <div class="skill-group-title">Detection Engineering</div>
        <div class="skill-group-line"></div>
        <ul>
          <li><strong>Sigma</strong> Rules</li>
          <li><strong>YARA</strong> Patterns</li>
          <li>KQL Queries</li>
          <li>Splunk SPL</li>
          <li>Detection-as-Code</li>
        </ul>
      </div>

      <div class="skill-group">
        <div class="skill-group-num">02</div>
        <div class="skill-group-title">Threat Intelligence</div>
        <div class="skill-group-line"></div>
        <ul>
          <li><strong>IOC</strong> Analysis</li>
          <li><strong>Threat</strong> Hunting</li>
          <li>MITRE ATT&CK</li>
          <li>TTP Mapping</li>
          <li>OSINT</li>
        </ul>
      </div>

      <div class="skill-group">
        <div class="skill-group-num">03</div>
        <div class="skill-group-title">Security Operations</div>
        <div class="skill-group-line"></div>
        <ul>
          <li><strong>Splunk</strong> Enterprise</li>
          <li><strong>Elastic</strong> SIEM</li>
          <li>Log Analysis</li>
          <li>Incident Response</li>
          <li>Alert Triage</li>
        </ul>
      </div>

      <div class="skill-group">
        <div class="skill-group-num">04</div>
        <div class="skill-group-title">Engineering</div>
        <div class="skill-group-line"></div>
        <ul>
          <li><strong>Python</strong></li>
          <li><strong>FastAPI</strong></li>
          <li>Docker</li>
          <li>Git</li>
          <li>Linux / Windows</li>
        </ul>
      </div>
    </div>
  </div>

  <div class="section-divider"></div>

  <!-- ═══ PROJECTS ═══ -->
  <div class="section" id="projects">
    <div class="section-label">Projects</div>

    <div class="projects-grid">

      <div class="project-card fade-in-d1">
        <div class="project-num">01</div>
        <div class="project-title">Windows Event Analyzer</div>
        <p class="project-desc">
          High-fidelity platform for advanced endpoint telemetry analysis
          and threat simulation across Windows environments.
        </p>
        <div class="project-tech">Technologies</div>
        <div class="project-tags">
          <span class="project-tag">Python</span>
          <span class="project-tag">Sysmon</span>
          <span class="project-tag">KQL</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/KhanFaiz5426" class="project-link" target="_blank">
            <svg viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
            Source
          </a>
          <a href="#" class="project-link">
            <svg viewBox="0 0 16 16" fill="currentColor"><path d="M3.75 2h3.5a.75.75 0 010 1.5h-3.5a.25.25 0 00-.25.25v8.5c0 .138.112.25.25.25h8.5a.25.25 0 00.25-.25v-3.5a.75.75 0 011.5 0v3.5A1.75 1.75 0 0112.25 14h-8.5A1.75 1.75 0 012 12.25v-8.5C2 2.784 2.784 2 3.75 2zm6.854-1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.751.751 0 01-1.042-.018.751.751 0 01-.018-1.042l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1z"/></svg>
            Demo
          </a>
        </div>
      </div>

      <div class="project-card fade-in-d2">
        <div class="project-num">02</div>
        <div class="project-title">Linux Auth Analyzer</div>
        <p class="project-desc">
          Automated forensic analysis of SSH logs, auditd trails, and
          anomalous activity detection on Linux systems.
        </p>
        <div class="project-tech">Technologies</div>
        <div class="project-tags">
          <span class="project-tag">Python</span>
          <span class="project-tag">Linux</span>
          <span class="project-tag">Auditd</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/KhanFaiz5426" class="project-link" target="_blank">
            <svg viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
            Source
          </a>
          <a href="#" class="project-link">
            <svg viewBox="0 0 16 16" fill="currentColor"><path d="M3.75 2h3.5a.75.75 0 010 1.5h-3.5a.25.25 0 00-.25.25v8.5c0 .138.112.25.25.25h8.5a.25.25 0 00.25-.25v-3.5a.75.75 0 011.5 0v3.5A1.75 1.75 0 0112.25 14h-8.5A1.75 1.75 0 012 12.25v-8.5C2 2.784 2.784 2 3.75 2zm6.854-1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.751.751 0 01-1.042-.018.751.751 0 01-.018-1.042l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1z"/></svg>
            Demo
          </a>
        </div>
      </div>

      <div class="project-card fade-in-d3">
        <div class="project-num">03</div>
        <div class="project-title">IOC Detection Engine</div>
        <p class="project-desc">
          Enterprise-grade platform for fast behavioral analysis and IOC
          correlation across distributed environments.
        </p>
        <div class="project-tech">Technologies</div>
        <div class="project-tags">
          <span class="project-tag">Go</span>
          <span class="project-tag">Elastic</span>
          <span class="project-tag">Docker</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/KhanFaiz5426" class="project-link" target="_blank">
            <svg viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
            Source
          </a>
          <a href="#" class="project-link">
            <svg viewBox="0 0 16 16" fill="currentColor"><path d="M3.75 2h3.5a.75.75 0 010 1.5h-3.5a.25.25 0 00-.25.25v8.5c0 .138.112.25.25.25h8.5a.25.25 0 00.25-.25v-3.5a.75.75 0 011.5 0v3.5A1.75 1.75 0 0112.25 14h-8.5A1.75 1.75 0 012 12.25v-8.5C2 2.784 2.784 2 3.75 2zm6.854-1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.751.751 0 01-1.042-.018.751.751 0 01-.018-1.042l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1z"/></svg>
            Demo
          </a>
        </div>
      </div>

      <div class="project-card fade-in-d4">
        <div class="project-num">04</div>
        <div class="project-title">Sigma Rule Collection</div>
        <p class="project-desc">
          Production-ready detection rules for Windows, Linux, and cloud
          environments. Tuned for high fidelity and low noise.
        </p>
        <div class="project-tech">Technologies</div>
        <div class="project-tags">
          <span class="project-tag">Sigma</span>
          <span class="project-tag">YARA</span>
          <span class="project-tag">Splunk</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/KhanFaiz5426" class="project-link" target="_blank">
            <svg viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
            Source
          </a>
          <a href="#" class="project-link">
            <svg viewBox="0 0 16 16" fill="currentColor"><path d="M3.75 2h3.5a.75.75 0 010 1.5h-3.5a.25.25 0 00-.25.25v8.5c0 .138.112.25.25.25h8.5a.25.25 0 00.25-.25v-3.5a.75.75 0 011.5 0v3.5A1.75 1.75 0 0112.25 14h-8.5A1.75 1.75 0 012 12.25v-8.5C2 2.784 2.784 2 3.75 2zm6.854-1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.751.751 0 01-1.042-.018.751.751 0 01-.018-1.042l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1z"/></svg>
            Demo
          </a>
        </div>
      </div>

    </div>
  </div>

  <div class="section-divider"></div>

  <!-- ═══ FOOTER ═══ -->
  <div class="footer">
    <div class="footer-statement">
      BUILDING DEFENSE<span class="accent">.</span>
    </div>

    <div class="footer-links">
      <a href="https://github.com/KhanFaiz5426" class="footer-link" target="_blank">
        <svg viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
        GitHub
      </a>
      <a href="https://www.linkedin.com/in/faiz-khan-b03a2a3a7" class="footer-link" target="_blank">
        <svg viewBox="0 0 16 16" fill="currentColor"><path d="M0 1.146C0 .513.526 0 1.175 0h13.65C15.474 0 16 .513 16 1.146v13.708c0 .633-.526 1.146-1.175 1.146H1.175C.526 16 0 15.487 0 14.854V1.146zm4.943 12.248V6.169H2.542v7.225h2.401zm-1.2-8.212c.837 0 1.358-.554 1.358-1.248-.015-.709-.52-1.248-1.342-1.248-.822 0-1.359.54-1.359 1.248 0 .694.521 1.248 1.327 1.248h.016zm4.908 8.212V9.359c0-.216.016-.432.08-.586.173-.431.568-.878 1.232-.878.869 0 1.216.662 1.216 1.634v3.865h2.401V9.25c0-2.22-1.184-3.252-2.764-3.252-1.274 0-1.845.7-2.165 1.193v.025h-.016a5.54 5.54 0 01.016-.025V6.169h-2.4c.03.678 0 7.225 0 7.225h2.4z"/></svg>
        LinkedIn
      </a>
      <a href="mailto:khanfaizmumbai@gmail.com" class="footer-link">
        <svg viewBox="0 0 16 16" fill="currentColor"><path d="M1.75 2h12.5c.966 0 1.75.784 1.75 1.75v8.5A1.75 1.75 0 0114.25 14H1.75A1.75 1.75 0 010 12.25v-8.5C0 2.784.784 2 1.75 2zM1.5 12.251c0 .138.112.25.25.25h12.5a.25.25 0 00.25-.25V5.809L8.38 9.397a.75.75 0 01-.76 0L1.5 5.809v6.442z"/></svg>
        Email
      </a>
      <a href="#" class="footer-link">
        <svg viewBox="0 0 16 16" fill="currentColor"><path d="M3.5 1.75a.25.25 0 01.25-.25h3.168a.75.75 0 000-1.5H3.75A1.75 1.75 0 002 1.75v12.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 14.25V5.612a.75.75 0 00-.22-.53l-3.14-3.14a.75.75 0 00-.53-.22H3.75a1.75 1.75 0 00-1.75 1.75v.001z"/></svg>
        Resume
      </a>
    </div>

    <div class="footer-brand">FK · 2024</div>
  </div>

</div>
