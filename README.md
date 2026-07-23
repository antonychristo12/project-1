<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Smart Water Quality Monitoring System — Project Overview</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&family=Inter:wght@400;500;600&display=swap');

  :root{
    --ink:#0b1f2a;
    --deep:#0e2f3d;
    --teal:#12505f;
    --teal-light:#1c7a8c;
    --aqua:#3fb8c4;
    --foam:#eef7f6;
    --paper:#f6f3ec;
    --line:#c9d8d4;
    --amber:#d98e3f;
    --text:#152a2f;
    --muted:#5a6f70;
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--paper);
    color:var(--text);
    font-family:'Inter',sans-serif;
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3,.disp{font-family:'Space Grotesk',sans-serif;}
  .mono{font-family:'IBM Plex Mono',monospace;}

  /* ---------- HERO ---------- */
  .hero{
    background:
      radial-gradient(circle at 15% 20%, rgba(63,184,196,0.25), transparent 45%),
      radial-gradient(circle at 85% 0%, rgba(217,142,63,0.12), transparent 40%),
      linear-gradient(180deg,var(--ink) 0%, var(--deep) 100%);
    color:var(--foam);
    padding:64px 6vw 56px;
    position:relative;
    overflow:hidden;
  }
  .hero::after{
    content:"";
    position:absolute; inset:0;
    background-image:
      repeating-linear-gradient(0deg, rgba(255,255,255,0.035) 0px, rgba(255,255,255,0.035) 1px, transparent 1px, transparent 42px);
    pointer-events:none;
  }
  .eyebrow{
    font-family:'IBM Plex Mono',monospace;
    font-size:12.5px;
    letter-spacing:0.14em;
    text-transform:uppercase;
    color:var(--aqua);
    display:flex; align-items:center; gap:10px;
    margin-bottom:22px;
  }
  .eyebrow .dot{width:7px;height:7px;border-radius:50%;background:var(--aqua);box-shadow:0 0 12px var(--aqua);}
  h1.title{
    font-size:clamp(34px,5vw,58px);
    line-height:1.04;
    font-weight:700;
    margin:0 0 18px;
    max-width:16ch;
    letter-spacing:-0.01em;
  }
  .hero-sub{
    max-width:56ch;
    font-size:16.5px;
    line-height:1.6;
    color:#c3d6d3;
    margin-bottom:34px;
  }
  .author-row{
    font-size:12.5px; letter-spacing:0.04em; color:var(--aqua);
    margin-bottom:30px; display:flex; align-items:center; gap:10px;
  }
  .author-row .sep{color:rgba(255,255,255,0.3);}
  .stat-row{
    display:flex; flex-wrap:wrap; gap:0;
    border-top:1px solid rgba(255,255,255,0.14);
    margin-top:10px;
  }
  .stat{
    flex:1 1 140px;
    padding:18px 22px 4px 0;
    border-right:1px solid rgba(255,255,255,0.14);
    margin-right:22px;
  }
  .stat:last-child{border-right:none;}
  .stat .num{font-family:'Space Grotesk',sans-serif; font-size:26px; font-weight:600; color:#fff;}
  .stat .lbl{font-family:'IBM Plex Mono',monospace; font-size:11px; letter-spacing:0.06em; color:#8fb3ae; text-transform:uppercase; margin-top:4px;}

  /* ---------- SECTION SHELL ---------- */
  section{padding:64px 6vw;}
  .section-head{margin-bottom:34px; max-width:70ch;}
  .kicker{
    font-family:'IBM Plex Mono',monospace;
    font-size:11.5px;
    letter-spacing:0.12em;
    text-transform:uppercase;
    color:var(--teal-light);
    margin-bottom:10px;
  }
  h2.section-title{font-size:clamp(22px,3vw,30px); margin:0 0 12px; font-weight:700; color:var(--ink);}
  .section-desc{color:var(--muted); font-size:15px; line-height:1.6;}

  /* ---------- WHICH PROJECT ---------- */
  .which-grid{
    display:grid; grid-template-columns:1.1fr 1fr; gap:36px;
    background:#fff; border:1px solid var(--line); border-radius:4px; padding:32px;
  }
  .which-grid p{font-size:15px; line-height:1.75; color:var(--text); margin:0 0 14px;}
  .which-grid ul{margin:0; padding-left:18px; color:var(--text); font-size:14.5px; line-height:1.9;}
  .which-col h3{
    font-family:'IBM Plex Mono',monospace; font-size:12px; letter-spacing:0.08em;
    text-transform:uppercase; color:var(--teal); margin:0 0 12px;
  }
  @media (max-width:800px){.which-grid{grid-template-columns:1fr;}}

  /* ---------- FRAMEWORK STRIP ---------- */
  .framework-strip{
    display:flex; align-items:center; gap:28px; flex-wrap:wrap;
    background:var(--deep); color:var(--foam);
    border-radius:4px; padding:26px 30px; margin-top:28px;
  }
  .framework-strip .badge{
    font-family:'Space Grotesk',sans-serif; font-weight:700; font-size:20px;
    background:var(--aqua); color:var(--ink); padding:6px 16px; border-radius:3px;
    letter-spacing:0.02em;
  }
  .framework-strip .fw-text{font-size:14px; line-height:1.6; color:#c3d6d3; max-width:70ch;}
  .framework-strip .fw-text b{color:#fff;}

  /* ---------- ACTIVITIES TABLE ---------- */
  .table-wrap{overflow-x:auto; border:1px solid var(--line); border-radius:4px; background:#fff;}
  table{width:100%; border-collapse:collapse; min-width:920px;}
  thead th{
    font-family:'IBM Plex Mono',monospace; font-size:10.5px; letter-spacing:0.07em; text-transform:uppercase;
    text-align:left; color:#fff; background:var(--teal); padding:12px 14px; white-space:nowrap;
  }
  tbody td{
    padding:12px 14px; font-size:13.5px; border-top:1px solid var(--line); vertical-align:top;
  }
  tbody tr:nth-child(even){background:#fbfaf6;}
  tbody tr:hover{background:var(--foam);}
  td.id, th.id{font-family:'IBM Plex Mono',monospace; color:var(--teal-light); font-weight:600;}
  .pill{
    display:inline-block; font-family:'IBM Plex Mono',monospace; font-size:11px; font-weight:600;
    padding:3px 9px; border-radius:20px; letter-spacing:0.03em;
  }
  .pill.s1{background:#e4f2ef; color:#0e6b5c;}
  .pill.s2{background:#eaf1fb; color:#20518f;}
  .pill.s3{background:#fbeee0; color:#a15f16;}
  .sp{font-family:'IBM Plex Mono',monospace; font-weight:600; color:var(--ink);}
  .pred{font-family:'IBM Plex Mono',monospace; color:var(--muted); font-size:12.5px;}
  .pred.none{color:#a9b8b4; font-style:italic;}

  /* ---------- SPRINTS ---------- */
  .sprint-grid{display:grid; grid-template-columns:repeat(3,1fr); gap:20px;}
  @media (max-width:900px){.sprint-grid{grid-template-columns:1fr;}}
  .sprint-card{
    background:#fff; border:1px solid var(--line); border-radius:4px; overflow:hidden;
    display:flex; flex-direction:column;
  }
  .sprint-card .sc-head{
    padding:20px 22px; color:#fff;
  }
  .sprint-card:nth-child(1) .sc-head{background:#0e6b5c;}
  .sprint-card:nth-child(2) .sc-head{background:#20518f;}
  .sprint-card:nth-child(3) .sc-head{background:#a15f16;}
  .sc-head .sc-num{font-family:'IBM Plex Mono',monospace; font-size:11px; letter-spacing:0.1em; text-transform:uppercase; opacity:0.85;}
  .sc-head h3{margin:6px 0 4px; font-size:19px;}
  .sc-head .sc-dur{font-family:'IBM Plex Mono',monospace; font-size:12px; opacity:0.9;}
  .sc-body{padding:18px 22px; flex:1; display:flex; flex-direction:column; gap:10px;}
  .sc-item{
    display:flex; justify-content:space-between; gap:10px; font-size:13px;
    padding-bottom:9px; border-bottom:1px dashed var(--line);
  }
  .sc-item:last-of-type{border-bottom:none;}
  .sc-item .name{color:var(--text);}
  .sc-item .pts{font-family:'IBM Plex Mono',monospace; color:var(--teal-light); font-weight:600; white-space:nowrap;}
  .sc-total{
    margin-top:auto; padding-top:12px; border-top:1px solid var(--line);
    display:flex; justify-content:space-between; font-family:'IBM Plex Mono',monospace; font-size:13px; font-weight:600; color:var(--ink);
  }

  /* ---------- DEPENDENCY FLOW (signature element) ---------- */
  .flow-wrap{
    background:#fff; border:1px solid var(--line); border-radius:4px; padding:36px 30px 30px;
    overflow-x:auto;
  }
  .flow{
    display:flex; align-items:flex-start; gap:0; min-width:1180px; position:relative;
  }
  .flow-col{
    display:flex; flex-direction:column; align-items:center; width:78px; flex-shrink:0; position:relative;
  }
  .flow-node{
    width:56px; height:56px; border-radius:50%;
    background:var(--foam); border:2px solid var(--teal-light);
    display:flex; align-items:center; justify-content:center;
    font-family:'IBM Plex Mono',monospace; font-weight:700; font-size:13px; color:var(--teal);
    position:relative; z-index:2;
  }
  .flow-node.start{background:var(--aqua); color:#fff; border-color:var(--aqua);}
  .flow-label{
    margin-top:10px; font-size:10.5px; text-align:center; color:var(--muted); line-height:1.35; max-width:90px;
  }
  .flow-line{
    position:absolute; top:28px; left:50%; height:2px; background:var(--line); z-index:1;
  }
  .flow-connector{
    flex:0 0 40px; height:56px; display:flex; align-items:center; justify-content:center; margin-top:0;
  }
  .flow-connector svg{overflow:visible;}

  /* legend */
  .legend{display:flex; gap:22px; margin-top:26px; flex-wrap:wrap;}
  .legend-item{display:flex; align-items:center; gap:8px; font-size:12px; color:var(--muted);}
  .legend-dot{width:12px;height:12px;border-radius:50%;}

  .net-block{
    background:#fff; border:1px solid var(--line); border-radius:4px;
    padding:28px 26px 24px; margin-bottom:28px;
  }
  .net-title{
    font-size:13px; letter-spacing:0.08em; text-transform:uppercase; color:var(--teal);
    margin:0 0 6px;
  }
  .net-desc{font-size:13.5px; color:var(--muted); line-height:1.6; margin:0 0 18px; max-width:80ch;}
  .aon-wrap{overflow-x:auto;}
  .aon-wrap svg{min-width:1300px; width:100%; height:auto; display:block;}

  footer{
    padding:30px 6vw 40px; text-align:center; color:var(--muted); font-size:12.5px;
    font-family:'IBM Plex Mono',monospace; border-top:1px solid var(--line); background:var(--foam);
  }

  @media (prefers-reduced-motion:no-preference){
    .fade-up{animation:fadeUp .6s ease both;}
    @keyframes fadeUp{from{opacity:0; transform:translateY(10px);} to{opacity:1; transform:translateY(0);}}
  }
</style>
</head>
<body>

<div class="hero">
  <div class="eyebrow"><span class="dot"></span>CSE DEPARTMENT · PROJECT CHARTER</div>
  <h1 class="title">Smart Water Quality Monitoring System</h1>
  <p class="hero-sub">An IoT + web-dashboard system that senses pH, turbidity, TDS, and temperature in real time, and alerts communities when water becomes unsafe to drink — planned and tracked using Scrum.</p>
  <div class="author-row mono">
    <span>Antony Christo A</span><span class="sep">·</span><span>2nd Year, CSE</span>
  </div>
  <div class="stat-row">
    <div class="stat"><div class="num">15</div><div class="lbl">Activities</div></div>
    <div class="stat"><div class="num">3</div><div class="lbl">Sprints</div></div>
    <div class="stat"><div class="num">83</div><div class="lbl">Story Points</div></div>
    <div class="stat"><div class="num">10 wks</div><div class="lbl">Duration</div></div>
    <div class="stat"><div class="num">Scrum</div><div class="lbl">Framework</div></div>
  </div>
</div>

<section id="which">
  <div class="section-head">
    <div class="kicker">01 · Which Project</div>
    <h2 class="section-title">Project identity</h2>
  </div>
  <div class="which-grid">
    <div class="which-col">
      <h3>Problem &amp; Solution</h3>
      <p>Access to safe drinking water is a persistent challenge in rural and semi-urban areas, where contamination often goes undetected until it causes illness. This project builds a low-cost, connected monitoring station that continuously measures water quality and flags unsafe readings before they reach consumers.</p>
      <p>An ESP32-based sensor node reads pH, turbidity, TDS, and temperature, transmits the data over WiFi, and a backend service checks each reading against WHO safe-water thresholds — triggering an SMS/email alert and updating a live dashboard when a limit is crossed.</p>
    </div>
    <div class="which-col">
      <h3>Target users</h3>
      <ul>
        <li>Rural water boards &amp; panchayats</li>
        <li>School and community water points</li>
        <li>NGOs running clean-water programs</li>
        <li>Municipal water quality officers</li>
      </ul>
      <h3 style="margin-top:22px;">Core deliverables</h3>
      <ul>
        <li>Sensor node (hardware + firmware)</li>
        <li>Backend API &amp; database</li>
        <li>Real-time analytics dashboard</li>
        <li>Threshold-based alert system</li>
      </ul>
    </div>
  </div>

  <div class="framework-strip">
    <div class="badge mono">SCRUM</div>
    <div class="fw-text">Delivered across <b>3 sprints over 10 weeks</b> — Sprint 1 (3 weeks), Sprint 2 (4 weeks), Sprint 3 (3 weeks). Each sprint ends with a working increment reviewed at a sprint review, followed by a retrospective. Backlog is prioritized and re-estimated at each sprint planning session using story points (Fibonacci scale).</div>
  </div>
</section>

<section id="activities">
  <div class="section-head">
    <div class="kicker">02 · Product Backlog</div>
    <h2 class="section-title">Project activities</h2>
    <p class="section-desc">15 activities across hardware, backend, and frontend workstreams, spanning a 10-week timeline, each estimated in story points and mapped to its predecessor(s).</p>
  </div>
  <div class="table-wrap">
    <table>
      <thead>
        <tr>
          <th class="id">ID</th>
          <th>Activity</th>
          <th>Sprint</th>
          <th>Story Points</th>
          <th>Duration</th>
          <th>Predecessor</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="id">A1</td>
          <td>Requirement gathering &amp; WHO water-safety threshold research</td>
          <td><span class="pill s1">Sprint 1</span></td>
          <td class="sp">3</td>
          <td>3 days</td>
          <td class="pred none">None</td>
        </tr>
        <tr>
          <td class="id">A2</td>
          <td>Select sensors (pH, turbidity, TDS, temperature) &amp; microcontroller</td>
          <td><span class="pill s1">Sprint 1</span></td>
          <td class="sp">3</td>
          <td>2 days</td>
          <td class="pred">A1</td>
        </tr>
        <tr>
          <td class="id">A3</td>
          <td>Circuit design &amp; sensor wiring on ESP32</td>
          <td><span class="pill s1">Sprint 1</span></td>
          <td class="sp">5</td>
          <td>4 days</td>
          <td class="pred">A2</td>
        </tr>
        <tr>
          <td class="id">A4</td>
          <td>Firmware: sensor reading &amp; calibration logic (C++)</td>
          <td><span class="pill s1">Sprint 1</span></td>
          <td class="sp">8</td>
          <td>5 days</td>
          <td class="pred">A3</td>
        </tr>
        <tr>
          <td class="id">A5</td>
          <td>WiFi data transmission (HTTP/MQTT) from ESP32</td>
          <td><span class="pill s1">Sprint 1</span></td>
          <td class="sp">5</td>
          <td>3 days</td>
          <td class="pred">A4</td>
        </tr>
        <tr>
          <td class="id">A6</td>
          <td>Database schema design for sensor readings</td>
          <td><span class="pill s1">Sprint 1</span></td>
          <td class="sp">3</td>
          <td>3 days</td>
          <td class="pred">A1</td>
        </tr>
        <tr>
          <td class="id">A7</td>
          <td>Backend API to receive &amp; store sensor data</td>
          <td><span class="pill s2">Sprint 2</span></td>
          <td class="sp">8</td>
          <td>5 days</td>
          <td class="pred">A5, A6</td>
        </tr>
        <tr>
          <td class="id">A8</td>
          <td>Threshold comparison engine (safe/unsafe logic)</td>
          <td><span class="pill s2">Sprint 2</span></td>
          <td class="sp">5</td>
          <td>4 days</td>
          <td class="pred">A7</td>
        </tr>
        <tr>
          <td class="id">A9</td>
          <td>Alert module — SMS/email notification integration</td>
          <td><span class="pill s2">Sprint 2</span></td>
          <td class="sp">5</td>
          <td>3 days</td>
          <td class="pred">A8</td>
        </tr>
        <tr>
          <td class="id">A10</td>
          <td>Historical data storage &amp; query optimization</td>
          <td><span class="pill s2">Sprint 2</span></td>
          <td class="sp">5</td>
          <td>3 days</td>
          <td class="pred">A7</td>
        </tr>
        <tr>
          <td class="id">A11</td>
          <td>Dashboard UI: live readings &amp; status indicators</td>
          <td><span class="pill s2">Sprint 2</span></td>
          <td class="sp">8</td>
          <td>5 days</td>
          <td class="pred">A8</td>
        </tr>
        <tr>
          <td class="id">A12</td>
          <td>Dashboard: historical trend graphs</td>
          <td><span class="pill s3">Sprint 3</span></td>
          <td class="sp">5</td>
          <td>4 days</td>
          <td class="pred">A10, A11</td>
        </tr>
        <tr>
          <td class="id">A13</td>
          <td>Field deployment &amp; sensor calibration on-site</td>
          <td><span class="pill s3">Sprint 3</span></td>
          <td class="sp">8</td>
          <td>5 days</td>
          <td class="pred">A9, A11</td>
        </tr>
        <tr>
          <td class="id">A14</td>
          <td>End-to-end testing &amp; bug fixing</td>
          <td><span class="pill s3">Sprint 3</span></td>
          <td class="sp">5</td>
          <td>4 days</td>
          <td class="pred">A13</td>
        </tr>
        <tr>
          <td class="id">A15</td>
          <td>Documentation &amp; final demo preparation</td>
          <td><span class="pill s3">Sprint 3</span></td>
          <td class="sp">2</td>
          <td>2 days</td>
          <td class="pred">A14</td>
        </tr>
      </tbody>
    </table>
  </div>
</section>

<section id="sprints">
  <div class="section-head">
    <div class="kicker">03 · Sprint Breakdown</div>
    <h2 class="section-title">Sprints &amp; story points</h2>
    <p class="section-desc">Each sprint runs 2 weeks. Points follow the Fibonacci scale (1, 2, 3, 5, 8).</p>
  </div>
  <div class="sprint-grid">
    <div class="sprint-card">
      <div class="sc-head">
        <div class="sc-num mono">SPRINT 1 · WK 1–3</div>
        <h3>Hardware &amp; Sensing</h3>
        <div class="sc-dur mono">Foundation layer</div>
      </div>
      <div class="sc-body">
        <div class="sc-item"><span class="name">A1 Requirement gathering</span><span class="pts">3 pts</span></div>
        <div class="sc-item"><span class="name">A2 Sensor selection</span><span class="pts">3 pts</span></div>
        <div class="sc-item"><span class="name">A3 Circuit design</span><span class="pts">5 pts</span></div>
        <div class="sc-item"><span class="name">A4 Firmware logic</span><span class="pts">8 pts</span></div>
        <div class="sc-item"><span class="name">A5 WiFi transmission</span><span class="pts">5 pts</span></div>
        <div class="sc-item"><span class="name">A6 DB schema design</span><span class="pts">3 pts</span></div>
        <div class="sc-total"><span>Sprint total</span><span>27 pts</span></div>
      </div>
    </div>
    <div class="sprint-card">
      <div class="sc-head">
        <div class="sc-num mono">SPRINT 2 · WK 4–7</div>
        <h3>Backend &amp; Alerts</h3>
        <div class="sc-dur mono">Core logic layer</div>
      </div>
      <div class="sc-body">
        <div class="sc-item"><span class="name">A7 Backend API</span><span class="pts">8 pts</span></div>
        <div class="sc-item"><span class="name">A8 Threshold engine</span><span class="pts">5 pts</span></div>
        <div class="sc-item"><span class="name">A9 Alert integration</span><span class="pts">5 pts</span></div>
        <div class="sc-item"><span class="name">A10 Historical storage</span><span class="pts">5 pts</span></div>
        <div class="sc-item"><span class="name">A11 Dashboard: live UI</span><span class="pts">8 pts</span></div>
        <div class="sc-total"><span>Sprint total</span><span>31 pts</span></div>
      </div>
    </div>
    <div class="sprint-card">
      <div class="sc-head">
        <div class="sc-num mono">SPRINT 3 · WK 8–10</div>
        <h3>Deployment &amp; Polish</h3>
