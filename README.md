<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>R Shruthi Yadav — Backend Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,300;0,400;0,500;1,400&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0c0f;
    --surface: #111418;
    --border: #1e2329;
    --accent: #00e5a0;
    --accent2: #0084ff;
    --muted: #4a5568;
    --text: #e2e8f0;
    --text-dim: #94a3b8;
    --mono: 'DM Mono', monospace;
    --sans: 'Syne', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--mono);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid lines background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,160,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,160,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 780px;
    margin: 0 auto;
    padding: 60px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    border-left: 3px solid var(--accent);
    padding-left: 20px;
    margin-bottom: 56px;
    animation: fadeUp 0.6s ease both;
  }

  .header .label {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 0.2em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 10px;
  }

  .header h1 {
    font-family: var(--sans);
    font-size: clamp(28px, 6vw, 44px);
    font-weight: 800;
    color: var(--text);
    line-height: 1.1;
    letter-spacing: -0.02em;
  }

  .header .role {
    font-size: 13px;
    color: var(--text-dim);
    margin-top: 10px;
    line-height: 1.7;
    max-width: 520px;
  }

  /* ── SECTION ── */
  .section {
    margin-bottom: 44px;
    animation: fadeUp 0.6s ease both;
  }

  .section:nth-child(2) { animation-delay: 0.08s; }
  .section:nth-child(3) { animation-delay: 0.14s; }
  .section:nth-child(4) { animation-delay: 0.20s; }
  .section:nth-child(5) { animation-delay: 0.26s; }
  .section:nth-child(6) { animation-delay: 0.32s; }

  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 18px;
  }

  .section-header h2 {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
    font-weight: 500;
  }

  .section-header::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── TECH STACK ── */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 10px;
  }

  .stack-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 12px 14px;
    transition: border-color 0.2s, transform 0.2s;
  }

  .stack-item:hover {
    border-color: var(--accent);
    transform: translateY(-2px);
  }

  .stack-item .stack-label {
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 6px;
    font-weight: 500;
  }

  .stack-item .stack-tags {
    font-size: 12.5px;
    color: var(--text-dim);
    line-height: 1.6;
  }

  /* ── CS FOUNDATIONS ── */
  .foundations {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tag {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--text-dim);
    font-size: 11.5px;
    padding: 5px 12px;
    border-radius: 4px;
    transition: all 0.2s;
    font-family: var(--mono);
  }

  .tag:hover {
    border-color: var(--accent2);
    color: var(--accent2);
  }

  /* ── FOCUS AREAS ── */
  .focus-list {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .focus-item {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    font-size: 13px;
    color: var(--text-dim);
    line-height: 1.6;
    padding: 10px 14px;
    background: var(--surface);
    border-left: 2px solid var(--border);
    border-radius: 0 4px 4px 0;
    transition: border-color 0.2s, color 0.2s;
  }

  .focus-item:hover {
    border-color: var(--accent);
    color: var(--text);
  }

  .focus-item .icon {
    color: var(--accent);
    font-size: 11px;
    margin-top: 3px;
    flex-shrink: 0;
  }

  /* ── LEETCODE ── */
  .leetcode-wrap {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    gap: 14px;
    align-items: flex-start;
  }

  .lc-link {
    font-size: 12px;
    color: var(--accent2);
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 6px;
    transition: opacity 0.2s;
  }

  .lc-link:hover { opacity: 0.75; }

  .leetcode-cards {
    display: flex;
    flex-direction: column;
    gap: 10px;
    width: 100%;
  }

  .leetcode-cards img {
    border-radius: 6px;
    max-width: 100%;
    display: block;
  }

  /* ── CONTACT ── */
  .contact-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .contact-chip {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 9px 16px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    text-decoration: none;
    font-size: 12.5px;
    color: var(--text-dim);
    transition: all 0.2s;
    font-family: var(--mono);
  }

  .contact-chip:hover {
    border-color: var(--accent);
    color: var(--text);
  }

  .contact-chip .dot {
    width: 7px;
    height: 7px;
    border-radius: 50%;
    background: var(--accent);
    flex-shrink: 0;
  }

  .contact-chip.email .dot { background: var(--accent2); }

  /* ── STATUS BAR ── */
  .statusbar {
    margin-top: 60px;
    padding-top: 20px;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 8px;
  }

  .statusbar span {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.08em;
  }

  .status-dot {
    display: inline-block;
    width: 6px;
    height: 6px;
    background: var(--accent);
    border-radius: 50%;
    margin-right: 6px;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <header class="header">
    <p class="label">// software engineer · backend</p>
    <h1>R Shruthi Yadav</h1>
    <p class="role">
      CS undergraduate building production-oriented backend systems with strong foundations in data structures, databases, and system-level thinking. Focused on writing clean, maintainable code beyond academic implementations.
    </p>
  </header>

  <!-- TECH STACK -->
  <section class="section">
    <div class="section-header"><h2>Tech Stack</h2></div>
    <div class="stack-grid">
      <div class="stack-item">
        <div class="stack-label">Languages</div>
        <div class="stack-tags">Java · SQL · Python</div>
      </div>
      <div class="stack-item">
        <div class="stack-label">Backend</div>
        <div class="stack-tags">REST APIs · OOP · Spring Boot (Learning)</div>
      </div>
      <div class="stack-item">
        <div class="stack-label">Tools</div>
        <div class="stack-tags">Git · GitHub · Linux</div>
      </div>
    </div>
  </section>

  <!-- CS FOUNDATIONS -->
  <section class="section">
    <div class="section-header"><h2>CS Foundations</h2></div>
    <div class="foundations">
      <span class="tag">Data Structures</span>
      <span class="tag">Algorithms</span>
      <span class="tag">DBMS</span>
      <span class="tag">Operating Systems</span>
      <span class="tag">Computer Networks</span>
    </div>
  </section>

  <!-- FOCUS -->
  <section class="section">
    <div class="section-header"><h2>Focus Areas</h2></div>
    <div class="focus-list">
      <div class="focus-item"><span class="icon">▸</span>Backend engineering using Java ecosystem</div>
      <div class="focus-item"><span class="icon">▸</span>Scalable API design and system logic clarity</div>
      <div class="focus-item"><span class="icon">▸</span>Linux-based development workflows</div>
      <div class="focus-item"><span class="icon">▸</span>Open-source contribution readiness (GSoC)</div>
    </div>
  </section>

  <!-- LEETCODE -->
  <section class="section">
    <div class="section-header"><h2>Problem Solving</h2></div>
    <div class="leetcode-wrap">
      <a class="lc-link" href="https://leetcode.com/shruthi_19" target="_blank">
        <span>↗</span> leetcode.com/shruthi_19
      </a>
      <div class="leetcode-cards">
        <img src="https://leetcard.jacoblin.cool/shruthi_19?theme=dark&font=JetBrains%20Mono" alt="LeetCode Stats" />
        <img src="https://leetcode-badge-showcase.vercel.app/api?username=shruthi_19&theme=dark" alt="LeetCode Badges" />
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="section">
    <div class="section-header"><h2>Contact</h2></div>
    <div class="contact-row">
      <a class="contact-chip" href="https://linkedin.com/in/rshruthiyadav" target="_blank">
        <span class="dot"></span>linkedin.com/in/rshruthiyadav
      </a>
      <a class="contact-chip email" href="mailto:shruthii1819@gmail.com">
        <span class="dot"></span>shruthii1819@gmail.com
      </a>
    </div>
  </section>

  <!-- STATUS BAR -->
  <div class="statusbar">
    <span><span class="status-dot"></span>open to opportunities</span>
    <span>backend · java · systems</span>
  </div>

</div>
</body>
</html>
