<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="theme-color" content="#fff7f0" />
  <title>My Beautiful Family ❤️</title>

  <!-- Google Fonts: the site still works if the font service is unavailable -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet" />


  <style>
/* =========================================================
   My Beautiful Family — responsive family website
   ========================================================= */

:root {
  --bg: #fff8f2;
  --surface: rgba(255, 255, 255, 0.82);
  --surface-strong: #ffffff;
  --text: #2f2430;
  --muted: #776873;
  --accent: #c95867;
  --accent-deep: #9f3e50;
  --accent-soft: #f8dbe0;
  --gold: #d39b4a;
  --line: rgba(120, 75, 87, 0.12);
  --shadow: 0 24px 70px rgba(95, 49, 62, 0.14);
  --radius-xl: 32px;
  --radius-lg: 22px;
}

* {
  box-sizing: border-box;
}

html {
  min-height: 100%;
  scroll-behavior: smooth;
}

body {
  min-height: 100vh;
  margin: 0;
  overflow-x: hidden;
  color: var(--text);
  background:
    radial-gradient(circle at 15% 15%, rgba(247, 210, 217, 0.55), transparent 28%),
    radial-gradient(circle at 86% 18%, rgba(239, 224, 199, 0.55), transparent 28%),
    linear-gradient(145deg, #fffdf9 0%, var(--bg) 52%, #fff4f1 100%);
  font-family: "DM Sans", system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  display: flex;
  flex-direction: column;
}

button {
  font: inherit;
}

.ambient {
  position: fixed;
  z-index: 0;
  width: 340px;
  height: 340px;
  border-radius: 50%;
  filter: blur(8px);
  pointer-events: none;
  opacity: 0.28;
}

.ambient-one {
  top: -150px;
  left: -100px;
  background: #ffdfe5;
}

.ambient-two {
  right: -120px;
  bottom: -140px;
  background: #f5e3bf;
}

.site-header,
.family-shell,
.site-footer {
  position: relative;
  z-index: 1;
}

.site-header {
  width: min(1180px, calc(100% - 32px));
  margin: 0 auto;
  padding: 24px 0 10px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.brand {
  display: inline-flex;
  gap: 10px;
  align-items: center;
  font-weight: 700;
  letter-spacing: 0.01em;
  font-size: 1.05rem;
}

.brand-heart {
  color: var(--accent);
  font-size: 1.2rem;
}

.music-toggle {
  border: 1px solid rgba(109, 69, 83, 0.12);
  background: rgba(255, 255, 255, 0.65);
  color: var(--text);
  border-radius: 999px;
  padding: 10px 14px;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  transition: transform 180ms ease, box-shadow 180ms ease, background 180ms ease;
  backdrop-filter: blur(12px);
}

.music-toggle:hover {
  transform: translateY(-1px);
  box-shadow: 0 10px 26px rgba(71, 42, 54, 0.1);
  background: rgba(255, 255, 255, 0.9);
}

.music-toggle.is-on {
  color: #8f3a4e;
  box-shadow: inset 0 0 0 1px rgba(201, 88, 103, 0.1), 0 10px 26px rgba(201, 88, 103, 0.1);
}

.family-shell {
  width: min(980px, calc(100% - 30px));
  margin: 0 auto;
  padding: 34px 0 42px;
  flex: 1;
}

.hero {
  text-align: center;
  margin: 24px auto 32px;
}

.eyebrow {
  margin: 0 0 10px;
  color: var(--accent-deep);
  font-size: 0.78rem;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  font-weight: 700;
}

.hero h1 {
  margin: 0;
  font-family: "Playfair Display", Georgia, serif;
  font-size: clamp(2.35rem, 5.5vw, 4.55rem);
  line-height: 1.05;
  letter-spacing: -0.035em;
}

.subtitle {
  margin: 14px 0 0;
  color: var(--muted);
  font-size: clamp(1rem, 2vw, 1.15rem);
}

.family-viewer {
  position: relative;
  padding: 18px;
  border: 1px solid rgba(255, 255, 255, 0.76);
  border-radius: var(--radius-xl);
  background: rgba(255, 255, 255, 0.48);
  box-shadow: 0 15px 60px rgba(77, 45, 57, 0.07);
  backdrop-filter: blur(16px);
}

.viewer-topline,
.progress-label {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
}

.viewer-topline {
  padding: 2px 4px 12px;
}

.relationship-badge {
  display: inline-flex;
  align-items: center;
  padding: 8px 12px;
  border-radius: 999px;
  font-size: 0.78rem;
  font-weight: 700;
  color: var(--accent-deep);
  background: var(--accent-soft);
}

.page-number {
  font-size: 0.84rem;
  color: var(--muted);
  font-weight: 700;
}

.profile-card {
  position: relative;
  min-height: 470px;
  padding: 62px 34px 46px;
  overflow: hidden;
  border-radius: 28px;
  background:
    radial-gradient(circle at 50% 4%, rgba(255, 255, 255, 0.96), transparent 35%),
    linear-gradient(145deg, rgba(255,255,255,0.96), rgba(255,247,241,0.93));
  border: 1px solid rgba(255, 255, 255, 0.95);
  box-shadow: var(--shadow);
  display: grid;
  place-items: center;
  gap: 24px;
  text-align: center;
  isolation: isolate;
  transform: translateZ(0);
}

.profile-card.enter-next {
  animation: enterNext 520ms cubic-bezier(.2,.78,.18,1) both;
}

.profile-card.enter-prev {
  animation: enterPrev 520ms cubic-bezier(.2,.78,.18,1) both;
}

.profile-card.is-changing {
  animation: none;
}

@keyframes enterNext {
  0% { opacity: 0; transform: translateX(42px) scale(0.98); }
  100% { opacity: 1; transform: translateX(0) scale(1); }
}

@keyframes enterPrev {
  0% { opacity: 0; transform: translateX(-42px) scale(0.98); }
  100% { opacity: 1; transform: translateX(0) scale(1); }
}

.decor {
  position: absolute;
  font-size: 2.4rem;
  color: rgba(201, 88, 103, 0.14);
  z-index: -1;
}

.decor-left {
  top: 22px;
  left: 26px;
}

.decor-right {
  right: 26px;
  top: 18px;
}

.photo-wrap {
  position: relative;
}

.photo-ring {
  width: clamp(150px, 24vw, 196px);
  height: clamp(150px, 24vw, 196px);
  padding: 7px;
  position: relative;
  border-radius: 50%;
  background: linear-gradient(135deg, #ffffff, #efc6ce);
  box-shadow:
    0 16px 36px rgba(98, 55, 67, 0.14),
    inset 0 0 0 1px rgba(255,255,255,.65);
}

.member-image,
.photo-placeholder {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  display: block;
}

.member-image {
  object-fit: cover;
  background: #f5e8df;
}

.photo-placeholder {
  position: absolute;
  inset: 7px;
  width: calc(100% - 14px);
  height: calc(100% - 14px);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 2px;
  background:
    radial-gradient(circle at 50% 30%, #fff 0%, #f8e3df 36%, #efd2d7 100%);
  color: var(--accent-deep);
}

.photo-placeholder span:first-child {
  font-size: 2.1rem;
  opacity: 0.82;
}

.photo-placeholder span:last-child {
  font-size: 1.45rem;
  font-weight: 800;
  letter-spacing: 0.06em;
}

.family-icon {
  position: absolute;
  right: -10px;
  bottom: 0;
  width: 54px;
  height: 54px;
  border-radius: 50%;
  border: 5px solid white;
  background: #fbebdd;
  box-shadow: 0 8px 22px rgba(88, 54, 65, 0.12);
  display: grid;
  place-items: center;
  font-size: 1.25rem;
}

.profile-copy {
  max-width: 680px;
}

.profile-kicker {
  margin: 0 0 9px;
  color: var(--gold);
  font-size: 0.77rem;
  text-transform: uppercase;
  letter-spacing: 0.14em;
  font-weight: 800;
}

.profile-copy h2 {
  margin: 0;
  font-family: "Playfair Display", Georgia, serif;
  font-size: clamp(2rem, 4vw, 3.15rem);
  letter-spacing: -0.025em;
}

.member-description {
  margin: 15px auto 0;
  max-width: 560px;
  color: var(--muted);
  line-height: 1.8;
  font-size: 1rem;
}

.card-glow {
  position: absolute;
  left: 50%;
  bottom: -160px;
  width: 440px;
  height: 280px;
  transform: translateX(-50%);
  background: radial-gradient(circle, rgba(201, 88, 103, 0.12), transparent 68%);
  pointer-events: none;
  z-index: -1;
}

.navigation {
  display: flex;
  justify-content: center;
  gap: 12px;
  flex-wrap: wrap;
  padding: 22px 4px 10px;
}

.nav-button {
  border: none;
  min-width: 138px;
  padding: 13px 18px;
  border-radius: 999px;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 9px;
  font-weight: 800;
  transition: transform 180ms ease, box-shadow 180ms ease, opacity 180ms ease, background 180ms ease;
}

.nav-button:hover:not(:disabled) {
  transform: translateY(-2px);
}

.nav-button.primary {
  color: white;
  background: linear-gradient(135deg, var(--accent), var(--accent-deep));
  box-shadow: 0 13px 26px rgba(169, 63, 80, 0.23);
}

.nav-button.primary:hover:not(:disabled) {
  box-shadow: 0 18px 32px rgba(169, 63, 80, 0.29);
}

.nav-button.secondary {
  color: var(--text);
  background: rgba(255,255,255,0.82);
  border: 1px solid rgba(91, 55, 68, 0.11);
  box-shadow: 0 9px 20px rgba(81, 47, 61, 0.06);
}

.nav-button:disabled {
  cursor: not-allowed;
  opacity: 0.45;
  transform: none;
  box-shadow: none;
}

.hidden {
  display: none !important;
}

.progress-area {
  padding: 10px 4px 4px;
}

.progress-label {
  margin-bottom: 8px;
  color: var(--muted);
  font-size: 0.76rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.09em;
}

.progress-track {
  height: 8px;
  width: 100%;
  overflow: hidden;
  border-radius: 999px;
  background: rgba(120, 77, 88, 0.10);
}

.progress-bar {
  width: 16.667%;
  height: 100%;
  border-radius: inherit;
  background: linear-gradient(90deg, #e4909c, var(--accent));
  transition: width 400ms cubic-bezier(.2,.78,.18,1);
}

.progress-dots {
  display: flex;
  justify-content: center;
  gap: 8px;
  padding-top: 13px;
}

.progress-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #dbcfd2;
  transition: all 240ms ease;
}

.progress-dot.active {
  width: 26px;
  border-radius: 999px;
  background: var(--accent);
}

.quote {
  margin: 28px auto 0;
  max-width: 700px;
  color: #6e5a63;
  text-align: center;
  font-family: "Playfair Display", Georgia, serif;
  font-size: 1.02rem;
}

.quote span {
  color: var(--accent);
}

.site-footer {
  padding: 18px 16px 26px;
  text-align: center;
  color: var(--muted);
  font-size: 0.86rem;
}

.site-footer span {
  color: var(--accent);
}

@media (max-width: 680px) {
  .site-header {
    width: min(100% - 20px, 1180px);
    padding-top: 16px;
  }

  .music-toggle {
    padding: 9px 11px;
    font-size: 0.78rem;
  }

  .family-shell {
    width: min(100% - 16px, 980px);
    padding-top: 20px;
  }

  .hero {
    margin: 12px auto 22px;
  }

  .profile-card {
    min-height: 500px;
    padding: 50px 20px 34px;
  }

  .family-viewer {
    padding: 11px;
    border-radius: 24px;
  }

  .navigation {
    gap: 9px;
  }

  .nav-button {
    min-width: 128px;
  }
}

@media (max-width: 430px) {
  .brand {
    font-size: 0.96rem;
  }

  .music-toggle span:last-child {
    display: none;
  }

  .profile-card {
    min-height: 490px;
  }

  .member-description {
    font-size: 0.95rem;
    line-height: 1.7;
  }

  .navigation {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  .nav-button {
    width: 100%;
    min-width: 0;
  }

  .nav-button.primary.hidden {
    grid-column: 1 / -1;
  }
}

@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }

  *,
  *::before,
  *::after {
    animation-duration: 1ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 1ms !important;
  }
}

  </style>
</head>
<body>
  <div class="ambient ambient-one" aria-hidden="true"></div>
  <div class="ambient ambient-two" aria-hidden="true"></div>

  <header class="site-header">
    <div class="brand">
      <span class="brand-heart" aria-hidden="true">♥</span>
      <span>My Family</span>
    </div>

    <button
      id="musicToggle"
      class="music-toggle"
      type="button"
      aria-pressed="false"
      aria-label="Turn background music on or off"
      title="Background music is off"
    >
      <span id="musicIcon" aria-hidden="true">♫</span>
      <span id="musicText">Music Off</span>
    </button>
  </header>

  <main class="family-shell">
    <section class="hero" aria-labelledby="pageTitle">
      <p class="eyebrow">A little place for the people I love</p>
      <h1 id="pageTitle">My Beautiful Family <span aria-hidden="true">❤️</span></h1>
      <p class="subtitle">My Family, My Strength, My World</p>
    </section>

    <section class="family-viewer" aria-live="polite" aria-atomic="true">
      <div class="viewer-topline">
        <span id="relationshipBadge" class="relationship-badge">Father</span>
        <span id="pageNumber" class="page-number">1 / 6</span>
      </div>

      <div id="profileCard" class="profile-card">
        <div class="decor decor-left" aria-hidden="true">✦</div>
        <div class="decor decor-right" aria-hidden="true">♡</div>

        <div class="photo-wrap">
          <div class="photo-ring">
            <img id="memberImage" class="member-image" src="" alt="" />
            <div id="photoPlaceholder" class="photo-placeholder" aria-hidden="true">
              <span id="placeholderIcon">❤</span>
              <span id="placeholderInitials">RV</span>
            </div>
          </div>
          <div id="familyIcon" class="family-icon" aria-hidden="true">👨‍👩‍👧‍👦</div>
        </div>

        <div class="profile-copy">
          <p class="profile-kicker" id="profileKicker">The heart of our home</p>
          <h2 id="memberName">Ram Naval Vishwakarma</h2>
          <p id="memberDescription" class="member-description">
            A beloved part of our family and a source of love, guidance, and strength.
          </p>
        </div>

        <div class="card-glow" aria-hidden="true"></div>
      </div>

      <div class="navigation">
        <button id="prevButton" class="nav-button secondary" type="button">
          <span aria-hidden="true">←</span>
          Previous
        </button>

        <button id="nextButton" class="nav-button primary" type="button">
          Next
          <span aria-hidden="true">→</span>
        </button>

        <button id="restartButton" class="nav-button primary hidden" type="button">
          Start Again
          <span aria-hidden="true">↻</span>
        </button>
      </div>

      <div class="progress-area">
        <div class="progress-label">
          <span>Family Journey</span>
          <span id="progressPercent">17%</span>
        </div>
        <div class="progress-track" aria-hidden="true">
          <div id="progressBar" class="progress-bar"></div>
        </div>
        <div id="dots" class="progress-dots" aria-label="Family member progress"></div>
      </div>
    </section>

    <p class="quote">
      “The love of a family is life’s greatest blessing.” <span aria-hidden="true">♥</span>
    </p>
  </main>

  <footer class="site-footer">Made with <span aria-hidden="true">❤️</span> for My Family</footer>


  <script>
/* =========================================================
   My Beautiful Family — page navigation + optional music
   ========================================================= */

const familyMembers = [
  {
    relationship: "Father",
    name: "Ram Naval Vishwakarma",
    description:
      "A beloved part of our family and a source of love, guidance, and strength.",
    kicker: "The heart of our home",
    initials: "RV",
    icon: "👨",
    image: "images/father.jpg"
  },
  {
    relationship: "Mother",
    name: "Reeta Devi",
    description:
      "A loving presence whose care, warmth, and blessings make our family feel complete.",
    kicker: "The warmth of our home",
    initials: "RD",
    icon: "👩",
    image: "images/mother.jpg"
  },
  {
    relationship: "Brother",
    name: "Sanjay Vishwakarma",
    description:
      "He is my backbone and one of the strongest pillars of my life.",
    kicker: "My strength beside me",
    initials: "SV",
    icon: "🤝",
    image: "images/brother-sanjay.jpg"
  },
  {
    relationship: "Sister",
    name: "Nikita Vishwakarma",
    description:
      "She is also very special to me and an important part of my family.",
    kicker: "A special part of my world",
    initials: "NV",
    icon: "🌸",
    image: "images/sister-nikita.jpg"
  },
  {
    relationship: "Bhabhi",
    name: "Vandana Vishwakarma",
    description:
      "A cherished member of our family who adds love, care, and togetherness to our home.",
    kicker: "Love that grows a family",
    initials: "VV",
    icon: "💐",
    image: "images/bhabhi-vandana.jpg"
  },
  {
    relationship: "Elder Brother’s Son",
    name: "Satvik Vishwakarma",
    description:
      "A precious young member of our family who brings joy, smiles, and beautiful memories.",
    kicker: "A little joy in the family",
    initials: "SV",
    icon: "🧸",
    image: "images/satvik.jpg"
  }
];

let currentIndex = 0;
let isAnimating = false;

// DOM references
const profileCard = document.getElementById("profileCard");
const relationshipBadge = document.getElementById("relationshipBadge");
const pageNumber = document.getElementById("pageNumber");
const memberName = document.getElementById("memberName");
const memberDescription = document.getElementById("memberDescription");
const profileKicker = document.getElementById("profileKicker");
const memberImage = document.getElementById("memberImage");
const photoPlaceholder = document.getElementById("photoPlaceholder");
const placeholderInitials = document.getElementById("placeholderInitials");
const familyIcon = document.getElementById("familyIcon");
const progressPercent = document.getElementById("progressPercent");
const progressBar = document.getElementById("progressBar");
const dots = document.getElementById("dots");
const prevButton = document.getElementById("prevButton");
const nextButton = document.getElementById("nextButton");
const restartButton = document.getElementById("restartButton");

// Build progress dots once
familyMembers.forEach((_, index) => {
  const dot = document.createElement("span");
  dot.className = "progress-dot";
  dot.setAttribute("aria-hidden", "true");
  dots.appendChild(dot);
});

function updateDots() {
  [...dots.children].forEach((dot, index) => {
    dot.classList.toggle("active", index === currentIndex);
  });
}

function setProfile(member, direction = "next") {
  relationshipBadge.textContent = member.relationship;
  pageNumber.textContent = `${currentIndex + 1} / ${familyMembers.length}`;
  memberName.textContent = member.name;
  memberDescription.textContent = member.description;
  profileKicker.textContent = member.kicker;
  familyIcon.textContent = member.icon;
  placeholderInitials.textContent = member.initials;

  // Image replacement is intentionally simple:
  // put your real photo at the matching path inside /images.
  memberImage.alt = `${member.relationship} - ${member.name}`;
  memberImage.src = member.image;

  // If the image is missing, the elegant placeholder remains visible.
  memberImage.onload = () => {
    memberImage.style.display = "block";
    photoPlaceholder.style.display = "none";
  };

  memberImage.onerror = () => {
    memberImage.style.display = "none";
    photoPlaceholder.style.display = "flex";
  };

  const percent = ((currentIndex + 1) / familyMembers.length) * 100;
  progressPercent.textContent = `${Math.round(percent)}%`;
  progressBar.style.width = `${percent}%`;

  prevButton.disabled = currentIndex === 0;
  nextButton.classList.toggle("hidden", currentIndex === familyMembers.length - 1);
  restartButton.classList.toggle("hidden", currentIndex !== familyMembers.length - 1);

  updateDots();

  // Re-trigger entrance animation
  profileCard.classList.remove("enter-next", "enter-prev");
  void profileCard.offsetWidth;
  profileCard.classList.add(direction === "prev" ? "enter-prev" : "enter-next");
}

function changeMember(newIndex, direction) {
  if (
    isAnimating ||
    newIndex < 0 ||
    newIndex >= familyMembers.length ||
    newIndex === currentIndex
  ) {
    return;
  }

  isAnimating = true;
  profileCard.classList.remove("enter-next", "enter-prev");

  // Brief fade/slide out, then update content.
  profileCard.animate(
    [
      { opacity: 1, transform: `translateX(0) scale(1)` },
      { opacity: 0, transform: `translateX(${direction === "next" ? "-34px" : "34px"}) scale(.985)` }
    ],
    {
      duration: 220,
      easing: "ease-in",
      fill: "forwards"
    }
  ).onfinish = () => {
    currentIndex = newIndex;
    setProfile(familyMembers[currentIndex], direction);

    profileCard.animate(
      [
        {
          opacity: 0,
          transform: `translateX(${direction === "next" ? "34px" : "-34px"}) scale(.985)`
        },
        { opacity: 1, transform: "translateX(0) scale(1)" }
      ],
      {
        duration: 330,
        easing: "cubic-bezier(.2,.78,.18,1)",
        fill: "both"
      }
    ).onfinish = () => {
      isAnimating = false;
    };
  };
}

function nextMember() {
  changeMember(currentIndex + 1, "next");
}

function previousMember() {
  changeMember(currentIndex - 1, "prev");
}

function restart() {
  if (isAnimating) return;
  currentIndex = 0;
  setProfile(familyMembers[currentIndex], "prev");
  window.scrollTo({ top: 0, behavior: "smooth" });
}

nextButton.addEventListener("click", nextMember);
prevButton.addEventListener("click", previousMember);
restartButton.addEventListener("click", restart);

// Keyboard navigation
document.addEventListener("keydown", (event) => {
  if (event.key === "ArrowRight") nextMember();
  if (event.key === "ArrowLeft") previousMember();
  if (event.key === "Home") restart();
});

/* ---------------------------------------------------------
   Background music
   OFF by default.
   We create a very soft ambient loop in the browser using
   the Web Audio API, so no external audio file is required.
   --------------------------------------------------------- */

let audioContext = null;
let masterGain = null;
let musicTimer = null;
let musicOn = false;
let step = 0;

const musicToggle = document.getElementById("musicToggle");
const musicIcon = document.getElementById("musicIcon");
const musicText = document.getElementById("musicText");

const notes = [261.63, 329.63, 392.0, 329.63, 293.66, 349.23, 440.0, 349.23];

function playSoftNote(frequency, startTime, duration = 1.5) {
  if (!audioContext || !masterGain) return;

  const oscillator = audioContext.createOscillator();
  const gain = audioContext.createGain();

  oscillator.type = "sine";
  oscillator.frequency.setValueAtTime(frequency, startTime);

  gain.gain.setValueAtTime(0.0001, startTime);
  gain.gain.exponentialRampToValueAtTime(0.035, startTime + 0.18);
  gain.gain.exponentialRampToValueAtTime(0.0001, startTime + duration);

  oscillator.connect(gain);
  gain.connect(masterGain);

  oscillator.start(startTime);
  oscillator.stop(startTime + duration + 0.05);
}

function startMusic() {
  if (musicOn) return;

  audioContext = audioContext || new (window.AudioContext || window.webkitAudioContext)();
  if (audioContext.state === "suspended") audioContext.resume();

  masterGain = masterGain || audioContext.createGain();
  // Reset the gain so music works again after being switched off.
  masterGain.gain.cancelScheduledValues(audioContext.currentTime);
  masterGain.gain.setValueAtTime(0.7, audioContext.currentTime);
  if (!masterGain.__connected) {
    masterGain.connect(audioContext.destination);
    masterGain.__connected = true;
  }

  musicOn = true;
  musicText.textContent = "Music On";
  musicIcon.textContent = "♫";
  musicToggle.classList.add("is-on");
  musicToggle.setAttribute("aria-pressed", "true");
  musicToggle.title = "Turn background music off";

  const loop = () => {
    if (!musicOn) return;
    const now = audioContext.currentTime;
    playSoftNote(notes[step % notes.length], now, 1.65);
    if (step % 4 === 0) {
      playSoftNote(notes[(step + 2) % notes.length] / 2, now + 0.15, 1.8);
    }
    step += 1;
    musicTimer = window.setTimeout(loop, 1350);
  };

  loop();
}

function stopMusic() {
  musicOn = false;
  window.clearTimeout(musicTimer);
  musicTimer = null;
  musicText.textContent = "Music Off";
  musicIcon.textContent = "♫";
  musicToggle.classList.remove("is-on");
  musicToggle.setAttribute("aria-pressed", "false");
  musicToggle.title = "Turn background music on";

  if (masterGain && audioContext) {
    masterGain.gain.cancelScheduledValues(audioContext.currentTime);
    masterGain.gain.setTargetAtTime(0.0001, audioContext.currentTime, 0.08);
  }
}

musicToggle.addEventListener("click", () => {
  if (musicOn) stopMusic();
  else startMusic();
});

// Prevent unexpected missing-element errors if the script loads in an unusual environment.
window.addEventListener("load", () => {
  setProfile(familyMembers[currentIndex], "next");
});

  </script>
</body>
</html>
