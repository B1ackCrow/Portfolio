<template>
  <section id="about" class="hero">
    <header class="hero-header">
      <div class="header-logo">
        DM
      </div>
      <nav class="header-navigation">
        <a href="#about" class="navigation-item">01. ABOUT</a>
        <a href="#projects" class="navigation-item">02. PROJECTS</a>
        <a href="#what-i-do" class="navigation-item">03. WHAT I DO</a>
        <a href="#tech-stack" class="navigation-item">04. TECH STACK</a>
        <a href="#contact" class="navigation-item">05. CONTACT</a>
      </nav>
    </header>
    <div class="hero-body">
      <div class="hero-content">
        <p class="hero-position">
          FULL-STACK DEVELOPER
        </p>
        <h1 class="hero-title">
          DENIS<br>MALYY
        </h1>
        <a href="#projects" class="view-work">
          <span class="view-work-icon">
            →
          </span>
          <span class="view-work-title">
            VIEW WORKS
          </span>
        </a>
      </div>
      <div class="hero-image">
        <img src="../assets/images/hero.jpg" alt="Denis Malyy"/>
      </div>
      <aside class="hero-info">
        <div class="hero-info__group">
          <span class="hero-info__label">01 / STACK</span>

          <ul class="hero-info__list">
            <li>C# / .NET</li>
            <li>POSTGRESQL</li>
            <li>VUE.JS</li>
            <li>SWIFT</li>
          </ul>
        </div>

        <div class="hero-info__group">
          <span class="hero-info__label">02 / FOCUS</span>

          <ul class="hero-info__list">
            <li>WEB APPLICATIONS</li>
            <li>BACKEND SYSTEMS</li>
            <li>API & DATABASES</li>
          </ul>
        </div>

        <div class="hero-info__group">
          <span class="hero-info__label">03 / ALSO</span>

          <ul class="hero-info__list">
            <li>iOS APPLICATIONS</li>
            <li>UI / UX DESIGN</li>
            <li>LANDING PAGES</li>
          </ul>
        </div>

        <div class="hero-info__group">
          <span class="hero-info__label">04 / WORK</span>

          <ul class="hero-info__list">
            <li>FULL-TIME</li>
            <li>CONTRACT</li>
            <li>REMOTE</li>
          </ul>
        </div>
      </aside>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
/* =========================
   HEADER
   ========================= */

.hero {
  position: relative;

  width: 100%;
  min-height: 100vh;

  padding: 0 var(--page-padding);

  background: var(--color-background);
  color: var(--color-text);
}

.hero-header {
  position: absolute;
  z-index: 10;

  top: 0;
  left: var(--page-padding);
  right: var(--page-padding);

  height: 100px;

  display: flex;
  align-items: center;
  gap: 100px;

  color: white;
  mix-blend-mode: difference;
}

.header-logo {
  font-family: var(--font-main);
  font-size: 24px;
  font-weight: 800;
  letter-spacing: -0.08em;
}

.header-navigation {
  display: flex;
  align-items: center;
  gap: 32px;
}

.navigation-item {
  font-family: var(--font-main);
  font-size: 12px;
  font-weight: 400;
  letter-spacing: 0.04em;

  opacity: 0.55;

  transition: opacity 0.2s ease;
}

.navigation-item:hover {
  opacity: 1;
}


/* =========================
   HERO BODY
   ========================= */

.hero-body {
  display: grid;
  grid-template-columns: 46% 39% 15%;

  min-height: 100vh;
}


/* =========================
   LEFT CONTENT
   ========================= */

.hero-content {
  display: flex;
  flex-direction: column;
  justify-content: center;

  padding-right: 40px;
}

.hero-position {
  position: relative;

  margin: 0 0 24px 4px;
  padding-top: 20px;

  font-family: var(--font-main);
  font-size: 12px;
  font-weight: 400;

  letter-spacing: 0.16em;

  color: var(--color-text-secondary);
}

.hero-position::before {
  content: '';

  position: absolute;
  top: 0;
  left: 0;

  width: 22px;
  height: 1px;

  background: var(--color-text);
}


/* =========================
   TITLE
   ========================= */

.hero-title {
  margin: 0;

  font-family: var(--font-main);
  font-size: clamp(80px, 10vw, 200px);
  font-weight: 800;

  line-height: 0.85;
  letter-spacing: -0.04em;

  transform: scaleY(1.12);
  transform-origin: left center;
}


/* =========================
   VIEW WORK
   ========================= */

.view-work {
  width: fit-content;

  display: flex;
  align-items: center;
  gap: 16px;

  margin-top: 55px;

  font-family: var(--font-main);
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.06em;
}

.view-work-icon {
  width: 48px;
  height: 48px;

  display: flex;
  align-items: center;
  justify-content: center;

  border: 1px solid var(--color-text);
  border-radius: 50%;

  font-size: 20px;

  transition:
      background 0.25s ease,
      color 0.25s ease,
      transform 0.25s ease;
}

.view-work:hover .view-work-icon {
  background: var(--color-text);
  color: var(--color-background);

  transform: translateX(4px);
}


