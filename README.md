
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>G-Dev Portfolio | Hiring Portal</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Google+Sans:wght@400;500;700&display=swap');

        :root {
            --g-blue: #8ab4f8;
            --g-green: #34A853;
            --dark-bg: #1a1c1e;
            --dark-card: #2d2f31;
            --glass-border: rgba(255, 255, 255, 0.08);
        }

        body { font-family: 'Google Sans', sans-serif; background: #121212; margin: 0; }

        /* 1. LAUNCHER WITH ENTRANCE ANIMATION */
        #gdev-launcher {
            position: fixed; right: 20px; top: 90%; transform: translateY(-50%);
            display: flex; align-items: center; gap: 12px;
            background: var(--dark-card); padding: 8px 18px 8px 8px;
            border-radius: 40px; cursor: pointer; z-index: 9999;
            box-shadow: 0 10px 40px rgba(0,0,0,0.5);
            transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 1px solid var(--glass-border);
            animation: slide-wobble 1.2s ease forwards;
            opacity: 0;
        }

        @keyframes slide-wobble {
            0% { transform: translateY(-50%) translateX(-100px); opacity: 0; }
            60% { transform: translateY(-50%) translateX(10px); opacity: 1; }
            80% { transform: translateY(-50%) translateX(-2px); }
            100% { transform: translateY(-50%) translateX(0); opacity: 1; }
        }

        #gdev-launcher:hover { transform: translateY(-50%) scale(1.08) translateX(5px); border-color: var(--g-blue); }

        .dev-avatar {
            width: 20px; height: 20px; background: #121212; border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            border: 2px solid var(--g-blue); color: var(--g-blue); position: relative;
        }

        .status-dot {
            position: absolute; bottom: 2px; right: 2px; width: 10px; height: 10px;
            background: var(--g-green); border-radius: 50%; border: 2px solid var(--dark-card);
        }

        .status-glow {
            position: absolute; inset: 0; background: var(--g-green);
            border-radius: 50%; animation: status-pulse 2s infinite;
        }

        @keyframes status-pulse { 0% { transform: scale(1); opacity: 0.8; } 100% { transform: scale(2.5); opacity: 0; } }

        /* 2. OVERLAY MODAL */
        #gdev-overlay {
            position: fixed; inset: 0; background: rgba(0,0,0,0.85);
            backdrop-filter: blur(12px); display: none; z-index: 10000;
            justify-content: center; align-items: center; padding: 20px;
            opacity: 0; transition: opacity 0.4s ease;
        }

        #gdev-overlay.active { display: flex; opacity: 1; }

        .gdev-modal {
            width: 100%; max-width: 950px; height: 92vh;
            background: var(--dark-bg); border-radius: 28px;
            display: flex; flex-direction: column; overflow: hidden;
            border: 1px solid var(--glass-border); position: relative;
            transform: scale(0.9); transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        #gdev-overlay.active .gdev-modal { transform: scale(1); }

        /* 3. IFRAME & FOOTER */
        #gdev-frame { flex-grow: 1; width: 100%; border: none; background: #fff; }

        .close-gdev {
            position: absolute; top: 70px; right: 25px; width: 30px; height: 30px;
            background: var(--dark-card); border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            cursor: pointer; color: #fff; z-index: 20; transition: 0.3s;
        }
        .close-gdev:hover { background: #ff4d4d; }

        .hire-btn {
            background: var(--g-green); color: white; padding: 8px 18px;
            border-radius: 20px; font-size: 11px; font-weight: 800;
            text-transform: uppercase; letter-spacing: 1px; display: flex;
            align-items: center; gap: 8px; transition: 0.3s;
            box-shadow: 0 4px 15px rgba(52, 168, 83, 0.3);
        }
        .hire-btn:hover { transform: translateY(-2px); box-shadow: 0 6px 20px rgba(52, 168, 83, 0.4); background: #2e964a; }

        @media (max-width: 768px) {
            .gdev-modal { height: 100vh; border-radius: 0; }
            .footer-controls { flex-direction: column; gap: 10px; padding: 15px; }
        }
    </style>
</head>
<body>

    <div id="gdev-launcher" onclick="toggleGDev(true)">
        <div class="dev-avatar">
            <i class="fab fa-google"></i>
            <div class="status-dot"><div class="status-glow"></div></div>
        </div>
        <div class="hidden sm:block">
            <div class="flex items-center gap-2">
                <span class="text-[9px] text-[#34A853] font-bold uppercase tracking-widest">Active</span>
            </div>
            <p class="text-[14px] font-medium text-gray-200">@debeatzgh</p>
        </div>
    </div>

    <div id="gdev-overlay">
        <div class="gdev-modal">
            <div class="close-gdev" onclick="toggleGDev(true)"><i class="fas fa-times"></i></div>
            <iframe id="gdev-frame" src=""></iframe>
            <div class="footer-controls p-4 bg-[#1a1c1e] border-t border-white/5 flex justify-between items-center px-8">
                <span class="text-[9px] text-gray-600 font-bold uppercase tracking-[2px]">G-Dev Protocol v4.0</span>
                <div class="flex items-center gap-3">
                    <button id="copy-btn" class="text-[11px] text-[#8ab4f8] font-bold px-4 py-2 hover:text-white transition" onclick="copyProfileLink()">
                        Copy Profile
                    </button>
                    <a href="https://wa.me/233549757544" target="_blank" class="hire-btn">
                        <i class="fas fa-briefcase"></i> Contact Me
                    </a>
                </div>
            </div>
        </div>
    </div>

    <script>
        const overlay = document.getElementById('gdev-overlay');
        const frame = document.getElementById('gdev-frame');
        const profileUrl = "https://form.svhrt.com/60f4a0aeedc1993c8c7b3989";
        
        let autoPopTimer = null;
        let isUserInteracted = false;

        function toggleGDev(isManual = false) {
            // If user clicks, stop all automatic pop-ups/closings
            if (isManual) {
                isUserInteracted = true;
                clearTimeout(autoPopTimer);
            }

            if (overlay.classList.contains('active')) {
                overlay.classList.remove('active');
                setTimeout(() => { 
                    overlay.style.display = 'none'; 
                    frame.src = ""; 
                }, 400);
                document.body.style.overflow = 'auto';
            } else {
                overlay.style.display = 'flex';
                setTimeout(() => overlay.classList.add('active'), 10);
                frame.src = profileUrl;
                document.body.style.overflow = 'hidden';
            }
        }

        // --- AUTOMATIC ENGINE ---
        window.addEventListener('load', () => {
            // 1. Auto Open after 6 seconds
            autoPopTimer = setTimeout(() => {
                if (!isUserInteracted) {
                    toggleGDev();
                    
                    // 2. Auto Close after 6 more seconds
                    autoPopTimer = setTimeout(() => {
                        if (!isUserInteracted) toggleGDev();
                    }, 6000);
                }
            }, 6000);
        });

        async function copyProfileLink() {
            await navigator.clipboard.writeText(profileUrl);
            const btn = document.getElementById('copy-btn');
            btn.innerText = "Copied!";
            setTimeout(() => { btn.innerText = "Copy Profile"; }, 2000);
        }

        overlay.onclick = (e) => { if (e.target === overlay) toggleGDev(true); };
    </script>
</body>
</html>




<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sleek Floating Banner</title>
    <style>
        /* Modern CSS reset for consistency */
        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            min-height: 200vh; /* Adds scrollable height to visualize the fixed positioning */
            background-color: #121212; /* A dark, neutral background */
            color: #fff;
        }

        /* MAIN FLOATING BANNER CONTAINER
           Fixed to the top center of the screen
        */
        #sleek-floating-banner {
            position: fixed;
            top: 20px; /* Slight offset from the top border */
            left: 50%;
            transform: translateX(-50%); /* Centers horizontally */
            width: 340px; /* Compact, friendly width for desktop/mobile */
            height: 52px;
            background: rgba(30, 30, 30, 0.9); /* Dark semi-transparent background */
            backdrop-filter: blur(10px); /* Modern 'glassmorphism' effect */
            -webkit-backdrop-filter: blur(10px); /* Safari support */
            border: 1px solid rgba(255, 255, 255, 0.1); /* Subtle outline */
            border-radius: 50px; /* Fully rounded edges for a sleek pill look */
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5); /* Strong shadow for depth */
            display: flex;
            align-items: center;
            justify-content: space-between; /* Icon+Text on left, button on right */
            padding: 0 6px 0 16px; /* Optimized padding for the components */
            z-index: 10000; /* Ensures it stays above all other content */
            overflow: hidden; /* Needed for the marquee slide effect */
            
            /* Entry animation */
            animation: bannerEntry 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
            opacity: 0;
            transition: all 0.3s ease;
        }

        /* Hover effect to highlight the interactive nature */
        #sleek-floating-banner:hover {
            transform: translateX(-50%) scale(1.03);
            border-color: #FF1493; /* DeepPink border highlight on hover */
        }

        /* Banner entry animation (slides in and bounces slightly) */
        @keyframes bannerEntry {
            from { top: -60px; opacity: 0; }
            to { top: 20px; opacity: 1; }
        }

        /* --- MARQUEE SLIDER STYLES --- */
        .banner-text-slider {
            flex: 1;
            height: 22px; /* Set height to constrain the text */
            overflow: hidden; /* Masks text outside the area */
            position: relative;
            margin-right: 12px;
        }

        .slide-inner {
            display: flex;
            flex-direction: column; /* Stacks text vertically for sliding */
            animation: verticalSlide 8s cubic-bezier(0.645, 0.045, 0.355, 1) infinite;
        }

        /* Text element properties */
        .slide-inner span {
            height: 22px; /* Matches parent height */
            color: rgba(255, 255, 255, 0.9); /* Slightly off-white for better readability */
            font-size: 0.8rem;
            font-weight: 600; /* Semi-bold */
            display: flex;
            align-items: center;
            gap: 8px; /* Gap for the indicator dot */
            white-space: nowrap; /* Prevents text wrapping */
        }

        /* Color highlight for key inscriptions */
        .highlight-text {
            color: #FF1493; /* DeepPink */
        }

        /* Subtle animated dot for live status feel */
        .live-dot {
            width: 7px;
            height: 7px;
            background-color: #FF1493;
            border-radius: 50%;
            box-shadow: 0 0 10px rgba(255, 20, 147, 0.8);
            animation: pulseDot 1.5s infinite;
        }

        /* Pulse animation for the live dot */
        @keyframes pulseDot {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.3; transform: scale(1.2); }
        }

        /* Vertical Slide Keyframes:
           4 states (3 texts + return to 1). 
           Uses percentages to control pause duration at each state.
        */
        @keyframes verticalSlide {
            0%, 22% { transform: translateY(0); } /* Pauses on Text 1 */
            33%, 55% { transform: translateY(-22px); } /* Slides to and Pauses on Text 2 */
            66%, 88% { transform: translateY(-44px); } /* Slides to and Pauses on Text 3 */
            100% { transform: translateY(0); } /* Loops back to Text 1 smoothly */
        }

        /* --- BUTTON STYLES --- */
        .launch-btn {
            background-color: #FF1493; /* Vibrant DeepPink for main color */
            color: #fff;
            padding: 9px 20px;
            border-radius: 25px; /* Rounded pill style to match banner */
            font-size: 0.75rem;
            font-weight: 900; /* Extra bold text for contrast */
            border: none;
            cursor: pointer;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-decoration: none; /* Removes underline for <a> tags */
            display: flex;
            align-items: center;
            gap: 6px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 20, 147, 0.3); /* Soft DeepPink glow */
        }

        /* Button interaction effects */
        .launch-btn:hover {
            background-color: #ff50ac; /* Lighter DeepPink on hover */
            transform: translateY(-1px);
            box-shadow: 0 6px 20px rgba(255, 20, 147, 0.5); /* Stronger DeepPink glow */
        }

        .launch-btn:active {
            transform: translateY(1px) scale(0.98); /* Click interaction feedback */
        }

        /* --- SVG ICON STYLE --- */
        .arrow-icon {
            width: 13px;
            height: 13px;
            fill: none;
            stroke: currentColor; /* Matches text color (#fff) */
            stroke-width: 3;
            transition: transform 0.3s ease;
        }

        /* Hover animation specifically for the icon */
        .launch-btn:hover .arrow-icon {
            transform: translateX(3px); /* Arrow nudges right on hover */
        }
    </style>
