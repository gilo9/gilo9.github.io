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
    *, *::before, *::after { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, sans-serif;
      line-height: 1.7;
      background: var(--bg);
      color: var(--text);
    }
    a { color: var(--brand); text-decoration: none; }
    a:hover { text-decoration: underline; }
    /* --------- Theme Variables --------- */
    :root {
      --bg: #f6f8fa;
      --text: #222;
      --muted: #6b7280;
      --card: #fff;
      --border: #e5e7eb;
      --brand: #2563eb;
      --brand-weak: #dbeafe;
      --shadow: 0 2px 16px rgba(60,80,120,0.08);
    }
    @media (prefers-color-scheme: dark) {
      :root {
        --bg: #101624;
        --text: #e5e7eb;
        --muted: #94a3b8;
        --card: #18223a;
        --border: #1f2937;
        --brand: #60a5fa;
        --brand-weak: #0b294f;
        --shadow: 0 2px 16px rgba(60,80,120,0.18);
      }
    }
    /* --------- Layout --------- */
    .container { width: min(1000px, 94%); margin: 0 auto; }
    header {
      position: sticky; top: 0;
      background: var(--card);
      border-bottom: 1px solid var(--border);
      box-shadow: var(--shadow);
      z-index: 50;
    }
    .nav {
      display: flex; align-items: center; justify-content: space-between;
      padding: 1rem 0;
    }
    .nav a.brand { font-weight: 700; font-size: 1.2rem; letter-spacing: 0.2px; }
    .nav ul {
      list-style: none; display: flex; gap: 1.2rem; margin: 0; padding: 0;
    }
    .nav ul li { margin: 0; }
    .btn {
      display: inline-flex; align-items: center; gap: 0.5rem;
      padding: 0.6rem 1.1rem;
      border: 1px solid var(--border);
      border-radius: 999px;
      background: var(--card);
      color: var(--text);
      font-weight: 600;
      box-shadow: var(--shadow);
      transition: box-shadow 0.2s;
    }
    .btn:hover { box-shadow: 0 4px 24px color-mix(in srgb, var(--brand) 15%, transparent); }
    /* --------- Hero Section --------- */
    .hero {
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      gap: 2rem;
      align-items: center;
      padding: 3rem 0 2rem;
      max-width: 1200px;
      margin: 0 auto;
    }
    .hero h1 { font-size: clamp(2rem, 2.6vw + 1rem, 3rem); margin: 0 0 0.7rem; }
    .hero p.lead { color: var(--muted); font-size: 1.08rem; }
    .chip {
      display: inline-flex; align-items: center; gap: 0.5rem;
      padding: 0.35rem 0.7rem;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 999px;
      font-size: 0.95rem;
      margin-right: 0.5rem;
      box-shadow: var(--shadow);
    }
    /* --------- Sections --------- */
    section { padding: 2.5rem 0; }
    section h2 { font-size: 1.5rem; margin: 0 0 1.2rem; }
    .grid { display: grid; gap: 1.2rem; }
    .grid-3 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
    .grid-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
    .card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 1rem;
      box-shadow: var(--shadow);
      padding: 1.2rem 1rem;
      margin-bottom: 0.5rem;
      transition: box-shadow 0.2s;
    }
    .card:hover { box-shadow: 0 6px 32px color-mix(in srgb, var(--brand) 10%, transparent); }
    .tags { margin-top: 0.7rem; }
    .project h3 { margin-bottom: 0.3rem; }
    .project .btn { margin-top: 0.7rem; }
    /* --------- Modal --------- */
    .modal {
      display: none;
      position: fixed;
      z-index: 1000;
      left: 0; top: 0;
      width: 100vw; height: 100vh;
      background: rgba(0,0,0,0.35);
      align-items: center; justify-content: center;
      overflow: auto; /* Enable scrolling for modal background */
    }
    .modal.active { display: flex; }
    .modal-content {
      background: var(--card); color: var(--text);
      border-radius: 1rem; box-shadow: var(--shadow);
      padding: 2rem;
      max-width: 95vw; /* Fit modal to screen width */
      max-height: 90vh; /* Fit modal to screen height */
      width: 100%;
      overflow-y: auto; /* Enable scrolling for modal content */
      position: relative;
    }
    .modal-close {
      position: absolute; top: 1rem; right: 1rem;
      background: none; border: none; font-size: 1.5rem; cursor: pointer;
      color: var(--muted);
    }
    /* --------- Responsive --------- */
    @media (max-width: 900px) {
      .hero { grid-template-columns: 1fr; }
      .grid-3, .grid-2 { grid-template-columns: 1fr; }
    }
    @media (max-width: 600px) {
      .container { width: 98%; }
      .modal-content { padding: 1rem; }
    }
  </style>
  <script>
    function toggleTheme(){
      document.documentElement.classList.toggle("theme-dark");
      document.documentElement.classList.toggle("theme-light");
    }
    // Modal logic
    function openModal(id) {
      document.getElementById(id).classList.add('active');
      document.body.style.overflow = 'hidden';
    }
    function closeModal(id) {
      document.getElementById(id).classList.remove('active');
      document.body.style.overflow = '';
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
          <li><button id="themeToggle" class="btn" type="button" onclick="toggleTheme()">🌓 Theme</button></li>
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
        <div style="margin: 1rem 0 1.2rem;">
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
        <article class="card project">
          <h3>Blockchain Data Sharing Platform</h3>
          <p>A decentralized app for secure, NFT-based data sharing using Ethereum smart contracts and IPFS.</p>
          <div class="tags">
            <span class="chip">Solidity</span><span class="chip">Hardhat</span><span class="chip">React</span><span class="chip">IPFS</span>
          </div>
          <button class="btn" onclick="openModal('modal1')">Learn More</button>
        </article>
        <article class="card project">
          <h3>Football League AI Chatbot</h3>
          <p>AI chatbot with AIML, NLP, logic reasoning, and CNN-based logo recognition.</p>
          <div class="tags">
            <span class="chip">Python</span><span class="chip">TensorFlow</span><span class="chip">AIML</span><span class="chip">NLTK</span>
          </div>
          <button class="btn" onclick="openModal('modal2')">Learn More</button>
        </article>
        <article class="card project">
          <h3>Global Dorm Accommodation Finder</h3>
          <p>Distributed system integrating multiple APIs and MongoDB for cloud deployment.</p>
          <div class="tags">
            <span class="chip">Java</span><span class="chip">MongoDB</span><span class="chip">REST API</span><span class="chip">Cloud</span>
          </div>
          <button class="btn" onclick="openModal('modal3')">Learn More</button>
        </article>
        <article class="card project">
          <h3>Secure Messaging System</h3>
          <p>Java-based secure messaging client-server with RSA/DES encryption and digital signatures.</p>
          <div class="tags">
            <span class="chip">Java</span><span class="chip">RSA</span><span class="chip">DES</span><span class="chip">Networking</span>
          </div>
          <button class="btn" onclick="openModal('modal4')">Learn More</button>
        </article>
      </div>
  </section>

    <!-- Modals for project details -->
   <div id="modal1" class="modal" onclick="if(event.target==this)closeModal('modal1')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal1')">&times;</button>
        <h3>Blockchain Data Sharing Platform</h3>
        <p><strong>Features:</strong> Mint NFTs for data, integrate IPFS for decentralized storage, transfer/burn NFTs, MetaMask wallet support, responsive React frontend.</p>
        <p><strong>Tech:</strong> Solidity, Hardhat, React, Tailwind, IPFS, OpenZeppelin.</p>
        <p><a href= "https://github.com/gilo9/FYP" > View Repo<a><p>
      </div>
    </div>
   <div id="modal2" class="modal" onclick="if(event.target==this)closeModal('modal2')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal2')">&times;</button>
        <h3>Football League AI Chatbot</h3>
        <p><strong>Features:</strong> Football Q&A via AIML, NLP similarity matching, logic reasoning with NLTK, CNN-based logo classification, real-time API data integration.</p>
        <p><strong>Tech:</strong> Python, AIML, TensorFlow/Keras, NLTK, Pandas, Scikit-learn, httpx, Wikipedia API.</p>
        <p><a href= "https://github.com/gilo9/ChatBot" > View Repo<a><p>
      </div>
    </div>
    <div id="modal3" class="modal" onclick="if(event.target==this)closeModal('modal3')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal3')">&times;</button>
        <h3>Global Dorm Accommodation Finder</h3>
        <p><strong>Features:</strong> RESTful orchestrator, MongoDB storage, geocoding, OSRM, weather APIs, scalable hybrid cloud model, big data-ready design.</p>
        <p><strong>Tech:</strong> Java, MongoDB, GSON, REST, Azure, AWS, BigQuery.</p>
        <p><a href= "https://github.com/gilo9/Client_Server" > View Repo<a><p>
      </div>
    </div>
    <div id="modal4" class="modal" onclick="if(event.target==this)closeModal('modal4')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal4')">&times;</button>
        <h3>Secure Messaging System</h3>
        <p><strong>Features:</strong> RSA key generation, DES encryption, client-server messaging, digital signatures, modular Java architecture.</p>
        <p><strong>Tech:</strong> Java, RSA, DES, Streams, TCP Sockets, GitHub.</p>
        <p><a href= "https://github.com/gilo9/CO3099Assignment" > View Repo<a><p>
      </div>
    </div>

    <!-- Skills -->
  <section id="skills"> 
      <h2>Skills</h2> 
      <div class="grid grid-3">
        <div class="card"><h3>Languages</h3><ul><li>Python, Java, JavaScript, C++, Dart, Solidity, AIML</li></ul></div>
        <div class="card"><h3>Frameworks/Tools</h3><ul><li>React, Flutter, Node.js, Hardhat, MongoDB, Docker, TensorFlow/Keras</li></ul></div>
        <div class="card"><h3>Concepts</h3><ul><li>Blockchain, Smart Contracts, Web3, AI/ML, REST APIs, SOA, Cryptography</li></ul></div>
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
      <h2>Education</h2>
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
