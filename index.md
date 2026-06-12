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
  .pub-section li {
    margin-bottom: .6rem;
    line-height: 1.65;
  }

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

  .awards-list {
    list-style: none;
    padding: 0;
  }
  .awards-list li {
    padding: .5rem 0;
    border-bottom: 1px solid var(--border);
    font-size: .92rem;
  }
  .awards-list li:last-child { border-bottom: none; }
  .awards-list .award-year {
    display: inline-block;
    width: 4.5rem;
    color: var(--muted);
    font-size: .82rem;
    font-weight: 500;
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
  <h1>Xianlin Zeng (曾宪琳)</h1>
  <h2>Ph.D. &bull; Professor</h2>
  <div class="affil">
    National Key Laboratory of Autonomous Intelligent Unmanned Systems<br>
    School of Automation, Beijing Institute of Technology, 100081 Beijing, China<br>
    📧 xianlin.zeng@bit.edu.cn
  </div>
  <div class="links">
    <a href="https://scholar.google.com/citations?user=S4KS0noAAAAJ&hl=en" target="_blank">🎓 Google Scholar</a>
    <a href="https://xlinzeng.github.io/web/" target="_blank">📄 Full Publication List</a>
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
    <p>I am a Professor at the <strong>School of Automation, Beijing Institute of Technology</strong>, affiliated with the National Key Laboratory of Autonomous Intelligent Unmanned Systems. My research interests span <strong>distributed optimization</strong>, <strong>noncooperative game theory</strong>, and <strong>intelligent planning &amp; decision-making for autonomous unmanned systems</strong>.</p>
    <p style="margin-top:.8rem">I received my Ph.D. in Mechanical Engineering from <strong>Texas Tech University</strong> (USA, 2015) and previously held postdoctoral positions at the Chinese Academy of Sciences and Beijing Institute of Technology.</p>
  </div>


  <div class="funding-card">
    <strong>🏛 Current Funding</strong>
    <ul style="margin-top:.5rem; padding-left:1.2rem; font-size:.92rem;">
      <li>NSFC Key International Cooperation Project — Distributed Optimization and Intelligent Decision-Making for Multi-Agent Cooperative Exploration in Complex Open Environments (2026–2030, Co-PI)</li>
    </ul>
  </div>
</section>

<!-- ═══ TAB: EDUCATION ═══ -->
<section class="tab-content" id="tab-education">
  <h2 class="section-title">Education &amp; Career</h2>
  <div class="card">
    <div class="timeline">
      <div class="timeline-item">
        <span class="year">2019 – present</span>
        <p>Associate Professor → Professor, School of Automation, <strong>Beijing Institute of Technology</strong></p>
      </div>
      <div class="timeline-item">
        <span class="year">2017 – 2019</span>
        <p>Postdoctoral Researcher, School of Automation, <strong>Beijing Institute of Technology</strong></p>
      </div>
      <div class="timeline-item">
        <span class="year">2015 – 2017</span>
        <p>Postdoctoral Researcher, Academy of Mathematics and Systems Science, <strong>Chinese Academy of Sciences</strong></p>
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
    <h3>🔬 Distributed Optimization &amp; Computation</h3>
    <ul>
      <li>Distributed stochastic optimization (projection-free, variance-reduced, zeroth-order methods)</li>
      <li>Distributed nonsmooth and nonconvex optimization over networks</li>
      <li>Continuous-time dynamical optimization algorithms with convergence rate analysis</li>
      <li>Distributed solutions to matrix equations (Lyapunov, Riccati, SDP)</li>
      <li>Time-varying and online optimization with prediction-correction strategies</li>
    </ul>
  </div>
  <div class="card">
    <h3>🎯 Game Theory &amp; Multi-Agent Decision Making</h3>
    <ul>
      <li>Generalized Nash equilibrium seeking in nonsmooth multi-cluster games</li>
      <li>Algorithms for extensive-form games and adversarial decision-making</li>
      <li>Saddle-point problems and primal-dual accelerated methods</li>
      <li>Pursuit-evasion games and cooperative strategies</li>
    </ul>
  </div>
  <div class="card">
    <h3>🤖 Intelligent Planning &amp; Control for Unmanned Systems</h3>
    <ul>
      <li>Motion planning for autonomous vehicles (MPC-based, optimization-based)</li>
      <li>Multi-robot cooperative task &amp; path planning</li>
      <li>AI planning for decision-making under uncertainty and adversarial environments</li>
      <li>Cooperative shape estimation and formation control</li>
    </ul>
  </div>
  <div class="card">
    <h3>📘 Textbooks &amp; Monographs</h3>
    <ul>
      <li><strong>X. Zeng</strong>, Y. Hong, H. Fang. <em>Distributed Nonsmooth Optimization and Control of Multi-Agent Systems</em> (多智能体系统的分布式非光滑优化控制). Beijing Institute of Technology Press, 2023. [National "14th Five-Year" Key Publication Project]</li>
      <li>H. Fang, <strong>X. Zeng</strong>, Q. Yang, J. Chen. <em>Autonomous Intelligent Unmanned Systems</em> (自主智能无人系统). Tsinghua University Press, 2024. [National "14th Five-Year" Planning Textbook]</li>
      <li>H. Fang, Q. Yang, <strong>X. Zeng</strong>, J. Chen. <em>Collaborative Control and Optimization of Autonomous Unmanned Systems</em> (自主无人系统协同控制与优化). Science Press. [National "14th Five-Year" Key Publication Project]</li>
    </ul>
  </div>
</section>

<!-- ═══ TAB: PUBLICATIONS ═══ -->
<section class="tab-content" id="tab-publications">
  <h2 class="section-title">Selected Publications</h2>
  <p style="margin-bottom:1.5rem; color:var(--muted); font-size:.9rem;">A curated selection organized by research theme. For the complete list, see <a href="https://xlinzeng.github.io/web/" style="color:var(--link)">full publication page</a> or <a href="https://scholar.google.com/citations?user=S4KS0noAAAAJ&hl=en" style="color:var(--link)">Google Scholar</a>.</p>

  <!-- ── Category 1: Distributed Stochastic & Projection-Free Optimization ── -->
  <div class="pub-section">
    <h3>Distributed Stochastic &amp; Projection-Free Optimization</h3>
    <ol>
      <li>J. Hou, <strong>X. Zeng*</strong>, S. Cui, X. Jiang, J. Sun. "Stochastic Frank-Wolfe Algorithm for Constrained Bilevel Optimization with Improved Per-Iteration Complexity." <em>IEEE Trans. Signal Processing</em>, vol. 73, pp. 3237–3252, 2025.</li>
      <li>J. Hou, <strong>X. Zeng*</strong>, S. Cui, J. Sun. "Distributed Stochastic Frank-Wolfe for Constrained Composite Minimization." <em>IEEE Trans. Automatic Control</em>, DOI: 10.1109/TAC.2025.3581321, 2025.</li>
      <li>X. Jiang, <strong>X. Zeng*</strong>, L. Xie, J. Sun, J. Chen. "Distributed Stochastic Projection-Free Algorithm for Constrained Optimization." <em>IEEE Trans. Automatic Control</em>, vol. 70, no. 4, Apr. 2025.</li>
      <li>X. Jiang, <strong>X. Zeng*</strong>, L. Xie, J. Sun, J. Chen. "Variance-Reduced Reshuffling Gradient Descent for Non-Convex Optimization: Centralized and Distributed Algorithms." <em>Automatica</em>, vol. 171, Jan. 2025.</li>
      <li>Y. Huang, <strong>X. Zeng*</strong>, J. Sun, Z. Meng. "Distributed Event-Triggered Algorithm for Convex Optimization with Coupled Constraints." <em>Automatica</em>, vol. 170, Dec. 2024.</li>
      <li>J. Hou, <strong>X. Zeng*</strong>, G. Wang, C. Chen, J. Sun. "Distributed Frank-Wolfe Solver for Stochastic Optimization with Coupled Inequality Constraints." <em>IEEE Trans. Neural Networks and Learning Systems</em>, vol. 36, no. 5, May 2025.</li>
      <li>X. Jiang, <strong>X. Zeng*</strong>, J. Sun, J. Chen. "Distributed Stochastic Gradient Tracking Algorithm with Variance Reduction for Non-Convex Optimization." <em>IEEE Trans. Neural Networks and Learning Systems</em>, DOI: 10.1109/TNNLS.2022.3170944, 2023.</li>
      <li>J. Hou, <strong>X. Zeng*</strong>, G. Wang, J. Sun, J. Chen. "Distributed Momentum-Based Frank-Wolfe Algorithm for Stochastic Optimization." <em>IEEE/CAA Journal of Automatica Sinica</em>, DOI: 10.1109/JAS.2022.105923, 2023.</li>
    </ol>
  </div>

  <!-- ── Category 2: Continuous-Time & Accelerated Optimization ── -->
  <div class="pub-section">
    <h3>Continuous-Time &amp; Accelerated Distributed Optimization</h3>
    <ol>
      <li>W. Li, <strong>X. Zeng</strong>, L. Pavel. "Primal-Dual Accelerated Mirror-Descent Method for Constrained Bilinear Saddle-Point Problems." <em>IEEE Trans. Automatic Control</em>, Feb. 2026.</li>
      <li><strong>X. Zeng</strong>, J. Lei, J. Chen. "Dynamical Primal-Dual Accelerated Method with Applications to Network Optimization." <em>IEEE Trans. Automatic Control</em>, vol. 68, no. 3, Mar. 2023.</li>
      <li>C. Wu, H. Fang, <strong>X. Zeng</strong>, Q. Yang, Y. Wei, J. Chen. "Distributed Continuous-Time Algorithm for Time-Varying Optimization with Affine Formation Constraints." <em>IEEE Trans. Automatic Control</em>, vol. 68, no. 4, 2023.</li>
      <li><strong>X. Zeng</strong>, P. Yi, Y. Hong, L. Xie. "Distributed Continuous-Time Algorithms for Nonsmooth Extended Monotropic Optimization." <em>SIAM Journal on Control and Optimization</em>, vol. 56, no. 6, pp. 3973–3993, 2018.</li>
      <li>X. Jiang, <strong>X. Zeng*</strong>, J. Sun, J. Chen. "A Fully Distributed Hybrid Control Framework for Non-Differentiable Multi-Agent Optimization." <em>IEEE/CAA Journal of Automatica Sinica</em>, 2022.</li>
    </ol>
  </div>

  <!-- ── Category 3: Nonsmooth, Nonconvex & Zeroth-Order ── -->
  <div class="pub-section">
    <h3>Nonsmooth, Nonconvex &amp; Zeroth-Order Optimization</h3>
    <ol>
      <li>J. Hou, X. Jiang, <strong>X. Zeng*</strong>, L. Zhao, J. Sun. "Distributed Nonsmooth Nonconvex Optimization: Deterministic and Stochastic Zeroth-Order Algorithms with Decaying Step Sizes." <em>IEEE Trans. Signal and Information Processing over Networks</em>, vol. 12, pp. 585–598, 2026.</li>
      <li>X. Jiang, Y. Fang, <strong>X. Zeng*</strong>, J. Sun, J. Chen. "Inexact Proximal Gradient Algorithm with Random Reshuffling for Nonsmooth Optimization." <em>Science China Information Sciences</em>, vol. 68, 112201, 2025.</li>
      <li>Y. Wang, <strong>X. Zeng*</strong>, W. Zhao, Y. Hong. "A Zeroth-Order Algorithm for Distributed Optimization with Stochastic Stripe Observations." <em>Science China Information Sciences</em>, vol. 66, 199202, 2023.</li>
    </ol>
  </div>

  <!-- ── Category 4: Time-Varying Optimization ── -->
  <div class="pub-section">
    <h3>Time-Varying &amp; Online Optimization</h3>
    <ol>
      <li>Z. Lin, J. Hou*, <strong>X. Zeng</strong>. "Optimal Prediction-Correction Algorithm Using Sparse Linear Extrapolation for Time-Varying Optimization." <em>IEEE Trans. Signal Processing</em>, accepted, 2026.</li>
      <li>Z. Lin, <strong>X. Zeng</strong>, J. Hou*, J. Sun, J. Chen. "Primal-Dual Prediction-Correction Method with Tunable Memory for Linearly Constrained Time-Varying Convex Optimization." <em>Journal of Systems Science and Complexity</em>, vol. 39, no. 2, pp. 483–510, 2026.</li>
    </ol>
  </div>

  <!-- ── Category 5: Distributed Matrix Equations ── -->
  <div class="pub-section">
    <h3>Distributed Matrix Equations &amp; Networked Computation</h3>
    <ol>
      <li>X. Jiang, <strong>X. Zeng*</strong>, J. Sun, J. Chen. "Distributed Algorithms for Semi-Definite Programming Problems over Unbalanced Digraphs." <em>IEEE Trans. Automatic Control</em>, vol. 68, no. 12, 2023.</li>
      <li>Y. Huang, <strong>X. Zeng*</strong>, Z. Meng, D. Meng. "Distributed Algorithms of Solving Linear Matrix Equations via Double-Layered Networks." <em>Automatica</em>, vol. 165, 111662, 2024.</li>
      <li><strong>X. Zeng</strong>, J. Chen, Y. Hong. "Distributed Optimization Design of Iterative Refinement Technique for Algebraic Riccati Equations." <em>IEEE Trans. Systems, Man, and Cybernetics: Systems</em>, DOI: 10.1109/TSMC.2021.3056871, 2022.</li>
      <li><strong>X. Zeng</strong>, J. Chen, J. Sun, Y. Hong. "Distributed Optimization Approach for Solving Continuous-Time Lyapunov Equations with Exponential Rate of Convergence." <em>IEEE Trans. Systems, Man, and Cybernetics: Systems</em>, vol. 52, no. 3, pp. 1684–1691, 2022.</li>
      <li><strong>X. Zeng</strong>, J. Chen, Y. Hong. "Distributed Optimization Design for Computation of Algebraic Riccati Inequalities." <em>IEEE Trans. Cybernetics</em>, vol. 52, no. 3, pp. 1924–1935, 2022.</li>
    </ol>
  </div>

  <!-- ── Category 6: Game Theory ── -->
  <div class="pub-section">
    <h3>Game Theory &amp; Multi-Agent Decision Making</h3>
    <ol>
      <li>X. Zhang, <strong>X. Zeng*</strong>, Q. Yang, H. Fang, L. Xie, J. Chen. "Distributed Nominal Configuration Design for Linear Formations." <em>IEEE Trans. Automatic Control</em>, DOI: 10.1109/TAC.2026.3689360, 2026.</li>
      <li><strong>X. Zeng</strong>, J. Chen, S. Liang, Y. Hong. "Generalized Nash Equilibrium Seeking Strategy for Distributed Nonsmooth Multi-Cluster Game." <em>Automatica</em>, vol. 103, pp. 20–26, 2019.</li>
      <li><strong>X. Zeng</strong>, L. Dou, J. Chen. "Accelerated First-Order Continuous-Time Algorithm for Solving Bilinear Saddle Point Problems." <em>IFAC World Congress</em>, 2020.</li>
      <li><strong>X. Zeng</strong>, L. Dou, J. Cui. "Distributed Accelerated Nash Equilibrium Learning for Two-Subnetwork Zero-Sum Game with Bilinear Coupling." <em>Kybernetika</em>, 2023.</li>
      <li>K. Zhu, <strong>X. Zeng*</strong>. "Almost Sure Convergence to Approximate Nash Equilibrium in Zero-Sum Extensive-Form Games." <em>IEEE ICCA</em>, 2024.</li>
    </ol>
  </div>

  <!-- ── Category 7: Motion Planning & Control ── -->
  <div class="pub-section">
    <h3>Motion Planning &amp; Autonomous Systems</h3>
    <ol>
      <li>X. Zhang, Q. Yang, <strong>X. Zeng</strong>, H. Fang, J. Chen. "Cooperative Shape-Translation Estimation and Control for Multi-Robot Systems." <em>IEEE Trans. Automatic Control</em>, 2025.</li>
      <li>Z. Cheng, <strong>X. Zeng*</strong>, H. Fang, G. Wang, L. Dou. "Hierarchical MPC-based Motion Planning for Autonomous Driving in Unstructured Environments." <em>Unmanned Systems</em>, 2023. <span style="color:var(--accent); font-size:.8rem; font-weight:500;">(Best Paper Award 2026)</span></li>
      <li><strong>X. Zeng</strong>. "Hybrid Networked Control for Cyber-Physical Network Systems." <em>Ph.D. Dissertation, Texas Tech University</em>, 2015.</li>
    </ol>
  </div>

  <!-- ── Category 8: Survey ── -->
  <div class="pub-section">
    <h3>Survey</h3>
    <ol>
      <li>X. Jiang, <strong>X. Zeng</strong>, J. Sun*, J. Chen. "Distributed Optimization for Multi-Agent Systems: A Survey and Perspectives" (多智能体系统分布式优化综述与前瞻). <em>Science China Information Sciences</em> (中国科学：信息科学), 2025.</li>
    </ol>
  </div>

  <p style="margin-top:1.2rem; padding-top:1rem; border-top:1px solid var(--border);">
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
        <td style="padding:.6rem .8rem">Fundamentals of Swarm Intelligence and Adversarial Games <span style="color:var(--muted)">(Graduate)</span> <span style="font-size:.78rem; color:var(--accent); font-weight:500;">— AI-Empowered Course</span></td>
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
    <div class="student-card"><span class="name">Zijun Cheng</span><br><span class="topic">Planning &amp; control of autonomous robots</span></div>
    <div class="student-card"><span class="name">Azhushima</span><br><span class="topic">Distributed optimization for multiple robots</span></div>
    <div class="student-card"><span class="name">Yuman He</span><br><span class="topic">Algorithms for noncooperative games</span></div>
    <div class="student-card"><span class="name">Yuliang Wang</span><br><span class="topic">Task &amp; path planning of robots</span></div>
    <div class="student-card"><span class="name">Yuhui Huang</span><br><span class="topic">TBA (2025–)</span></div>
    <div class="student-card"><span class="name">Xin Yu</span><br><span class="topic">TBA (2025–)</span></div>
    <div class="student-card"><span class="name">Qinglong Zhang</span><br><span class="topic">TBA (2025–)</span></div>
  </div>

  <h3 style="margin-top:1.5rem; margin-bottom:.6rem; color:var(--navy);">Master Students <span class="badge badge-ms">M.Sc. 2</span> <span class="badge badge-meng">M.Eng. 9</span></h3>
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
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem; width:7rem;">2020–2025</td>
        <td style="padding:.5rem .6rem"><strong>Jie Hou</strong> <span class="badge badge-phd">Ph.D.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Distributed projection-free stochastic optimization</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2022–2025</td>
        <td style="padding:.5rem .6rem"><strong>Yixuan Li</strong> <span class="badge badge-ms">M.Sc.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Cooperative pursuit via adversarial game theory</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2022–2025</td>
        <td style="padding:.5rem .6rem"><strong>Xuanming Zhang</strong> <span class="badge badge-ms">M.Sc.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Motion planning via behavioral game theory</td>
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
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2020–2023</td>
        <td style="padding:.5rem .6rem"><strong>Zijun Cheng</strong> <span class="badge badge-meng">M.Eng.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Optimization-based motion planning</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2020–2023</td>
        <td style="padding:.5rem .6rem"><strong>Kai Wang</strong> <span class="badge badge-meng">M.Eng.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Interpretable intention recognition &amp; trajectory prediction</td>
      </tr>
      <tr style="border-bottom:1px solid var(--border)">
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2019–2022</td>
        <td style="padding:.5rem .6rem"><strong>Jiebang Xing</strong> <span class="badge badge-ms">M.Sc.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Pursuit-evasion games via deep RL</td>
      </tr>
      <tr>
        <td style="padding:.5rem .6rem; color:var(--muted); font-size:.82rem;">2019–2022</td>
        <td style="padding:.5rem .6rem"><strong>Junchao Zhang</strong> <span class="badge badge-meng">M.Eng.</span></td>
        <td style="padding:.5rem .6rem; font-size:.85rem">Pursuit strategy via model-free RL</td>
      </tr>
    </table>
  </div>
</section>

</main>

<footer class="footer">
  &copy; 2026 Xianlin Zeng &bull; Beijing Institute of Technology &bull; Last updated: June 2026
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
      history.replaceState(null, '', '#' + target);
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
