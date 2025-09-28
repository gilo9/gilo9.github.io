<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Giles Mwa — Portfolio</title>
  <meta name="description" content="Portfolio of Giles Mwa: blockchain, AI/ML, distributed systems, and secure development projects." />
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
      --shadow: 0 2px 16px rgba(60, 80, 120, 0.08);  }
  

  :root[data-theme="dark"] {
      --bg: #101624;
      --text: #e5e7eb;
      --muted: #94a3b8;
      --card: #18223a;
      --border: #1f2937;
      --brand: #60a5fa;
      --brand-weak: #0b294f;
      --shadow: 0 2px 16px rgba(60, 80, 120, 0.18);
    }

  body {
      background: var(--bg);
      color: var(--text);
    }
    /* --------- Layout --------- */
    .container { width: min(1000px, 94%); margin: 0 auto; }
    header {
        border-radius: 25px;
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
      list-style: none; display: flex; gap: 1.2rem; margin: 0; padding: 0; align-items: center;
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
    /* --------- General table styles --------- */
    table {
        display: flex;
      width: 100%;
      border-collapse: collapse;
      font-size: 0.95rem;
      background: var(--card); /* Matches the card background */
      color: var(--text); /* Matches the text color */
      border: 1px solid var(--border); /* Matches the border color */
    }

  table th, table td {
    background: var(--card);
      text-align: left;
      padding: 6px;
      border-bottom: 1px solid var(--border); /* Matches the border color */
    }

  table th {
      font-weight: bold;
    }

  table tr:last-child td {
      border-bottom: none; /* Remove border for the last row */
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
    .navigation{
        display: flex;
        align-items: center;   /* vertical centering */
        
        height: 50px;         /* needs a defined height */
        border: 1px solid #ccc;

    }
  </style>
  <script>
  function toggleTheme() {
    const html = document.documentElement;
    const currentTheme = html.getAttribute("data-theme");
    const newTheme = currentTheme === "dark" ? "light" : "dark";
    html.setAttribute("data-theme", newTheme);
    localStorage.setItem("theme", newTheme); // Save theme preference
  }

  // Load saved theme on page load
  document.addEventListener("DOMContentLoaded", () => {
    const savedTheme = localStorage.getItem("theme") || "light";
    document.documentElement.setAttribute("data-theme", savedTheme);
  });
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
      <nav aria-label="Primary" >
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
        <p class="lead">Computer Science graduate with strong hands-on experience in <strong>blockchain</strong>, <strong>AI/ML</strong>, and <strong>secure systems development</strong>. I’m passionate about solving real-world problems through secure, scalable, and user-centric tech solutions.</p>
        <div style="margin: 1rem 0 1.2rem;">
          <span class="chip">📍 London, UK</span>
          <span class="chip">🎯 Tech Consulting Track</span>
          <span class="chip">🔒 Security-first mindset</span>
        </div>
        <div style="display: flex; gap: 0.8rem; flex-wrap: wrap;">
          <a class="btn" href="#projects">View Projects</a>
          <a class="btn" href="./Giles-Mwa-CV.pdf" target="_blank" rel="noopener"><Strong>View CV</Strong></a>
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
            <img src="https://img.shields.io/badge/Solidity-%5E0.8.26-green" alt="Solidity" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/Hardhat-%E2%9C%93-blue" alt="Hardhat" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/React-18.x-blue" alt="React" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/IPFS-available-lightgrey" alt="IPFS" style="height:20px; margin-right:6px;"/>
          </div>
          <div style="margin-top:8px;">
            <table style="width:100%; border-collapse:collapse; font-size:0.95rem;">
              <tr>
                <th style="text-align:left; padding:6px; border-bottom:1px solid #e5e7eb;">Component</th>
                <th style="text-align:left; padding:6px; border-bottom:1px solid #e5e7eb;">Technologies</th>
              </tr>
              <tr>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">Smart Contracts</td>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">Solidity (ERC-721), OpenZeppelin, Hardhat</td>
              </tr>
              <tr>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">Frontend</td>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">React, Ethers.js, TailwindCSS</td>
              </tr>
              <tr>
                <td style="padding:6px;">Storage & Wallets</td>
                <td style="padding:6px;">IPFS (kubo), MetaMask</td>
              </tr>
            </table>
          </div>
          <button class="btn" onclick="openModal('modal1')" style="margin-top:10px;">Learn More</button>
        </article>

  <article class="card project">
         <h3>Football League AI Chatbot</h3>
         <p>AI chatbot with AIML, NLP, logic reasoning, and CNN-based logo recognition.</p>
          <div class="tags">
            <img src="https://img.shields.io/badge/Python-3.x-blue" alt="Python" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/TensorFlow-Keras-orange" alt="TensorFlow/Keras" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/AIML-Chatbot-lightgrey" alt="AIML" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/NLTK-NLP-important" alt="NLTK" style="height:20px; margin-right:6px;"/>
          </div>
          <div style="margin-top:8px;">
            <table style="width:100%; border-collapse:collapse; font-size:0.95rem;">
              <tr>
                <th style="text-align:left; padding:6px; border-bottom:1px solid #e5e7eb;">Component</th>
                <th style="text-align:left; padding:6px; border-bottom:1px solid #e5e7eb;">Technologies</th>
              </tr>
              <tr>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">Conversational Agents</td>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">AIML rules, pattern-matching agents</td>
              </tr>
              <tr>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">NLP & Q&A</td>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">TF-IDF, Scikit-learn, Pandas, Wikipedia API</td>
              </tr>
              <tr>
                <td style="padding:6px;">Image Classification</td>
                <td style="padding:6px;">TensorFlow/Keras CNN, OpenCV</td>
              </tr>
            </table>
          </div>
          <button class="btn" onclick="openModal('modal2')" style="margin-top:10px;">Learn More</button>
       </article>

  <article class="card project">
          <h3>Global Dorm Accommodation Finder</h3>
          <p>Distributed system integrating multiple APIs and MongoDB for cloud deployment.</p>
          <div class="tags">
            <img src="https://img.shields.io/badge/Java-17-blue" alt="Java" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/MongoDB-4.x-green" alt="MongoDB" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/REST-API-lightgrey" alt="REST" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/Cloud-Azure%2FAWS-lightgrey" alt="Cloud" style="height:20px; margin-right:6px;"/>
          </div>
          <div style="margin-top:8px;">
            <table style="width:100%; border-collapse:collapse; font-size:0.95rem;">
              <tr>
                <th style="text-align:left; padding:6px; border-bottom:1px solid #e5e7eb;">Component</th>
                <th style="text-align:left; padding:6px; border-bottom:1px solid #e5e7eb;">Technologies</th>
              </tr>
              <tr>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">Orchestrator Service</td>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">Java REST endpoints, GSON</td>
              </tr>
              <tr>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">Persistence</td>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">MongoDB (NoSQL)</td>
              </tr>
              <tr>
                <td style="padding:6px;">External APIs</td>
                <td style="padding:6px;">OSRM, OpenCage Geocoding, 7Timer! Weather</td>
              </tr>
            </table>
          </div>
          <button class="btn" onclick="openModal('modal3')" style="margin-top:10px;">Learn More</button>
        </article>

  <article class="card project">
          <h3>Secure Messaging System</h3>
          <p>Java-based secure messaging client-server with RSA/DES encryption and digital signatures.</p>
          <div class="tags">
            <img src="https://img.shields.io/badge/Java-11%2B-blue" alt="Java" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/RSA-Crypto-lightgrey" alt="RSA" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/DES-Legacy-orange" alt="DES" style="height:20px; margin-right:6px;"/>
            <img src="https://img.shields.io/badge/TCP-Sockets-lightgrey" alt="Networking" style="height:20px; margin-right:6px;"/>
          </div>
          <div style="margin-top:8px;">
            <table style="width:100%; border-collapse:collapse; font-size:0.95rem;">
              <tr>
                <th style="text-align:left; padding:6px; border-bottom:1px solid #e5e7eb;">Component</th>
                <th style="text-align:left; padding:6px; border-bottom:1px solid #e5e7eb;">Technologies</th>
              </tr>
              <tr>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">Key Management</td>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">RSA key generation utilities</td>
              </tr>
              <tr>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">Encryption</td>
                <td style="padding:6px; border-bottom:1px solid #f1f5f9;">DES symmetric encryption & RSA asymmetric</td>
              </tr>
              <tr>
                <td style="padding:6px;">Networking</td>
                <td style="padding:6px;">TCP sockets, DataInputStream/DataOutputStream</td>
              </tr>
            </table>
          </div>
          <button class="btn" onclick="openModal('modal4')" style="margin-top:10px;">Learn More</button>
        </article>
      </div>
    </section>

    <!-- Modals for project details -->
   <div id="modal1" class="modal" onclick="if(event.target==this)closeModal('modal1')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal1')">&times;</button>
        <h3>Blockchain Data Sharing Platform</h3>
        <p><strong>Features:</strong> Mint NFTs to represent files/data, IPFS-backed storage, transfer/burn tokens, wallet authentication (MetaMask), responsive React UI, test suite with Hardhat.</p>
        <p><strong>Tech Stack:</strong> Solidity (ERC-721), Hardhat, OpenZeppelin, React, Ethers.js, IPFS, TailwindCSS.</p>
        <p><strong>Repository:</strong> <a href="https://github.com/gilo9/FYP" target="_blank" rel="noopener">View Repository</a></p>
        <p><strong>Quick setup</strong></p>
      </div>
    </div>

   <div id="modal2" class="modal" onclick="if(event.target==this)closeModal('modal2')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal2')">&times;</button>
        <h3>Football League AI Chatbot</h3>
        <p><strong>Features:</strong> AIML-based conversational rules, TF-IDF similarity Q&A, first-order logic reasoning (dynamic KB), CNN image classifier for league logos, API integration for live football data.</p>
        <p><strong>Tech Stack:</strong> Python, AIML, TensorFlow/Keras, NLTK, Scikit-learn, Pandas, OpenCV, httpx/Wikipedia API.</p>
        <p><strong>Repository:</strong> <a href="https://github.com/gilo9/ChatBot" target="_blank" rel="noopener">View Repository</a>/p>
      </div>
    </div>

   <div id="modal3" class="modal" onclick="if(event.target==this)closeModal('modal3')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal3')">&times;</button>
        <h3>Global Dorm - Distributed Accommodation Finder</h3>
        <p><strong>Features:</strong> RESTful orchestrator for searching/applying for rooms, JSON-based communication, MongoDB persistence, geocoding and distance enrichment (OpenCage + OSRM), 7-day weather integration (7Timer!), hybrid cloud-ready architecture.</p>
        <p><strong>Tech Stack:</strong> Java, GSON, MongoDB, HTTP REST, OSRM, OpenCage, 7Timer!, Azure/AWS (deployment).</p>
        <p><strong>Repository:</strong> <a href="https://github.com/gilo9/Orchestrator" target="_blank" rel="noopener">View Repository</a></p>
      </div>
    </div>

   <div id="modal4" class="modal" onclick="if(event.target==this)closeModal('modal4')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal4')">&times;</button>
        <h3>Secure Messaging System (CO3099)</h3>
        <p><strong>Features:</strong> RSA key generation utilities, DES-based symmetric encryption demo, signed/encrypted client-server messaging, modular Java code for streams and byte handling.</p>
        <p><strong>Tech Stack:</strong> Java, RSA, DES, TCP sockets, DataInputStream/DataOutputStream.</p>
        <p><strong>Repository:</strong> <a href="https://github.com/gilo9/Client-Server" target="_blank" rel="noopener">View Repository</a></p>
      </div>
    </div>

    <!-- Skills -->
   <section id="skills">
      <h2>Skills</h2>
      <div class="grid grid-3">
        <div class="card"><h3>Languages</h3><ul><li>Python, Java, JavaScript, C++, Dart, Solidity, AIML</li></ul></div>
        <div class="card"><h3>Frameworks &amp; Tools</h3><ul><li>React, Flutter, Node.js, Hardhat, MongoDB, Docker, TensorFlow/Keras, OpenZeppelin</li></ul></div>
        <div class="card"><h3>Concepts</h3><ul><li>Blockchain, Smart Contracts, Web3, AI/ML, REST APIs, SOA, Cryptography, Distributed Systems</li></ul></div>
      </div>
      <div style="margin-top:12px;">
        <img src="https://img.shields.io/badge/Python-3.x-blue" alt="Python" style="height:20px; margin-right:6px;"/>
        <img src="https://img.shields.io/badge/Java-11%2B-blue" alt="Java" style="height:20px; margin-right:6px;"/>
        <img src="https://img.shields.io/badge/JavaScript-ES6-yellow" alt="JavaScript" style="height:20px; margin-right:6px;"/>
        <img src="https://img.shields.io/badge/Solidity-%5E0.8.26-green" alt="Solidity" style="height:20px; margin-right:6px;"/>
        <img src="https://img.shields.io/badge/React-18.x-blue" alt="React" style="height:20px; margin-right:6px;"/>
        <img src="https://img.shields.io/badge/TensorFlow-Keras-orange" alt="TensorFlow" style="height:20px; margin-right:6px;"/>
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