/* =========================
   IMAGE
   ========================= */

.hero-image {
  height: 100vh;

  overflow: hidden;
}

.hero-image img {
  display: block;

  width: 100%;
  height: 100%;

  object-fit: cover;
  object-position: center;
}

/* =========================
   INFO
   ========================= */

.hero-info {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 90px;

  padding-left: 32px;
}

.hero-info__group {
  position: relative;

  padding-left: 18px;
}

.hero-info__group::before {
  content: '';

  position: absolute;
  top: 0;
  left: 0;

  width: 1px;
  height: 100%;

  background: var(--color-border);
}

.hero-info__label {
  display: block;

  margin-bottom: 18px;

  color: var(--color-text-secondary);

  font-size: 12px;
  font-weight: 500;
  letter-spacing: 0.12em;
}

.hero-info__list {
  display: flex;
  flex-direction: column;

  margin: 0;
  padding: 0;

  list-style: none;
}

.hero-info__list li {
  color: var(--color-text-secondary);

  font-size: 14px;
  font-weight: 300;
  line-height: 1.55;
  letter-spacing: 0.02em;
}
/* =========================
   TABLET
   ========================= */

/* =========================
   TABLET
   ========================= */

@media (min-width: 701px) and (max-width: 1200px) {
  .hero {
    min-height: 100svh;
    padding: 0;
  }


  /* HEADER */

  .hero-header {
    left: 32px;
    right: 32px;

    height: 80px;
    gap: 50px;
  }

  .header-logo {
    flex-shrink: 0;

    font-size: 22px;
  }

  .header-navigation {
    gap: 22px;
  }

  .navigation-item {
    font-size: 9px;
    white-space: nowrap;
  }


  /* BODY */

  .hero-body {
    display: grid;

    grid-template-columns: 46% 54%;
    grid-template-rows: 100svh auto;

    min-height: auto;
  }


  /* MAIN CONTENT */

  .hero-content {
    justify-content: center;
    min-width: 0;

    padding-left: 32px;
    padding-right: 30px;
  }

  .hero-position {
    margin-bottom: 20px;

    font-size: 9px;
  }

  .hero-title {
    font-size: clamp(68px, 9vw, 92px);

    line-height: 0.82;
  }

  .view-work {
    margin-top: 42px;

    font-size: 9px;
  }

  .view-work-icon {
    width: 44px;
    height: 44px;
  }


  /* IMAGE */

  .hero-image {
    width: 100%;
    height: 100svh;
  }

  .hero-image img {
    object-position: center;
  }


  /* INFO */

  .hero-info {
    grid-column: 1 / -1;

    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));

    gap: 30px;

    padding: 45px 0 50px;

    display: none;
  }

  .hero-info__group {
    padding-left: 14px;
  }

  .hero-info__label {
    margin-bottom: 14px;

    font-size: 9px;
  }

  .hero-info__list li {
    font-size: 11px;

    line-height: 1.55;

    white-space: nowrap;
  }
}


/* =========================
   MOBILE
   ========================= */

@media (max-width: 700px) {
  .hero {
    min-height: auto;
    padding: 0;
  }


  /* =========================
     HEADER
     ========================= */

  .hero-header {
    position: absolute;

    top: 0;
    left: 22px;
    right: 22px;

    height: 70px;
  }

  .header-logo {
    font-size: 21px;
  }

  .header-navigation {
    display: none;
  }


  /* =========================
     BODY
     ========================= */

  .hero-body {
    display: flex;
    flex-direction: column;

    min-height: auto;
  }


  /* =========================
     MAIN
     ========================= */

  .hero-content {
    min-height: auto;
    justify-content: flex-start;

    padding:
        100px
        22px
        45px;
  }

  .hero-position {
    margin: 0 0 20px 2px;
    padding-top: 17px;

    font-size: 9px;
    letter-spacing: 0.16em;
  }

  .hero-position::before {
    width: 20px;
  }

  .hero-title {
    font-size: clamp(68px, 21.5vw, 92px);

    line-height: 0.79;
    letter-spacing: -0.055em;

    transform: scaleY(1.08);
  }


  /* =========================
     VIEW WORK
     ========================= */

  .view-work {
    gap: 14px;

    margin-top: 34px;

    font-size: 10px;
  }

  .view-work-icon {
    width: 44px;
    height: 44px;

    font-size: 18px;
  }


  /* =========================
     IMAGE
     ========================= */

  .hero-image {
    width: 100%;
    height: 400px;

    margin: 0;
  }

  .hero-image img {
    width: 100%;
    height: 100%;

    object-fit: cover;
    object-position: center 35%;
  }

  /* =========================
     INFO
     ========================= */

  .hero-info {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));

    gap: 42px 24px;

    padding:
        45px
        22px
        55px;
  }

  .hero-info__group {
    padding-left: 14px;
  }

  .hero-info__group::before {
    height: 100%;
  }

  .hero-info__label {
    margin-bottom: 13px;

    font-size: 9px;
    letter-spacing: 0.12em;
  }

  .hero-info__list li {
    font-size: 11px;
    line-height: 1.55;
  }
}
</style>