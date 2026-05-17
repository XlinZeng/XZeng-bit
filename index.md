<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Xianlin Zeng — Homepage</title>
<style>
  :root {
    --navy: #1a2332;
    --accent: #c9a84c;
    --bg: #f9f8f5;
    --card: #ffffff;
    --text: #2d2d2d;
    --muted: #6b7280;
    --border: #e5e7eb;
    --link: #2563eb;
  }
  * { margin:0; padding:0; box-sizing:border-box; }
  body {
    font-family: "Inter", "Segoe UI", "PingFang SC", "Microsoft YaHei", sans-serif;
    background: var(--bg);
    color: var(--text);
    line-height: 1.7;
  }

  /* ── HEADER ── */
  .header {
    background: var(--navy);
    color: #fff;
    padding: 3rem 2rem 2rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .header::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 4px;
    background: linear-gradient(90deg, var(--accent), #e5b93c, var(--accent));
  }
  .header h1 {
    font-size: 2.2rem;
    font-weight: 700;
    letter-spacing: 1px;
    margin-bottom: .2rem;
  }
  .header h2 {
    font-size: 1.1rem;
    font-weight: 400;
    color: #bcc4d0;
  }
  .header .affil {
    margin-top: .6rem;
    font-size: .92rem;
    color: #9ca3af;
    line-height: 1.6;
  }
  .header .links {
    margin-top: .8rem;
    display: flex;
    justify-content: center;
    gap: 1.4rem;
    flex-wrap: wrap;
  }
  .header .links a {
    color: var(--accent);
    text-decoration: none;
    font-size: .9rem;
    transition: color .2s;
  }
  .header .links a:hover { color: #fff; }

  /* ── TABS ── */
  .tab-nav {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 0;
    background: #fff;
    border-bottom: 2px solid var(--border);
    position: sticky;
    top: 0;
    z-index: 100;
    box-shadow: 0 1px 4px rgba(0,0,0,.04);
  }
  .tab-btn {
    padding: .85rem 1.5rem;
    border: none;
    background: transparent;
    font-size: .92rem;
    cursor: pointer;
    color: var(--muted);
    font-weight: 500;
    border-bottom: 3px solid transparent;
    transition: all .2s;
    white-space: nowrap;
  }
  .tab-btn:hover { color: var(--text); background: #f3f4f6; }
  .tab-btn.active {
    color: var(--navy);
    border-bottom-color: var(--accent);
    font-weight: 600;
  }

  /* ── MAIN ── */
  .container {
    max-width: 920px;
    margin: 0 auto;
    padding: 2rem 1.5rem 4rem;
  }
  .tab-content { display: none; animation: fadeIn .35s ease; }
  .tab-content.active { display: block; }
  @keyframes fadeIn { from { opacity:0; transform:translateY(6px); } to { opacity:1; transform:translateY(0); } }

  .section-title {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--navy);
    margin-bottom: 1rem;
    padding-bottom: .5rem;
    border-bottom: 2px solid var(--accent);
    display: inline-block;
  }
  .card {
    background: var(--card);
    border-radius: 10px;
    padding: 1.5rem 1.8rem;
    margin-bottom: 1.5rem;
    box-shadow: 0 1px 3px rgba(0,0,0,.06);
    border: 1px solid var(--border);
  }
  .card h3 {
    font-size: 1.05rem;
    color: var(--navy);
    margin-bottom: .6rem;
  }
  .card ul, .card ol {
    padding-left: 1.3rem;
  }
  .card li {
    margin-bottom: .5rem;
    line-height: 1.65;
  }

  /* ── PUB SUBSECTIONS ── */
  .pub-section { margin-bottom: 1.8rem; }
  .pub-section h3 {
    font-size: 1rem;
    color: var(--accent);
    background: #fef9ee;
    display: inline-block;
    padding: .25rem .8rem;
    border-radius: 20px;
    font-weight: 600;
    margin-bottom: .8rem;
  }
  .pub-section ol { padding-left: 1.3rem; }

  /* timeline style for education */
  .timeline { border-left: 3px solid var(--accent); padding-left: 1.5rem; }
  .timeline-item {
    position: relative;
    margin-bottom: 1rem;
    padding: .5rem 0;
  }
  .timeline-item::before {
    content: '';
    position: absolute;
    left: -1.9rem;
    top: .7rem;
    width: 10px; height: 10px;
    background: var(--accent);
    border-radius: 50%;
  }
  .timeline-item .year {
    font-size: .82rem;
    color: var(--muted);
    font-weight: 500;
  }
  .student-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: .8rem;
  }
  .student-card {
    background: var(--card);
    border-radius: 8px;
    padding: .9rem 1rem;
    border: 1px solid var(--border);
    font-size: .92rem;
    transition: box-shadow .2s;
  }
  .student-card:hover { box-shadow: 0 2px 8px rgba(0,0,0,.08); }
  .student-card .name { font-weight: 600; color: var(--navy); }
  .student-card .topic { font-size: .82rem; color: var(--muted); margin-top: .2rem; }

  /* badges */
  .badge {
    display: inline-block;
    padding: .15rem .6rem;
    border-radius: 12px;
    font-size: .78rem;
    font-weight: 500;
    margin-left: .4rem;
  }
  .badge-phd { background: #e0e7ff; color: #3730a3; }
  .badge-ms { background: #d1fae5; color: #065f46; }
  .badge-meng { background: #fef3c7; color: #92400e; }

  .funding-card {
    background: linear-gradient(135deg, #f0f4ff, #fef9ee);
    border: 1px solid #dbeafe;
    border-radius: 10px;
    padding: 1.2rem 1.5rem;
    margin-top: 1rem;
  }

  .footer {
    text-align: center;
    padding: 2rem;
    color: var(--muted);
    font-size: .85rem;
    border-top: 1px solid var(--border);
    margin-top: 2rem;
  }
  .footer a { color: var(--link); }

  @media (max-width: 640px) {
    .header h1 { font-size: 1.6rem; }
    .tab-btn { padding: .7rem .9rem; font-size: .82rem; }
    .container { padding: 1.2rem .8rem 2rem; }
    .card { padding: 1rem 1.2rem; }
  }

  /* Publication counter badge */
  .pub-count {
    font-size: .78rem;
    color: var(--muted);
    font-weight: 400;
    margin-left: .3rem;
  }
</style>
</head>
<body>

<!-- ═══ HEADER ═══ -->
<header class="header">
  <h1>Xianlin Zeng</h1>
  <h2>Ph.D. &bull; Professor</h2>
  <div class="affil">
    National Key Laboratory of Autonomous Intelligent Unmanned Systems<br>
    School of Automation, Beijing Institute of Technology, 100081 Beijing, China<br>
    📧 xianlin.zeng@bit.edu.cn
  </div>
  <div class="links">
    <a href="https://xlinzeng.github.io/web/" target="_blank">📄 Publications</a>
    <a href="https://scholar.google.com/citations?user=S4KS0noAAAAJ&hl=en" target="_blank">🎓 Google Scholar</a>
  </div>
</header>

<!-- ═══ TAB NAV ═══ -->
<nav class="tab-nav" id="tabNav">
  <button class="tab-btn active" data-tab="about">About</button>
  <button class="tab-btn" data-tab="education">Education</button>
  <button class="tab-btn" data-tab="research">Research</button>
  <button class="tab-btn" data-tab="publications">Publications</button>
  <button class="tab-btn" data-tab="teaching">Teaching</button>
  <button class="tab-btn" data-tab="students">Students</button>
  <button class="tab-btn" data-tab="alumni">Alumni</button>
</nav>

<main class="container">

<!-- ═══ TAB: ABOUT ═══ -->
<section class="tab-content active" id="tab-about">
  <h2 class="section-title">About</h2>
  <div class="card">
    <p>I am a Professor at the <strong>School of Automation, Beijing Institute of Technology</strong>, affiliated with the National Key Laboratory of Autonomous Intelligent Unmanned Systems. My research interests span distributed optimization, noncooperative game theory, and task & motion planning of autonomous systems.</p>
    <p style="margin-top:.8rem">I received my Ph.D. in Mechanical Engineering from <strong>Texas Tech University</strong> (USA, 2015) and previously held postdoctoral positions at the Chinese Academy of Sciences and Beijing Institute of Technology.</p>
  </div>
  <div class="funding-card">
    <strong>🏛 Current Funding</strong>
    <p style="margin-top:.5rem">Distributed Optimization and Intelligent Decision-Making for Multi-Agent Cooperative Exploration in Complex Open Environments — <em>NSFC, 2026–2030, Co-PI</em></p>
  </div>
</section>

<!-- ═══ TAB: EDUCATION ═══ -->
<section class="tab-content" id="tab-education">
  <h2 class="section-title">Education & Career</h2>
  <div class="card">
    <div class="timeline">
      <div class="timeline-item">
        <span class="year">2017 – 2019</span>
        <p>Postdoc Researcher, School of Automation, <strong>Beijing Institute of Technology</strong></p>
      </div>
      <div class="timeline-item">
        <span class="year">2015 – 2017</span>
        <p>Postdoc Researcher, Academy of Mathematics and Systems Science, <strong>Chinese Academy of Sciences</strong></p>
      </div>
      <div class="timeline-item">
        <span class="year">2011 – 2015</span>
        <p>Ph.D. in Mechanical Engineering, <strong>Texas Tech University</strong>, Lubbock, USA</p>
      </div>
      <div class="timeline-item">
        <span class="year">2009 – 2011</span>
        <p>M.Sc. in Control Science and Engineering, <strong>Harbin Institute of Technology</strong></p>
      </div>
      <div class="timeline-item">
        <span class="year">2005 – 2009</span>
        <p>B.Sc. in Control Science and Engineering, <strong>Harbin Institute of Technology</strong></p>
      </div>
    </div>
  </div>
</section>

<!-- ═══ TAB: RESEARCH ═══ -->
<section class="tab-content" id="tab-research">
  <h2 class="section-title">Research Interests</h2>
  <div class="card">
    <h3>🔬 Optimizaiton, game theory, and AI for multi-agent systems</h3>
    <ul>
      <li>Distributed Optimization Algorithms  </li>
      <li>Game Theory and Equilibrium Seeking</li>
      <li>Solving Matrix Equations and Inequalities</li>
    </ul>
  </div>
  <div class="card">
    <h3>🤖 Application of these methods for unmanned systems</h3>
    <ul>
      <li>Motion planning of autonomous vehicles and robots</li>
      <li>Modeling and intelligent control of robotic systems</li>
      <li>AI planning for decision makeing problems under uncertainty</li>
    </ul>
  </div>
  <div class="card">
    <h3>📘 Textbooks & Monographs</h3>
    <ul>
      <li>Xianlin Zeng, Yiguang Hong, Hao Fang, Distributed Optimization and Control of Multi-agent System, Beijing Institute of Technology Press, 2023 (in Chinese);（曾宪琳，洪奕光，方浩，多智能体系统的分布式非光滑优化控制，北京理工大学出版社，2023）</li>
      <li>Hao Fang, Xianlin Zeng, Qingkai Yang, Jie Chen, Autonomous Intelligent Unmanned System, Tsinghua University Press, 2023 (in Chinese);（方浩，曾宪琳，杨庆凯，陈杰，自主智能无人系统，清华大学出版社，2025）</li>
    </ul>
  </div>
</section>

<!-- ═══ TAB: PUBLICATIONS ═══ -->
<section class="tab-content" id="tab-publications">
  <h2 class="section-title">Selected Publications</h2>

  <div class="pub-section">
    <h3>Distributed & Stochastic Optimization</h3>
    <ol>
      <li>Jie Hou, <strong>X. Zeng</strong>, S. Cui, J. Sun. Stochastic Frank-Wolfe Algorithm for Constrained Bilevel Optimization. <em>IEEE Trans. Signal Processing</em>, vol. 73, 2025.</li>
      <li>Jie Hou, <strong>X. Zeng</strong>, S. Cui, J. Sun. Distributed Stochastic Frank-Wolfe for Constrained Composite Minimization. <em>IEEE Trans. Automatic Control</em>, Dec 2025.</li>
      <li>Xia Jiang, <strong>X. Zeng</strong>, L. Xie, J. Sun, J. Chen. Variance-reduced Reshuffling Gradient Descent for Nonconvex Optimization. <em>Automatica</em>, 2024.</li>
      <li>Xia Jiang, <strong>X. Zeng</strong>, L. Xie, J. Sun, J. Chen. Distributed stochastic projection-free solver. <em>IEEE Trans. Automatic Control</em>, 2024.</li>
      <li>Jie Hou, <strong>X. Zeng</strong>, G. Wang, C. Chen, J. Sun. Distributed Frank-Wolfe Solver for Stochastic Optimization with Coupled Inequality Constraints. <em>IEEE Trans. Neural Networks and Learning Systems</em>, 2024.</li>
    </ol>
  </div>

  <div class="pub-section">
    <h3>Motion Planning & Control</h3>
    <ol>
      <li>X. Zhang, Q. Yang, <strong>X. Zeng</strong>, H. Fang, J. Chen. Cooperative Shape-Translation Estimation and Control. <em>IEEE Trans. Automatic Control</em>, 2025.</li>
      <li>Z. Cheng, <strong>X. Zeng</strong>, H. Fang, G. Wang, L. Dou. Hierarchical MPC-based Motion Planning. <em>Unmanned Systems</em>, 2023.</li>
      <li>C. Wu, H. Fang, <strong>X. Zeng</strong>, Q. Yang, Y. Wei, J. Chen. Distributed Continuous-Time Algorithm for Time-Varying Optimization. <em>IEEE Trans. Automatic Control</em>, vol. 68, 2023.</li>
      <li><strong>X. Zeng</strong>. Hybrid Networked Control for Cyber-Physical Network Systems. <em>Ph.D. Dissertation, Texas Tech University</em>, 2015.</li>
    </ol>
  </div>

  <div class="pub-section">
    <h3>Noncooperative Games</h3>
    <ol>
      <li>K. Zhu, <strong>X. Zeng</strong>. Almost Sure Convergence to Approximate Nash Equilibrium in Zero-Sum Extensive-Form Games. <em>IEEE ICCA</em>, 2024.</li>
      <li><strong>X. Zeng</strong>, L. Dou, J. Chen. Accelerated First-Order Continuous-Time Algorithm for Bilinear Saddle Point Problem. <em>IFAC World Congress</em>, 2020.</li>
      <li><strong>X. Zeng</strong>, J. Chen, S. Liang, Y. Hong. Generalized Nash equilibrium seeking for distributed nonsmooth multi-cluster game. <em>Automatica</em>, vol. 103, 2019.</li>
    </ol>
  </div>

  <div class="pub-section">
    <h3>Distributed Matrix Equations & Continuous-Time Optimization</h3>
    <ol>
      <li>X. Jiang, <strong>X. Zeng</strong>, J. Sun, J. Chen. Distributed algorithms for semi-definite programming. <em>IEEE Trans. Automatic Control</em>, vol. 68, 2023.</li>
      <li><strong>X. Zeng</strong>, J. Chen, Y. Hong. Distributed Optimization Design of Iterative Refinement for Algebraic Riccati Equations. <em>IEEE Trans. SMC: Systems</em>, 2022.</li>
      <li>W. Li, <strong>X. Zeng</strong>, L. Pavel. Primal-dual Accelerated Mirror-Descent Method for Constrained Bilinear Saddle-Point Problems. <em>IEEE Trans. Automatic Control</em>, Feb 2026.</li>
      <li><strong>X. Zeng</strong>, P. Yi, Y. Hong, L. Xie. Distributed continuous-time algorithms for nonsmooth extended monotropic optimization. <em>SIAM J. Control and Optimization</em>, 2018.</li>
    </ol>
  </div>

  <p style="margin-top:1.2rem">
    📄 <a href="https://xlinzeng.github.io/web/" style="color:var(--link)">Complete Publication List</a>
    &nbsp;&nbsp;|&nbsp;&nbsp;
    🎓 <a href="https://scholar.google.com/citations?user=S4KS0noAAAAJ&hl=en" style="color:var(--link)">Google Scholar</a>
  </p>
</section>

<!-- ═══ TAB: TEACHING ═══ -->
<section class="tab-content" id="tab-teaching">
  <h2 class="section-title">Teaching</h2>
  <div class="card">
    <table style="width:100%; border-collapse:collapse;">
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.6rem .8rem; color:var(--muted); font-size:.85rem; width:7rem;">2025–now</td>
        <td style="padding:.6rem .8rem">Intelligent Coordination of Multi-Robot Systems <span style="color:var(--muted)">(Undergrad)</span></td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.6rem .8rem; color:var(--muted); font-size:.85rem;">2025–now</td>
        <td style="padding:.6rem .8rem">Fundamentals of Autonomous Intelligent Systems <span style="color:var(--muted)">(Graduate)</span></td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.6rem .8rem; color:var(--muted); font-size:.85rem;">2023–now</td>
        <td style="padding:.6rem .8rem">Scientific Writing and Communication <span style="color:var(--muted)">(Undergrad)</span></td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.6rem .8rem; color:var(--muted); font-size:.85rem;">2023–now</td>
        <td style="padding:.6rem .8rem">Fundamentals of Swarm Intelligence and Adversarial Games <span style="color:var(--muted)">(Graduate)</span></td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.6rem .8rem; color:var(--muted); font-size:.85rem;">2021–2024</td>
        <td style="padding:.6rem .8rem">Fundamentals of Intelligent Control <span style="color:var(--muted)">(Undergrad)</span></td>
      </tr>
      <tr>
        <td style="padding:.6rem .8rem; color:var(--muted); font-size:.85rem;">2020–2022</td>
        <td style="padding:.6rem .8rem">Optimization Theory and Methods <span style="color:var(--muted)">(Graduate)</span></td>
      </tr>
    </table>
  </div>
</section>

<!-- ═══ TAB: STUDENTS ═══ -->
<section class="tab-content" id="tab-students">
  <h2 class="section-title">Current Graduate Students</h2>

  <h3 style="margin-bottom:.6rem; color:var(--navy);">Ph.D. Students <span class="badge badge-phd">8</span></h3>
  <div class="student-grid">
    <div class="student-card"><span class="name">Kui Zhu</span><br><span class="topic">Algorithms for noncooperative games</span></div>
    <div class="student-card"><span class="name">Zijun Cheng</span><br><span class="topic">Planning & control of autonomous robots</span></div>
    <div class="student-card"><span class="name">Azhushima</span><br><span class="topic">Distributed optimization for multiple robots</span></div>
    <div class="student-card"><span class="name">Yuman He</span><br><span class="topic">Algorithms for noncooperative games</span></div>
    <div class="student-card"><span class="name">Yuliang Wang</span><br><span class="topic">Task & path planning of robots</span></div>
    <div class="student-card"><span class="name">Yuhui Huang</span><br><span class="topic">TBA (2025–)</span></div>
    <div class="student-card"><span class="name">Xin Yu</span><br><span class="topic">TBA (2025–)</span></div>
    <div class="student-card"><span class="name">Qinglong Zhang</span><br><span class="topic">TBA (2025–)</span></div>
  </div>

  <h3 style="margin-top:1.5rem; margin-bottom:.6rem; color:var(--navy);">Master Students <span class="badge badge-ms">3</span> <span class="badge badge-meng">8</span></h3>
  <div class="student-grid">
    <div class="student-card"><span class="name">Luying Chen</span> <span class="badge badge-ms">M.Sc.</span><br><span class="topic">Game theory</span></div>
    <div class="student-card"><span class="name">Kairui Guo</span> <span class="badge badge-ms">M.Sc.</span><br><span class="topic">TBA</span></div>
    <div class="student-card"><span class="name">Chongyao Li</span> <span class="badge badge-meng">M.Eng.</span><br><span class="topic">Game theory</span></div>
    <div class="student-card"><span class="name">Jiarui Liang</span> <span class="badge badge-meng">M.Eng.</span><br><span class="topic">Motion planning of vehicles</span></div>
    <div class="student-card"><span class="name">Zhonghao Lin</span> <span class="badge badge-meng">M.Eng.</span><br><span class="topic">Time-varying optimization</span></div>
    <div class="student-card"><span class="name">Dongxiang Liu</span> <span class="badge badge-meng">M.Eng.</span><br><span class="topic">Motion planning of vehicles</span></div>
    <div class="student-card"><span class="name">Zelin Li</span> <span class="badge badge-meng">M.Eng.</span><br><span class="topic">Task planning of robots</span></div>
    <div class="student-card"><span class="name">Jiahui Chen</span> <span class="badge badge-meng">M.Eng.</span><br><span class="topic">Path planning of robots</span></div>
    <div class="student-card"><span class="name">Sunhan Zhou</span> <span class="badge badge-meng">M.Eng.</span><br><span class="topic">TBA</span></div>
    <div class="student-card"><span class="name">Ke Jia</span> <span class="badge badge-meng">M.Eng.</span><br><span class="topic">TBA</span></div>
    <div class="student-card"><span class="name">Tong Huang</span> <span class="badge badge-meng">M.Eng.</span><br><span class="topic">TBA</span></div>
  </div>
</section>

<!-- ═══ TAB: ALUMNI ═══ -->
<section class="tab-content" id="tab-alumni">
  <h2 class="section-title">Student Alumni</h2>
  <div class="card">
    <table style="width:100%; border-collapse:collapse;">
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem; width:7rem;">2019–2022</td>
        <td style="padding:.5rem .6rem"><strong>Jiebang Xing</strong> <span class="badge badge-ms">M.Sc.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Pursuit evasion games via DRL</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2019–2022</td>
        <td style="padding:.5rem .6rem"><strong>Junchao Zhang</strong> <span class="badge badge-meng">M.Eng.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Pursuing strategy via model-free RL</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2020–2023</td>
        <td style="padding:.5rem .6rem"><strong>Zijun Cheng</strong> <span class="badge badge-meng">M.Eng.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Optimization-based motion planning</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2020–2023</td>
        <td style="padding:.5rem .6rem"><strong>Kai Wang</strong> <span class="badge badge-meng">M.Eng.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Interpretable intention recognition & trajectory prediction</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2021–2024</td>
        <td style="padding:.5rem .6rem"><strong>Lan Wang</strong> <span class="badge badge-ms">M.Sc.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Interpretable vehicle intention prediction</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2021–2024</td>
        <td style="padding:.5rem .6rem"><strong>Yanyan Fang</strong> <span class="badge badge-meng">M.Eng.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Multimodal trajectory prediction for mixed traffic</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2020–2025</td>
        <td style="padding:.5rem .6rem"><strong>Jie Hou</strong> <span class="badge badge-phd">Ph.D.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Distributed projection-free stochastic optimization</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2022–2025</td>
        <td style="padding:.5rem .6rem"><strong>Yixuan Li</strong> <span class="badge badge-ms">M.Sc.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Cooperative pursuit via adversarial game theory</td>
      </tr>
      <tr>
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2022–2025</td>
        <td style="padding:.5rem .6rem"><strong>Xuanming Zhang</strong> <span class="badge badge-ms">M.Sc.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Multimodal trajectory prediction via behavioral game theory</td>
      </tr>
    </table>
  </div>
</section>

</main>

<footer class="footer">
  &copy; 2026 Xianlin Zeng &bull; Beijing Institute of Technology
</footer>

<script>
  const btns = document.querySelectorAll('.tab-btn');
  const contents = document.querySelectorAll('.tab-content');

  btns.forEach(btn => {
    btn.addEventListener('click', () => {
      const target = btn.dataset.tab;
      btns.forEach(b => b.classList.remove('active'));
      contents.forEach(c => c.classList.remove('active'));
      btn.classList.add('active');
      document.getElementById('tab-' + target).classList.add('active');
    });
  });

  // URL hash support
  function activateFromHash() {
    const hash = window.location.hash.replace('#','');
    if (hash) {
      const btn = document.querySelector(`[data-tab="${hash}"]`);
      if (btn) btn.click();
    }
  }
  window.addEventListener('hashchange', activateFromHash);
  activateFromHash();
</script>

</body>
</html>
