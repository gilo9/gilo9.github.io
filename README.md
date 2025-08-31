
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Giles Mwa — Portfolio</title>
  <meta name="description" content="Portfolio of Giles Mwa: blockchain, AI/ML, mobile, and backend development projects." />
  <meta name="author" content="Giles Mwa" />
  <meta name="color-scheme" content="light dark" />
  <style>
    /* --------- Reset & Base --------- */
    *, *::before, *::after {
      box-sizing: border-box;
    }
    html {
      scroll-behavior: smooth;
    }
    body {
      margin: 0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, sans-serif;
      line-height: 1.6;
      background: radial-gradient(1200px 600px at 80% -10%, var(--brand-weak), transparent 40%), var(--bg);
      color: var(--text);
    }
    a {
      color: var(--brand);
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }
    /* --------- Theme Variables --------- */
    :root {
      --bg: #ffffff;
      --text: #111827; /* slate-900 */
      --muted: #4b5563; /* gray-600 */
      --card: #f8fafc; /* slate-50 */
      --border: #e5e7eb; /* gray-200 */
      --brand: #2563eb; /* blue-600 */
      --brand-weak: #dbeafe; /* blue-100 */
    }
    @media (prefers-color-scheme: dark) {
      :root {
        --bg: #0b1020;
        --text: #e5e7eb;
        --muted: #94a3b8;
        --card: #0f172a;
        --border: #1f2937;
        --brand: #60a5fa;
        --brand-weak: #0b294f;
      }
    }
      :root.theme-light {
      --bg: #ffffff;
      --text: #111827;
      --muted: #4b5563;
      --card: #f8fafc;
      --border: #e5e7eb;
      --brand: #2563eb;
      --brand-weak: #dbeafe;
    }
      :root.theme-dark {
      --bg: #0b1020;
      --text: #e5e7eb;
      --muted: #94a3b8;
      --card: #0f172a;
      --border: #1f2937;
      --brand: #60a5fa;
      --brand-weak: #0b294f;
    }
    /* --------- Layout --------- */
    .container {
      width: min(1100px, 92%);
      margin: 0 auto;
    }
    header {
      position: sticky;
      top: 0;
      backdrop-filter: saturate(180%) blur(6px);
      background: color-mix(in hsl, var(--bg) 75%, transparent);
      border-bottom: 1px solid var(--border);
      z-index: 50;
    }
    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0.8rem 0;
    }
    .nav a.brand {
      font-weight: 700;
      letter-spacing: 0.2px;
    }
    .nav ul {
      list-style: none;
      display: flex;
      gap: 1rem;
      margin: 0;
      padding: 0;
    }
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.6rem 0.9rem;
      border: 1px solid var(--border);
      border-radius: 999px;
      background: var(--card);
      color: var(--text);
      text-decoration: none;
      font-weight: 600;
    }
    .btn:hover {
      box-shadow: 0 2px 12px color-mix(in srgb, var(--brand) 15%, transparent);
      text-decoration: none;
    }
    /* --------- Hero Section --------- */
    .hero {
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      gap: 2rem;
      align-items: center;
      padding: 3.5rem 0 2rem;
    }
    .hero h1 {
      font-size: clamp(1.8rem, 2.6vw + 1rem, 3rem);
      line-height: 1.2;
      margin: 0 0 0.5rem;
    }
    .hero p.lead {
      color: var(--muted);
      font-size: 1.05rem;
    }
    .chip {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.35rem 0.6rem;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 999px;
      font-size: 0.88rem;
    }
    .chip + .chip {
      margin-left: 0.5rem;
    }
    /* --------- Sections --------- */
    section {
      padding: 2.5rem 0;
    }
    section h2 {
      font-size: 1.6rem;
      margin: 0 0 1rem;
    }
    .grid {
      display: grid;
      gap: 1rem;
    }
    .grid-3 {
      grid-template-columns: repeat(3, minmax(0, 1fr));
    }
    .grid-2 {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
    /* --------- Responsive --------- */
    @media (max-width: 900px) {
      .hero {
        grid-template-columns: 1fr;
      }
      .grid-3 {
        grid-template-columns: 1fr;
      }
      .grid-2 {
        grid-template-columns: 1fr;
      }
    }
  </style>
  <script>
    function toggleTheme(){
      var element = document.body;
      element.classList.toggle("root.theme-light");
    }
  </script>
</head>
<body>
  <header>
    <div class="container nav">
      <a class="brand" href="#home">Giles Mwa</a>
      <nav aria-label="Primary">
        <ul>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#skills">Skills</a></li>
          <li><a href="#experience">Experience</a></li>
          <li><a href="#education">Education</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><button id="themeToggle" class="btn" type="button" onclick="toggleTheme()" >🌓 Theme</button></li>
        </ul>
      </nav>
    </div>
  </header>

  <main id="home" class="container">
    <!-- Hero Section -->
    <section class="hero">
      <div>
        <h1>Hi, I’m Giles Mwa 👋</h1>
        <p class="lead">
          Computer Science graduate with strong hands-on experience in <strong>blockchain</strong>, <strong>secure systems</strong>, and <strong>software development</strong>. I’m passionate about solving real-world problems through secure, scalable, and user-centric tech solutions.
        </p>
        <div style="margin: 1rem 0 1.2rem ;">
          <span class="chip">📍 London, UK</span>
          <span class="chip">🎯 Tech Consulting Track</span>
          <span class="chip">🔒 Security-first mindset</span>
        </div>
        <div style="display: flex; gap: 0.8rem; flex-wrap: wrap;">
          <a class="btn" href="#projects">View Projects</a>
          <a class="btn" href="./Giles-Mwa-CV.pdf" download>⬇️ Download CV</a>
          <a class="btn" href="https://github.com/gilo9" target="_blank" rel="noopener">GitHub</a>
          <a class="btn" href="https://www.linkedin.com/in/giles-mwa-411910243/" target="_blank" rel="noopener">LinkedIn</a>
        </div>
      </div>
    </section>

    <!-- Projects -->
  <section id="projects">
      <h2>Key Projects</h2>
      <div class="grid grid-3">
        <article class="card project" data-tags="blockchain security frontend">
          <h3>Secure File Sharing Dapp</h3>
          <p>Built a decentralized file-sharing platform using Ethereum smart contracts (<strong>Solidity</strong>, <strong>Hardhat</strong>) and <strong>IPFS</strong>. Token-based access control with a React frontend and Node.js backend.</p>
          <div class="tags">
            <span class="chip">Solidity</span><span class="chip">IPFS</span><span class="chip">React</span><span class="chip">Node.js</span>
          </div>
          <p><a href="https://github.com/gilesmwa/secure-file-sharing" target="_blank">Repo</a></p>
        </article>
        <article class="card project" data-tags="ai ml chatbot">
          <h3>AI Chatbot with Image Classifier</h3>
          <p>Developed a football chatbot identifying club logos and player faces using CNNs in Python. Integrated into a web interface with a custom-trained dataset.</p>
          <div class="tags">
            <span class="chip">Python</span><span class="chip">PyTorch</span><span class="chip">OpenCV</span>
          </div>
        </article>
        <article class="card project" data-tags="mobile flutter security">
          <h3>Authentication App</h3>
          <p>Flutter-based app for secure hardware access with time-based tokens, real-time expiry logic, and Firebase integration.</p>
          <div class="tags"><span class="chip">Flutter</span><span class="chip">Dart</span><span class="chip">Firebase</span></div>
        </article>
      </div>
    </section>

    <!-- Skills -->
  <section id="skills">
      <h2>Skills</h2>
      <div class="grid grid-3">
        <div class="card"><h3>Languages</h3><ul class="list"><li>Python, Java, JavaScript, C++, Dart, Solidity</li></ul></div>
        <div class="card"><h3>Frameworks/Tools</h3><ul class="list"><li>React, Flutter, Node.js, Hardhat, MongoDB, Docker</li></ul></div>
        <div class="card"><h3>Concepts</h3><ul class="list"><li>Blockchain, Smart Contracts, Web3, REST APIs, OOP, DSA</li></ul></div>
      </div>
    </section>

    <!-- Experience -->
  <section id="experience">
      <h2>Experience</h2>
      <div class="grid grid-2">
        <div class="card">
          <h3>Retail Team Leader — Nottingham Forest FC</h3>
          <p>Supervised match-day staff, optimized payment flows, and consistently surpassed sales targets.</p>
        </div>
        <div class="card">
          <h3>Catering & Events Staff — Constellation</h3>
          <p>Delivered high-standard service at major stadiums, trained junior staff, and ensured compliance.</p>
        </div>
        <div class="card">
          <h3>Engineering Intern — SPIE UK</h3>
          <p>Debugged building maintenance algorithms and contributed to software development teams.</p>
        </div>
      </div>
    </section>

    <!-- Education -->
  <section id="education">
      <h2>Education </h2>
      <div class="card">
        <p><strong>BSc (Hons) Computer Science</strong>, Nottingham Trent University — 2:2 Honours (2024–2025)</p>
        <p><strong>Diploma of Higher Education</strong>, University of Leicester (2021–2024)</p>
      </div>
  </section>

    <!-- Contact -->
  <section id="contact">
      <h2>Contact</h2>
      <div class="grid grid-2">
        <div class="card">
          <p>Email: <a href="mailto:gilesmwa@gmail.com">gilesmwa@gmail.com</a></p>
          <p>GitHub: <a href="https://github.com/gilo9">@gilo9</a></p>
          <p>LinkedIn: <a href="https://www.linkedin.com/in/giles-mwa-411910243">/in/gilesmwa</a></p>
        </div>
      </div>
    </section>
  </main>
</body>
</html>
