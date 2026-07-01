
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --gh-bg: #0d1117;
            --gh-border: #30363d;
            --hustle-accent: #238636;
            --text-gray: #8b949e;
        }

        /* 1. Slim Top Overlay Banner */
        .mini-hustle-card {
            position: fixed;
            top: 10px; /* Positioned at the top */
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            max-width: 450px; /* Narrower for a cleaner look */
            background: var(--gh-bg);
            border: 1px solid var(--gh-border);
            border-radius: 8px; /* Slightly sharper professional corners */
            padding: 10px 15px;
            cursor: pointer;
            box-shadow: 0 4px 20px rgba(0,0,0,0.6);
            z-index: 1000;
            overflow: hidden;
            display: flex;
            align-items: center;
            gap: 12px;
            animation: borderPulse 4s infinite;
        }

        @keyframes borderPulse {
            0% { border-color: var(--gh-border); }
            50% { border-color: var(--hustle-accent); box-shadow: 0 0 10px rgba(35, 134, 54, 0.2); }
            100% { border-color: var(--gh-border); }
        }

        /* 2. Compact Auto-Slide Content */
        .slide-container {
            flex-grow: 1;
        }

        .slide-text {
            display: none;
            font-size: 0.8rem; /* Smaller font for top overlay */
            line-height: 1.2;
            color: white;
            animation: fadeSlide 0.5s ease;
        }

        .slide-text.active { display: block; }

        @keyframes fadeSlide {
            from { opacity: 0; transform: translateY(-5px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .hustle-tag {
            background: var(--hustle-accent);
            color: white;
            font-size: 0.65rem;
            font-weight: bold;
            padding: 2px 6px;
            border-radius: 4px;
            text-transform: uppercase;
            white-space: nowrap;
        }

        /* 3. Full-Screen Iframe Overlay */
        #iframe-overlay {
            position: fixed;
            top: 0; left: 0; 
            width: 100%; height: 100%;
            background: rgba(0,0,0,0.9);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            backdrop-filter: blur(8px);
        }

        .iframe-container {
            width: 95%; /* Wider for GitHub Page tools */
            max-width: 1200px;
            height: 90vh;
            background: #ffffff;
            border-radius: 12px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 0 50px rgba(0,0,0,0.5);
        }

        .close-iframe {
            position: absolute;
            top: 10px;
            right: 15px;
            background: #f85149;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            z-index: 10001;
            font-weight: bold;
            font-size: 0.8rem;
        }

        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
    </style>
</head>
<body>

    <div class="mini-hustle-card" onclick="openHustleKit()">
        <span class="hustle-tag">NEW</span>
        
        <div class="slide-container">
            <div class="slide-text active">
                <strong>Side Hustle Tools:</strong> Launch your digital business today.
            </div>
            
            <div class="slide-text">
                <strong>Entrepreneur Ideas:</strong> Thrive in the digital economy.
            </div>

            <div class="slide-text">
                <strong>One-Stop Place:</strong> Everything you need online.
            </div>
        </div>

        <span style="color: var(--text-gray); font-size: 1rem;">›</span>
    </div>

    <div id="iframe-overlay" onclick="closeHustleKit(event)">
        <div class="iframe-container" onclick="event.stopPropagation()">
            <button class="close-iframe" onclick="closeHustleKit(event)">CLOSE [X]</button>
            <iframe src="https://msha.ke/debeatzgh#digimartgh-1" title="Side Hustle Starter Kit"></iframe>
        </div>
    </div>

    <script>
        // Auto-Slide Logic
        let currentSlide = 0;
        const slides = document.querySelectorAll('.slide-text');
        
        function rotateSlides() {
            slides[currentSlide].classList.remove('active');
            currentSlide = (currentSlide + 1) % slides.length;
            slides[currentSlide].classList.add('active');
        }

        setInterval(rotateSlides, 3500); 

        // Iframe Open/Close Logic
        function openHustleKit() {
            document.getElementById('iframe-overlay').style.display = 'flex';
            document.body.style.overflow = 'hidden'; // Prevent background scroll
        }

        function closeHustleKit(event) {
            document.getElementById('iframe-overlay').style.display = 'none';
            document.body.style.overflow = 'auto'; // Restore scroll
        }
    </script>
















<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Digital Creators Hub – Build With AI</title>

<style>
:root{
  --primary:#2563eb;
  --secondary:#16a34a;
  --dark:#020617;
}
body{
  margin:0;
  font-family:system-ui,Arial,sans-serif;
  background:#f1f5f9;
  color:#1e293b;
}

/* HERO */
.hero{
  background:linear-gradient(135deg,var(--primary),var(--secondary));
  color:white;
  padding:70px 20px;
  text-align:center;
}
.hero h1{margin:0;font-size:2.6rem}
.hero p{max-width:900px;margin:15px auto;font-size:1.1rem}

/* LAYOUT */
.container{max-width:1200px;margin:auto;padding:30px}
.section{
  background:white;
  padding:28px;
  margin-bottom:30px;
  border-radius:16px;
  box-shadow:0 12px 35px rgba(0,0,0,.06);
}
.section h2{color:var(--primary);margin-top:0}

.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:22px;
}
.card{
  background:#f8fafc;
  padding:22px;
  border-radius:14px;
}

/* BUTTONS */
@keyframes heartbeat{0%{transform:scale(1)}14%{transform:scale(1.15)}28%{transform:scale(1)}}
@keyframes shake{0%{transform:translateX(0)}25%{transform:translateX(-3px)}50%{transform:translateX(3px)}75%{transform:translateX(-3px)}100%{transform:translateX(0)}}

.btn{
  display:inline-block;
  margin-top:12px;
  padding:10px 18px;
  background:var(--primary);
  color:white;
  border-radius:8px;
  text-decoration:none;
  font-size:.9rem;
  cursor:pointer;
  animation:heartbeat 2.8s infinite;
  position:relative;
}

/* IFRAME VIEWER */
#viewer{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.88);
  display:none;
  z-index:9999;
}
#viewer iframe{width:100%;height:90%;border:none}

