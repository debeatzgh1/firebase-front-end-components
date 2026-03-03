
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --ui-accent: #00f2ff; /* Cyber Cyan */
            --ui-bg: rgba(10, 10, 12, 0.9);
            --ui-glow: rgba(0, 242, 255, 0.4);
            --text-light: #f0f6fc;
        }

        /* --- TOPMOST FLOATING BANNER --- */
        .ui-browser-banner {
            position: fixed;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
            width: 310px;
            height: 48px;
            background: var(--ui-bg);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid rgba(0, 242, 255, 0.2);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 8px 0 15px;
            z-index: 10001; /* Higher than other banners */
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.8), 0 0 10px var(--ui-glow);
            overflow: hidden;
        }

        /* Auto-Slide Text Container */
        .ui-slider-box {
            flex: 1;
            overflow: hidden;
            position: relative;
            height: 20px;
            margin-right: 10px;
        }

        .ui-slider-content {
            display: flex;
            flex-direction: column;
            animation: slideText 6s cubic-bezier(0.645, 0.045, 0.355, 1) infinite;
        }

        .ui-slider-content span {
            height: 20px;
            font-family: 'Monaco', 'Consolas', monospace;
            font-size: 0.75rem;
            color: var(--ui-accent);
            display: flex;
            align-items: center;
            gap: 6px;
            letter-spacing: 1px;
            font-weight: bold;
        }

        /* Action Button */
        .ui-open-btn {
            background: var(--ui-accent);
            color: #000;
            border: none;
            padding: 6px 14px;
            border-radius: 6px;
            font-size: 0.7rem;
            font-weight: 900;
            cursor: pointer;
            text-transform: uppercase;
            transition: 0.3s ease;
            display: flex;
            align-items: center;
            gap: 4px;
        }

        .ui-open-btn:hover {
            background: #fff;
            box-shadow: 0 0 15px #fff;
            transform: scale(1.05);
        }

        /* --- OVERLAY IFRAME --- */
        #ui-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.95);
            display: none;
            flex-direction: column;
            z-index: 20000;
            animation: overlayFade 0.4s ease;
        }

        .ui-overlay-nav {
            height: 50px;
            background: #111;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 20px;
            border-bottom: 2px solid var(--ui-accent);
        }

        .ui-frame {
            width: 100%;
            flex-grow: 1;
            border: none;
            background: #fff;
        }

        /* --- ANIMATIONS --- */
        @keyframes slideText {
            0%, 20% { transform: translateY(0); }
            33%, 53% { transform: translateY(-20px); }
            66%, 86% { transform: translateY(-40px); }
            100% { transform: translateY(0); }
        }

        @keyframes overlayFade {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .pulse-icon {
            width: 6px;
            height: 6px;
            background: var(--ui-accent);
            border-radius: 50%;
            box-shadow: 0 0 8px var(--ui-accent);
        }
    </style>
</head>
<body>

    <div class="ui-browser-banner">
        <div class="ui-slider-box">
            <div class="ui-slider-content">
                <span><div class="pulse-icon"></div> Browse UI & Interfaces</span>
                <span><div class="pulse-icon"></div> Discover Experience</span>
                <span><div class="pulse-icon"></div> Portfolio Access</span>
            </div>
        </div>
        <button class="ui-open-btn" onclick="openUIHub()">
            Explore <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
        </button>
    </div>

    <div id="ui-overlay">
        <div class="ui-overlay-nav">
            <span style="color: var(--ui-accent); font-family: monospace; font-weight: bold; font-size: 0.8rem;">DEBEATZGH // UI_INTERFACES</span>
            <button onclick="closeUIHub()" style="background:none; border: 1px solid #444; color: #888; padding: 4px 12px; cursor: pointer; border-radius: 4px; font-size: 0.7rem;">CLOSE [ESC]</button>
        </div>
        <iframe class="ui-frame" id="ui-iframe"></iframe>
    </div>

    <script>
        const uiOverlay = document.getElementById('ui-overlay');
        const uiIframe = document.getElementById('ui-iframe');

        function openUIHub() {
            uiIframe.src = "https://form.svhrt.com/60f4a0aeedc1993c8c7b3989";
            uiOverlay.style.display = 'flex';
            document.body.style.overflow = 'hidden';
        }

        function closeUIHub() {
            uiOverlay.style.display = 'none';
            uiIframe.src = "";
            document.body.style.overflow = 'auto';
        }

        // Close on Escape key
        document.addEventListener('keydown', (e) => {
            if (e.key === "Escape") closeUIHub();
        });
    </script>
</body>
</html>




<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Debeatzgh Digital Hub</title>

<style>
:root{
  --primary:#2563eb;
  --secondary:#16a34a;
  --dark:#020617;
}
body{margin:0;font-family:system-ui,Arial,sans-serif}

/* Floating launcher */
#dbz-launcher{
  position:fixed;
  right:16px;
  top:50%;
  transform:translateY(-50%);
  width:48px;height:48px;
  background:var(--primary);
  color:#fff;
  border-radius:50%;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:20px;
  cursor:pointer;
  z-index:99999;
  box-shadow:0 8px 24px rgba(0,0,0,.35);
}

/* Overlay */
#dbz-overlay{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.85);
  display:none;
  z-index:99998;
}

/* App box */
#dbz-box{
  position:absolute;
  inset:16px;
  background:#fff;
  border-radius:18px;
  display:flex;
  flex-direction:column;
  overflow:hidden;
}

/* Header */
#dbz-header{
  background:linear-gradient(135deg,var(--primary),var(--secondary));
  color:#fff;
  padding:12px 16px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}
#dbz-controls span{
  margin-left:12px;
  cursor:pointer;
  font-size:18px;
}

