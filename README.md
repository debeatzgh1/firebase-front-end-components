

    <div class="page-container">
        <!-- Site Header Navigation Context -->
        <header>
            <div class="logo">DEBEATZGH</div>
            <div class="status-pill">
                <span class="status-dot"></span>
                Ehub Hub Active
            </div>
        </header>

        <!-- Main Identity Showcase (Hero Section) -->
        <main class="hero">
            <h1>Next-Generation Creative & Digital Workspace Portals</h1>
            <p>Deploying lightweight automation blocks, production widgets, streaming modules, and asset kits tailored for active developers and digital web managers.</p>
            <div class="cta-group">
                <!-- Direct hook execution mimicking action parameters -->
                <button class="btn-primary" onclick="document.getElementById('dbz-btn').click();">
                    Launch Interactive App Hub
                </button>
            </div>
        </main>

        <!-- Spatial Feature Indexing Matrix Section -->
        <section class="features-grid">
            <div class="feature-card">
                <h3>Floating Workspace</h3>
                <p>Access your primary digital environments securely via our dedicated corner window interface system without shifting away from your running tab.</p>
            </div>
            <div class="feature-card">
                <h3>Lazy Architecture</h3>
                <p>Saves visual processing resources by compiling system memory structures exclusively when interaction parameters occur on screen.</p>
            </div>
            <div class="feature-card">
                <h3>Mobile Fluidity</h3>
                <p>Fully decoupled native multi-touch swipe mechanics handle item sorting gracefully across narrow physical panel layouts.</p>
            </div>
        </section>

        <div class="section-divider"></div>

        <!-- SCRIPT CONTAINER 2: Embed Object FAQ Interface Frame Insertion -->
        <div id="dbz-faq-hub">
            <style>
                #dbz-faq-hub {
                    --dbz-space-bg: #090d16;
                    --dbz-panel-bg: rgba(15, 23, 42, 0.65);
                    --dbz-card-border: rgba(255, 255, 255, 0.06);
                    --dbz-text-main: #f8fafc;
                    --dbz-text-muted: #94a3b8;
                    --dbz-accent-neon: #d946ef; /* Ehub / DeBeatzGH Accent Magenta */
                    --dbz-accent-blue: #3b82f6;
                    
                    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, sans-serif;
                    background: var(--dbz-space-bg);
                    color: var(--dbz-text-main);
                    padding: 40px 16px;
                    max-width: 768px;
                    margin: 0 auto;
                    border-radius: 24px;
                }

                #dbz-faq-hub h2 {
                    text-align: center;
                    font-size: 1.75rem;
                    font-weight: 900;
                    margin-bottom: 24px;
                    background: linear-gradient(45deg, var(--dbz-text-main), var(--dbz-text-muted));
                    -webkit-background-clip: text;
                    -webkit-text-fill-color: transparent;
                    letter-spacing: -0.5px;
                }

                /* Swipeable Mobile Category Bar */
                #dbz-faq-hub .category-slider {
                    display: flex;
                    gap: 10px;
                    overflow-x: auto;
                    scroll-snap-type: x mandatory;
                    scrollbar-width: none; /* Hide scrollbar for Firefox */
                    -webkit-overflow-scrolling: touch;
                    padding-bottom: 16px;
                    margin-bottom: 20px;
                    border-bottom: 1px solid var(--dbz-card-border);
                }

                #dbz-faq-hub .category-slider::-webkit-scrollbar {
                    display: none; /* Hide scrollbar for Chrome/Safari */
                }

                #dbz-faq-hub .cat-btn {
                    flex: 0 0 auto;
                    scroll-snap-align: start;
                    background: rgba(255, 255, 255, 0.03);
                    border: 1px solid var(--dbz-card-border);
                    color: var(--dbz-text-muted);
                    padding: 8px 18px;
                    border-radius: 20px;
                    font-size: 0.85rem;
                    font-weight: 600;
                    cursor: pointer;
                    transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
                }

                #dbz-faq-hub .cat-btn.active {
                    background: linear-gradient(135deg, var(--dbz-accent-neon) 0%, var(--dbz-accent-blue) 100%);
                    color: #ffffff;
                    border-color: transparent;
                    box-shadow: 0 4px 15px rgba(217, 70, 239, 0.25);
                }

                /* Lazy Load Accordion Layout */
                #dbz-faq-hub .faq-wrapper {
                    display: none;
                    flex-direction: column;
                    gap: 12px;
                }

                #dbz-faq-hub .faq-wrapper.active {
                    display: flex;
                    animation: dbzFadeIn 0.35s ease;
                }

                #dbz-faq-hub .faq-item {
                    background: var(--dbz-panel-bg);
                    border: 1px solid var(--dbz-card-border);
                    border-radius: 14px;
                    overflow: hidden;
                    transition: border-color 0.2s ease;
                }

                #dbz-faq-hub .faq-trigger {
                    width: 100%;
                    padding: 16px 20px;
                    text-align: left;
                    background: transparent;
                    border: none;
                    color: var(--dbz-text-main);
                    font-size: 0.95rem;
                    font-weight: 700;
                    cursor: pointer;
                    display: flex;
                    justify-content: space-between;
                    align-items: center;
                    gap: 15px;
                }

                #dbz-faq-hub .faq-icon {
                    font-size: 0.75rem;
                    color: var(--dbz-text-muted);
                    transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
                    flex-shrink: 0;
                }

                #dbz-faq-hub .faq-item.open {
                    border-color: rgba(217, 70, 239, 0.25);
                }

                #dbz-faq-hub .faq-item.open .faq-icon {
                    transform: rotate(180deg);
                    color: var(--dbz-accent-neon);
                }

                #dbz-faq-hub .faq-content {
                    max-height: 0;
                    overflow: hidden;
                    transition: max-height 0.3s cubic-bezier(0.4, 0, 0.2, 1);
                    background: rgba(0, 0, 0, 0.15);
                }

                #dbz-faq-hub .faq-content-inner {
                    padding: 16px 20px;
                    font-size: 0.88rem;
                    line-height: 1.5;
                    color: var(--dbz-text-muted);
                    border-top: 1px solid rgba(255, 255, 255, 0.02);
                }

                @keyframes dbzFadeIn {
                    from { opacity: 0; transform: translateY(6px); }
                    to { opacity: 1; transform: translateY(0); }
                }
            </style>

            <h2>Frequently Asked Questions</h2>

            <div class="category-slider" id="dbz-faq-cats">
                <button class="cat-btn active" onclick="switchFaqCategory('general')">General Portal</button>
                <button class="cat-btn" onclick="switchFaqCategory('ehub')">Ehub Streaming</button>
                <button class="cat-btn" onclick="switchFaqCategory('resources')">Creative Assets</button>
            </div>

            <div class="faq-wrapper active" id="faq-general">
                <div class="faq-item">
                    <button class="faq-trigger" onclick="toggleFaqAccordion(this, 'What is the DeBeatzGH workspace hub?')">
                        <span>What is the DeBeatzGH workspace hub?</span>
                        <span class="faq-icon">▼</span>
                    </button>
                    <div class="faq-content"><div class="faq-content-inner"></div></div>
                </div>
                <div class="faq-item">
                    <button class="faq-trigger" onclick="toggleFaqAccordion(this, 'How do I submit forms via GitHub pages safely?')">
                        <span>How do I submit forms via GitHub pages safely?</span>
                        <span class="faq-icon">▼</span>
                    </button>
                    <div class="faq-content"><div class="faq-content-inner"></div></div>
                </div>
            </div>

            <div class="faq-wrapper" id="faq-ehub">
                <div class="faq-item">
                    <button class="faq-trigger" onclick="toggleFaqAccordion(this, 'Where can I find the official music countdown charts?')">
                        <span>Where can I find the official music countdown charts?</span>
                        <span class="faq-icon">▼</span>
                    </button>
                    <div class="faq-content"><div class="faq-content-inner"></div></div>
                </div>
                <div class="faq-item">
                    <button class="faq-trigger" onclick="toggleFaqAccordion(this, 'Can I integrate the floating Ehub widget into my blog?')">
                        <span>Can I integrate the floating Ehub widget into my blog?</span>
                        <span class="faq-icon">▼</span>
                    </button>
                    <div class="faq-content"><div class="faq-content-inner"></div></div>
                </div>
            </div>

            <div class="faq-wrapper" id="faq-resources">
                <div class="faq-item">
                    <button class="faq-trigger" onclick="toggleFaqAccordion(this, 'Are the blogger templates free to modify?')">
                        <span>Are the blogger templates free to modify?</span>
                        <span class="faq-icon">▼</span>
                    </button>
                    <div class="faq-content"><div class="faq-content-inner"></div></div>
                </div>
            </div>

            <script>
                // Tab Switch Engine
                function switchFaqCategory(catId) {
                    document.querySelectorAll('#dbz-faq-hub .faq-wrapper').forEach(wrapper => {
                        wrapper.classList.remove('active');
                    });
                    document.querySelectorAll('#dbz-faq-hub .cat-btn').forEach(btn => {
                        btn.classList.remove('active');
                    });

                    document.getElementById(`faq-${catId}`).classList.add('active');
                    
                    const activeBtn = Array.from(document.querySelectorAll('#dbz-faq-hub .cat-btn')).find(btn => {
                        return btn.getAttribute('onclick').includes(catId);
                    });
                    if (activeBtn) {
                        activeBtn.classList.add('active');
                        activeBtn.scrollIntoView({ behavior: 'smooth', block: 'nearest', inline: 'center' });
                    }
                }

                // Lazy-Loading Accordion Logic Engine
                function toggleFaqAccordion(triggerElement, questionText) {
                    const faqItem = triggerElement.parentElement;
                    const contentPane = faqItem.querySelector('.faq-content');
                    const innerTextNode = faqItem.querySelector('.faq-content-inner');

                    if (!innerTextNode.innerHTML || innerTextNode.innerHTML.trim() === "") {
                        innerTextNode.innerHTML = fetchLazyFaqData(questionText);
                    }

                    const currentWrapper = faqItem.parentElement;
                    currentWrapper.querySelectorAll('.faq-item').forEach(item => {
                        if (item !== faqItem) {
                            item.classList.remove('open');
                            item.querySelector('.faq-content').style.maxHeight = null;
                        }
                    });

                    if (faqItem.classList.contains('open')) {
                        faqItem.classList.remove('open');
                        contentPane.style.maxHeight = null;
                    } else {
                        faqItem.classList.add('open');
                        contentPane.style.maxHeight = contentPane.scrollHeight + "px";
                    }
                }

                function fetchLazyFaqData(question) {
                    const dictionary = {
                        "What is the DeBeatzGH workspace hub?": "The DeBeatzGH workspace hub is a unified dashboard designed to catalog tools, widgets, entertainment pipelines, and custom API interfaces for creators, developers, and platform managers.",
                        "How do I submit forms via GitHub pages safely?": "Our system integrates lightweight sandboxed oembed environments. Your form fields render lazily inside designated sandboxes, bypassing raw infrastructure processing for maximum data compliance.",
                        "Where can I find the official music countdown charts?": "All digital entertainment updates are broadcast live inside the Ehub portal stream. Simply deploy the layout toggle widget or launch our system carousel overlays to view updated ranks.",
                        "Can I integrate the floating Ehub widget into my 



<!-- Live Workspace Embed Component -->
<div class="dbz-embed-container" style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; margin: 20px auto; max-width: 1000px; border-radius: 16px; overflow: hidden; box-shadow: 0 10px 30px rgba(0,0,0,0.08); border: 1px solid #e2e8f0; background: #ffffff;">
    
    <!-- Control Header -->
    <div style="background: #f8fafc; padding: 12px 20px; border-b: 1px solid #e2e8f0; display: flex; justify-content: space-between; items-center: center; flex-wrap: wrap; gap: 10px;">
        <div style="display: flex; items-center: center; gap: 8px;">
            <span style="width: 10px; height: 10px; border-radius: 50%; background: #ef4444; display: inline-block;"></span>
            <span style="width: 10px; height: 10px; border-radius: 50%; background: #eab308; display: inline-block;"></span>
            <span style="width: 10px; height: 10px; border-radius: 50%; background: #22c55e; display: inline-block;"></span>
            <span style="font-size: 13px; font-weight: 600; color: #475569; margin-left: 10px;"> | </span>
        </div>
        <div>
            <a href="https://debeatzgh1.github.io/Home-/" target="_blank" style="font-size: 12px; font-weight: 600; color: #2563eb; text-decoration: none; padding: 6px 12px; border-radius: 6px; background: #eff6ff; transition: all 0.2s;" onmouseover="this.style.background='#dbeafe'" onmouseout="this.style.background='#eff6ff'">
                Open Native Page <span style="font-size: 10px; margin-left: 2px;">↗</span>
            </a>
        </div>
    </div>

    <!-- Active Sandbox Viewport -->
    <div style="position: relative; width: 100%; height: 750px; background: #f1f5f9;">
        <!-- CSS-Only Spinner (Hidden automatically once iframe mounts content threads) -->
        <div id="dbz-embed-loader" style="position: absolute; inset: 0; display: flex; flex-direction: column; align-items: center; justify-content: center; background: #ffffff; z-index: 5;">
            <div style="width: 40px; height: 40px; border: 3px solid #cbd5e1; border-top-color: #2563eb; border-radius: 50%; animation: dbz-spin 0.8s linear infinite;"></div>
            <p style="margin-top: 12px; font-size: 13px; color: #64748b; font-weight: 500;">Establishing portal attachment...</p>
        </div>

        <!-- Embedded Frame Target Node -->
        <iframe 
            src="https://msha.ke/debeatzgh#links-1" 
            style="width: 120%; height: 120%; border: none; opacity: 0; transition: opacity 0.3s ease;" 
            allow="geolocation; microphone; camera; midi; encrypted-media;"
            sandbox="allow-forms allow-modals allow-popups allow-scripts allow-same-origin allow-top-navigation-by-user-activation"
            onload="document.getElementById('dbz-embed-loader').style.display='none'; this.style.opacity='1';">
        </iframe>
    </div>
</div>

<!-- Essential Animation Styles Definition -->
<style>
    @keyframes dbz-spin {
        to { transform: rotate(360deg); }
    }
</style>







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
#viewer iframe{width:100%;height:100%;border:none}

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
  top:30%;
  right:16px;
  transform:translateY(-50%);
  background:#ef4444;
  color:white;
  padding:12px 16px;
  border-radius:50%;
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