</head>
<body>

    <div id="sleek-floating-banner" onclick="openHomeLink()">
        <div class="banner-text-slider">
            <div class="slide-inner">
                <span>
                    <div class="live-dot"></div> 
                    DeBeatz<span class="highlight-text">GH</span> Resource Hub
                </span>
                <span>
                    <div class="live-dot"></div>
                    Lifestyle <span class="highlight-text">&</span> Strategy
                </span>
                <span>
                    <div class="live-dot"></div>
                    Latest updates are <span class="highlight-text">Live</span>
                </span>
            </div>
        </div>

        <button class="launch-btn" onclick="openHomeLink(event)">
            OPEN 
            <svg class="arrow-icon" viewBox="0 0 24 24" aria-hidden="true">
                <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
        </button>
    </div>

    <script>
        /**
         * Opens the specified URL in a new tab without navigating
         * away from the current page.
         * @param {Event} e - Optional event object to prevent bubbling.
         */
        function openHomeLink(e) {
            // Check if event exists and stop propagation so clicking the button
            // doesn't also trigger the banner's onclick.
            if (e && e.stopPropagation) {
                e.stopPropagation();
            }
            
            // window.open(url, '_blank') opens in a new tab.
            window.open("https://debeatzgh1.github.io/Home-/", "_blank");
        }
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