/* Section tabs */
#dbz-sections{
  display:flex;
  gap:8px;
  padding:10px;
  background:#f1f5f9;
}
#dbz-sections button{
  border:none;
  padding:6px 14px;
  border-radius:999px;
  cursor:pointer;
  background:#e5e7eb;
  font-size:13px;
}
#dbz-sections button.active{
  background:var(--primary);
  color:#fff;
}

/* Section description */
#dbz-desc{
  padding:10px 16px;
  background:#f8fafc;
  font-size:13px;
  color:#475569;
}

/* Tabs */
#dbz-tabs{
  display:flex;
  gap:6px;
  padding:8px;
  background:#f1f5f9;
  overflow-x:auto;
}
#dbz-tabs button{
  border:none;
  padding:5px 12px;
  border-radius:999px;
  cursor:pointer;
  background:#e5e7eb;
  font-size:12px;
  white-space:nowrap;
}
#dbz-tabs button.active{
  background:var(--secondary);
  color:#fff;
}

/* Iframe */
#dbz-frame{
  flex:1;
  border:none;
}
</style>
</head>

<body>

<!-- Floating Button -->
<div id="dbz-launcher" title="Open Debeatzgh Hub">☰</div>

<!-- Overlay App -->
<div id="dbz-overlay">
  <div id="dbz-box">

    <div id="dbz-header">
      <strong>Digital Creators Hub</strong>
      <div id="dbz-controls">
        <span id="dbz-back">⟵</span>
        <span id="dbz-forward">⟶</span>
        <span id="dbz-full">⛶</span>
        <span id="dbz-close">✕</span>
      </div>
    </div>

    <div id="dbz-sections"></div>
    <div id="dbz-desc"></div>
    <div id="dbz-tabs"></div>

    <iframe id="dbz-frame"></iframe>

  </div>
</div>

<script>
/* ===================== DATA ===================== */
const SECTIONS = [
{
  title:"🚀 Core Platforms",
  desc:"Start here. These are the foundation tools to build your digital presence and income streams.",
  tabs:[
    ["Home","https://debeatzgh1.github.io/1/"],
    ["Blog","https://debeatzgh.wordpress.com/"],
    ["AI Chat","https://debeatzgh1.github.io/ai-chat/"],
    ["Tools Hub","https://debeatzgh1.github.io/Home-/"],
    ["WEBSITE","https://msha.ke/debeatzgh"]
  ]
},
{
  title:"🧩 Apps & Utilities",
  desc:"Interactive tools and widgets to boost productivity, creativity, and learning.",
  tabs:[
    ["Collaborators","https://debeatzgh1.github.io/Debeatzgh-Collaborators-Hub/"],
    ["AI Starter Kit","https://debeatzgh1.github.io/Decode-AI-starter-kit-/"],
    ["Productivity App","https://debeatzgh1.github.io/Improve-productivity-with-AI-Web-App-project-/"],
    ["Menu Widget","https://debeatzgh1.github.io/menu-widget-/"],
    ["Flashcards","https://debeatzgh1.github.io/Floating-Flashcards-Widget/"],
    ["Docs Carousel","https://debeatzgh1.github.io/Docs-Carousel-for-Blogger/"]
  ]
},
{
  title:"📚 Resource Vault",
  desc:"Everything in one place. Guides, business kits, games, posts, and monetization resources.",
  tabs:[
    ["Side Hustle Guide","https://debeatzgh1.github.io/The-Ultimate-Guide-to-Side-Hustle/"],
    ["Sales Strategies","https://debeatzgh1.github.io/sales/"],
    ["Online Business Kit","https://debeatzgh1.github.io/Online-business-kit/"],
    ["Games","https://debeatzgh1.github.io/games-/"],
    ["Posts","https://debeatzgh1.github.io/posts/"],
    ["Home Hub","https://debeatzgh1.github.io/Home-/"]
  ]
}
];

/* ===================== LOGIC ===================== */
const overlay=document.getElementById("dbz-overlay");
const frame=document.getElementById("dbz-frame");
const sectionsBox=document.getElementById("dbz-sections");
const tabsBox=document.getElementById("dbz-tabs");
const descBox=document.getElementById("dbz-desc");

document.getElementById("dbz-launcher").onclick=()=>overlay.style.display="block";
document.getElementById("dbz-close").onclick=()=>{
  overlay.style.display="none";
  frame.src="";
};

document.getElementById("dbz-back").onclick=()=>{try{frame.contentWindow.history.back()}catch(e){}};
document.getElementById("dbz-forward").onclick=()=>{try{frame.contentWindow.history.forward()}catch(e){}};
document.getElementById("dbz-full").onclick=()=>{
  const box=document.getElementById("dbz-box");
  !document.fullscreenElement ? box.requestFullscreen() : document.exitFullscreen();
};

function loadSection(i){
  sectionsBox.querySelectorAll("button").forEach(b=>b.classList.remove("active"));
  sectionsBox.children[i].classList.add("active");

  descBox.textContent=SECTIONS[i].desc;
  tabsBox.innerHTML="";

  SECTIONS[i].tabs.forEach((t,j)=>{
    const btn=document.createElement("button");
    btn.textContent=t[0];
    btn.onclick=()=>{
      frame.src=t[1];
      tabsBox.querySelectorAll("button").forEach(x=>x.classList.remove("active"));
      btn.classList.add("active");
    };
    if(j===0){
      btn.classList.add("active");
      frame.src=t[1];
    }
    tabsBox.appendChild(btn);
  });
}

SECTIONS.forEach((s,i)=>{
  const b=document.createElement("button");
  b.textContent=s.title;
  if(i===0)b.classList.add("active");
  b.onclick=()=>loadSection(i);
  sectionsBox.appendChild(b);
});

loadSection(0);
</script>

</body>
</html>
