<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Modern UI Carousel</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    .carousel-item { display: none; }
    .carousel-item.active { display: block; }
  </style>
</head>
<body class="bg-gray-100 min-h-screen flex flex-col items-center p-6">

  <h1 class="text-3xl font-bold mb-6 text-gray-800">Modern Professional UI Carousel</h1>

  <!-- Carousel Wrapper -->
  <div class="w-full max-w-2xl bg-white shadow-lg rounded-2xl p-6 relative">

    <!-- Carousel Items -->
    <div id="carousel">

      <!-- ITEM TEMPLATE SAMPLE -->
    </div>

    <!-- Controls -->
    <div class="flex justify-between mt-4">
      <button onclick="prevSlide()" class="px-4 py-2 bg-gray-700 text-white rounded-lg">Prev</button>
      <button onclick="nextSlide()" class="px-4 py-2 bg-blue-600 text-white rounded-lg">Next</button>
    </div>
  </div>

  <!-- Iframe Modal -->
  <div id="iframeModal" class="fixed inset-0 bg-black bg-opacity-70 hidden justify-center items-center p-4">
    <div class="bg-white w-full max-w-3xl h-[80vh] rounded-xl shadow-xl relative">
      <button onclick="closeIframe()" class="absolute -top-4 -right-4 bg-red-600 text-white w-10 h-10 rounded-full">✕</button>
      <iframe id="iframeViewer" src="" class="w-full h-full rounded-xl"></iframe>
    </div>
  </div>

<script>
const data = [
  {
    title: "AI Home Dashboard",
    desc: "Your central hub for all Debeatzgh AI tools and digital resources.",
    url: "https://debeatzgh1.github.io/Home-/"
  },
  {
    title: "Blogger Iframe Embed Generator",
    desc: "Easily generate professional iframe widgets for Blogger.",
    url: "https://debeatzgh1.github.io/Blogger-iframe-embed-generator/"
  },
  {
    title: "Docs Carousel for Blogger",
    desc: "A stylish rotating documentation carousel for blogs.",
    url: "https://debeatzgh1.github.io/Docs-Carousel-for-Blogger/"
  },
  {
    title: "Floating Dock Smart iFrame Modal",
    desc: "Modern floating dock UI for embedding smart iframe popups.",
    url: "https://debeatzgh1.github.io/-Floating-Dock-Smart-Iframe-Modal/"
  },
  {
    title: "Personal Portfolio Website",
    desc: "Showcase your creative work using a clean portfolio design.",
    url: "https://debeatzgh1.github.io/Personal-Portfolio-site-/"
  },
  {
    title: "Sliding Newsletter Signup Widget",
    desc: "Animated sliding widget that increases email signups.",
    url: "https://debeatzgh1.github.io/Sliding-Newsletter-Signup-Widget-with-Pulse-Animation/"
  },
  {
    title: "Digital Creator's Tools Library",
    desc: "An essential collection of tools and guides for digital creators.",
    url: "https://debeatzgh1.github.io/Digital-Creator-s-Essential-Guides-Tools/"
  },
  {
    title: "Floating Flashcards Widget",
    desc: "Interactive floating flashcards to improve user learning engagement.",
    url: "https://debeatzgh1.github.io/Floating-Flashcards-Widget/"
  },
  {
    title: "Blogger Product Carousel + WhatsApp Button",
    desc: "Promote products with a rotating carousel and WhatsApp CTA.",
    url: "https://debeatzgh1.github.io/Blogger-Product-Carousel-with-WhatsApp-Floating-Button/"
  },
  {
    title: "Firebase Login Popup UI",
    desc: "A modern popup login module powered by Firebase.",
    url: "https://debeatzgh1.github.io/-Firebase-Login-Popup/"
  }
];

let currentIndex = 0;

function renderCarousel() {
  const carousel = document.getElementById("carousel");
  carousel.innerHTML = data.map((item, index) => `
    <div class="carousel-item ${index === 0 ? 'active' : ''} text-center transition-all">
      <h2 class="text-2xl font-semibold text-gray-900 mb-2">${item.title}</h2>
      <p class="text-gray-600 mb-4">${item.desc}</p>
      <button onclick="openIframe('${item.url}')" class="px-5 py-2 bg-blue-600 text-white rounded-xl shadow hover:bg-blue-700">View in Iframe</button>
    </div>
  `).join("");
}

function showSlide(i) {
  const items = document.querySelectorAll('.carousel-item');
  items.forEach(item => item.classList.remove('active'));
  items[i].classList.add('active');
}

function nextSlide() {
  currentIndex = (currentIndex + 1) % data.length;
  showSlide(currentIndex);
}

function prevSlide() {
  currentIndex = (currentIndex - 1 + data.length) % data.length;
  showSlide(currentIndex);
}

function openIframe(url) {
  document.getElementById("iframeViewer").src = url;
  document.getElementById("iframeModal").classList.remove("hidden");
  document.getElementById("iframeModal").classList.add("flex");
}

function closeIframe() {
  document.getElementById("iframeModal").classList.add("hidden");
  document.getElementById("iframeViewer").src = "";
}

renderCarousel();
</script>

</body>
</html>



# 🚀 Firebase Curated Front-End Components

A curated collection of modern front-end components powered by **Firebase**, originally shared on the [Beatzde4 Blog](https://beatzde4.blogspot.com/p/firebase-curated-front-end-components.html). This project brings together login forms, authentication interfaces, and other Firebase-ready UI components in a lightweight and customizable format.
# 🚀 Firebase Curated Front-End Components

<p align="center">
  <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/07/screenshot_20250731-172746_12073168234250614551.png" alt="Firebase Front-End Components Preview" width="600"/>
</p>

A curated collection of modern front-end components powered by **Firebase**, originally shared on the [Beatzde4 Blog](https://beatzde4.blogspot.com/p/firebase-curated-front-end-components.html). This project brings together login forms, authentication interfaces, and other Firebase-ready UI components in a lightweight and customizable format.
---

## 📌 What's Inside

- ✅ Firebase Login UI
- 🔐 Firebase Email/Password Authentication
- 🌐 Responsive Forms
- 🎨 Minimalist HTML/CSS components
- ⚡ Firebase JS SDK Integration
- 🧩 Easily embeddable iframe or script-based UI blocks

---

## 📂 Project Structure
firebase-front-end-components/
├── index.html # Main Firebase login UI
├── style.css # Styles for UI components
├── app.js # Firebase setup and functions
├── firebase-config.js # Firebase credentials file
└── README.md # You're here!


---

## 🔧 Firebase Setup & Usage

1. **Clone the repo:**

```bash

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "your-app.firebaseapp.com",
  projectId: "your-app-id",
  storageBucket: "your-app.appspot.com",
  messagingSenderId: "SENDER_ID",
  appId: "APP_ID"
};