/* NAVIGATION CONTROLS AT BOTTOM */
.controls-bottom{
  position:absolute;
  bottom:25px;
  left:50%;
  transform:translateX(-50%);
  display:flex;
  gap:14px;
  z-index:10000;
}
.controls-bottom .control{
  background:#020617;
  color:white;
  padding:10px 14px; /* Bigger buttons */
  border-radius:30%;
  cursor:pointer;
  font-size:1.3rem; /* Bigger icon */
}

/* CLOSE BUTTON RIGHT CENTER */
#closeBtn{
  position:absolute;
  bottom:25%;
  right:16px;
  transform:translateY(-50%);
  background:#ef4444;
  color:white;
  padding:12px 16px;
  border-radius:30%;
  cursor:pointer;
  z-index:10001;
  font-size:1.2rem;
}

/* FOOTER */
footer{
  background:#020617;
  color:#cbd5f5;
  padding:35px;
  text-align:center;
}
</style>
</head>

<body>

<!-- HERO -->
<div class="hero">
  <h1>Digital Creators Hub</h1>
  <p>Treasure troves for startups, creators, and entrepreneurs who want to build successful digital assets and online presence from scratch.</p>
</div>

<div class="container">

<!-- CONTENT BUTTONS -->
<div class="section">
<h2>🌐 Explore Our Tools & Guides</h2>
<div class="grid">

<div class="card">
<h3>Collaborators Hub</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/Debeatzgh-Collaborators-Hub/')">Open</button>
</div>

<div class="card">
<h3>AI Starter Kit</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/Decode-AI-starter-kit-/')">Open</button>
</div>

<div class="card">
<h3>Side Hustle Guide</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/The-Ultimate-Guide-to-Side-Hustle/')">Open</button>
</div>

<div class="card">
<h3>Sales Strategies</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/sales/')">Open</button>
</div>

<div class="card">
<h3>Online Business Kit</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/Online-business-kit/')">Open</button>
</div>

<div class="card">
<h3>Home Hub</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/Home-/')">Open</button>
</div>

<div class="card">
<h3>Productivity Web App</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/Improve-productivity-with-AI-Web-App-project-/')">Open</button>
</div>

<div class="card">
<h3>Menu Widget</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/menu-widget-/')">Open</button>
</div>

<div class="card">
<h3>AI Chat</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/ai-chat/')">Open</button>
</div>

<div class="card">
<h3>Games</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/games-/')">Open</button>
</div>

<div class="card">
<h3>Flashcards Widget</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/Floating-Flashcards-Widget/')">Open</button>
</div>

<div class="card">
<h3>Docs Carousel</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/Docs-Carousel-for-Blogger/')">Open</button>
</div>

<div class="card">
<h3>Posts</h3>
<button class="btn" onclick="openSmart('https://debeatzgh1.github.io/posts/')">Open</button>
</div>

</div>
</div>

</div>

<!-- VIEWER -->
<div id="viewer">
  <iframe id="docFrame"></iframe>
  <!-- CLOSE BUTTON RIGHT CENTER -->
  <div id="closeBtn" onclick="closeViewer()">✕</div>
  <!-- NAVIGATION BUTTONS BOTTOM -->
  <div class="controls-bottom">
    <div class="control" onclick="goBack()">⟵</div>
    <div class="control" onclick="goForward()">⟶</div>
    <div class="control" onclick="toggleFullscreen()">⛶</div>
  </div>
</div>

<footer>
<p>© Digital Creators Hub – Debeatzgh</p>
<p>Build • Learn • Monetize with AI</p>
</footer>

<script>
let historyStack=[],historyIndex=-1;

// Open URL in iframe or new tab for ads
function openSmart(url){
  const wpAdDomains=["ads.com","doubleclick.net","googleads"];
  const isWPAd=wpAdDomains.some(d=>url.includes(d));

  if(isWPAd){
    window.open(url,'_blank');
    return;
  }

  document.getElementById('viewer').style.display='block';
  loadUrl(url,true);
}

function loadUrl(url,push){
  document.getElementById('docFrame').src=url;
  if(push){
    historyStack=historyStack.slice(0,historyIndex+1);
    historyStack.push(url);
    historyIndex++;
  }
}

function goBack(){if(historyIndex>0){historyIndex--;loadUrl(historyStack[historyIndex],false)}}
function goForward(){if(historyIndex<historyStack.length-1){historyIndex++;loadUrl(historyStack[historyIndex],false)}}
function toggleFullscreen(){
  const v=document.getElementById('viewer');
  if(!document.fullscreenElement){v.requestFullscreen().catch(()=>{})}
  else{document.exitFullscreen()}
}
function closeViewer(){
  document.getElementById('viewer').style.display='none';
  document.getElementById('docFrame').src='';
}

// Shaking animation every 3s
setInterval(()=>{
  document.querySelectorAll('.btn').forEach(btn=>{
    btn.style.animation='heartbeat 2.8s, shake 0.6s';
    setTimeout(()=>btn.style.animation='heartbeat 2.8s',600);
  });
},3000);

</script>

</body>
</html>
