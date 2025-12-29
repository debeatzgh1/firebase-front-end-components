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
      <strong>Debeatzgh Digital Hub</strong>
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
    ["Milkshake","https://msha.ke/debeatzgh"]
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
