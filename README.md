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
        <article class="card project" data-tags="blockchain security frontend">
          <h3>Secure File Sharing Dapp</h3>
          <p>Decentralized file-sharing platform using Ethereum smart contracts, IPFS, React, and Node.js.</p>
          <div class="tags">
            <span class="chip">Solidity</span><span class="chip">IPFS</span><span class="chip">React</span><span class="chip">Node.js</span>
          </div>
          <button class="btn" onclick="openModal('modal1')">Learn More</button>
          <p><a href="https://github.com/gilesmwa/secure-file-sharing" target="_blank">Repo</a></p>
        </article>
        <article class="card project" data-tags="ai ml chatbot">
          <h3>AI Chatbot with Image Classifier</h3>
          <p>Football chatbot identifying club logos and player faces using CNNs in Python.</p>
          <div class="tags">
            <span class="chip">Python</span><span class="chip">PyTorch</span><span class="chip">OpenCV</span>
          </div>
          <button class="btn" onclick="openModal('modal2')">Learn More</button>
        </article>
        <article class="card project" data-tags="mobile flutter security">
          <h3>Authentication App</h3>
          <p>Flutter app for secure hardware access with time-based tokens and Firebase integration.</p>
          <div class="tags"><span class="chip">Flutter</span><span class="chip">Dart</span><span class="chip">Firebase</span></div>
          <button class="btn" onclick="openModal('modal3')">Learn More</button>
        </article>
      </div>
  </section>

    <!-- Modals for project details -->
   <div id="modal1" class="modal" onclick="if(event.target==this)closeModal('modal1')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal1')">&times;</button>
        <h3>Secure File Sharing Dapp</h3>
        <p>
          <strong>Overview:</strong> This project is an innovative proof-of-concept platform for secure, decentralized data sharing, combining blockchain technology (Ethereum smart contracts) with distributed storage (IPFS) and advanced cryptography. It addresses the vulnerabilities and limitations of traditional centralized data systems—including single points of failure, privacy risks, and compliance challenges—by leveraging blockchain’s immutability, transparency, and decentralized trust.
        </p>
        <p><strong>Key Features</strong></p>
        <ul>
          <li><strong>Smart Contract-Controlled File Sharing</strong>Implements a custom ERC-721 (NFT) smart contract on Ethereum. Each uploaded file is tokenized as an NFT, representing ownership and access rights immutably on-chain.</li>
          <li><strong>Decentralized Storage via IPFS:</strong>Actual files are stored off-chain in IPFS, a peer-to-peer protocol, with only their cryptographic hashes and metadata registered on the blockchain, minimizing costs and ensuring tamper resistance.</li>
          <li><strong>Access Control & Auditability:</strong> Owners can grant/revoke access to files via smart contract functions, allowing for fine-grained permissions. All actions (uploads, access grants, transfers) are logged immutably for transparency and audit.</li>
          <li><strong>End-to-End Encryption:</strong>Files are encrypted with AES before IPFS upload, ensuring confidentiality. Only authorized users can decrypt and access the data.</li>
          <li><strong>User Interface (Front-End DApp):</strong>Built in React.js, the web app integrates with MetaMask for authentication, allowing users to upload, share, and manage files seamlessly. The DApp interacts with Ethereum via Ethers.js/Web3.js and IPFS via its HTTP API.</li>
          <li>Regulatory Compliance:<strong></strong>Designed to comply with GDPR by keeping personal data off-chain and using cryptographic methods to enforce privacy and data erasure.</li>
        </ul> 
        <p><strong>Technologies Used:</strong></p> 
        <ul>
          <li><span class= "chip">Ethereum / Solidity / Hardhat</span>For smart contract development, deployment, and automated testing.</li>
          <li><span class= "chip">IPFS</span>For decentralized, content-addressable file storage.</li>
          <li><span class= "chip">React.js</span>For responsive, modular frontend DApp development.</li>
          <li><span class= "chip">Web3.js / Ethers.js</span>For blockchain interaction in the frontend.</li>
          <li><span class= "chip">MetaMask</span> For wallet integration and user authentication.</li>
          <li><span class= "chip">OpenZeppelin</span>For secure, audited smart contract libraries.</li>
          <li><span class= "chip">GitHub</span>For version control and backup.</li>
        </ul>
        <p><a href="https://github.com/gilesmwa/secure-file-sharing" target="_blank">View Repository</a></p>
      </div>
    </div>
   <div id="modal2" class="modal" onclick="if(event.target==this)closeModal('modal2')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal2')">&times;</button>
        <h3>AI Chatbot with Image Classifier</h3>
        <p>
          <strong>Overview:</strong> Football chatbot that identifies club logos and player faces using custom-trained CNNs in Python. Integrated into a web interface for interactive use.
        </p>
        <ul>
          <li>Deep learning with PyTorch</li>
          <li>Image processing via OpenCV</li>
          <li>Custom dataset for football clubs/players</li>
          <li>Web integration for user interaction</li>
        </ul>
      </div>
    </div>
    <div id="modal3" class="modal" onclick="if(event.target==this)closeModal('modal3')">
      <div class="modal-content">
        <button class="modal-close" onclick="closeModal('modal3')">&times;</button>
        <h3>Authentication App</h3>
        <p>
          <strong>Overview:</strong> Mobile app for secure hardware access, using time-based tokens and real-time expiry logic. Built with Flutter and Firebase.
        </p>
        <ul>
          <li>Flutter mobile development</li>
          <li>Time-based token generation</li>
          <li>Firebase for backend/auth</li>
          <li>Security-first design</li>
        </ul>
      </div>
    </div>

    <!-- Skills -->
  <section id="skills"> 
      <h2>Skills</h2> 
      <div class="grid grid-3">
        <div class="card"><h3>Languages</h3><ul><li>Python, Java, JavaScript, C++, Dart, Solidity</li></ul></div>
        <div class="card"><h3>Frameworks/Tools</h3><ul><li>React, Flutter, Node.js, Hardhat, MongoDB, Docker</li></ul></div>
        <div class="card"><h3>Concepts</h3><ul><li>Blockchain, Smart Contracts, Web3, REST APIs, OOP, DSA</li></ul></div>
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
