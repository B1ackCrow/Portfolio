<script setup>
</script>

<template>
  <section id="tech-stack" class="tech-stack">
    <header class="tech-stack-header">
      <span class="section-number">04.</span>
      <h2 class="title">TECH STACK</h2>
    </header>

    <div class="stack-groups">

      <section class="stack-group">
        <h3 class="stack-group-title">BACKEND</h3>

        <ul class="stack-items">
          <li class="stack-item">C#</li>
          <li class="stack-item">.NET</li>
          <li class="stack-item">ASP.NET Core</li>
          <li class="stack-item">PostgreSQL</li>
        </ul>
      </section>

      <section class="stack-group">
        <h3 class="stack-group-title">FRONTEND</h3>

        <ul class="stack-items">
          <li class="stack-item">Vue.js</li>
          <li class="stack-item">JavaScript</li>
        </ul>
      </section>

      <section class="stack-group">
        <h3 class="stack-group-title">MOBILE</h3>

        <ul class="stack-items">
          <li class="stack-item">Swift</li>
          <li class="stack-item">SwiftUI</li>
          <li class="stack-item">UIKit</li>
          <li class="stack-item">Xcode</li>
        </ul>
      </section>

      <section class="stack-group">
        <h3 class="stack-group-title">INFRASTRUCTURE</h3>

        <ul class="stack-items">
          <li class="stack-item">Linux</li>
          <li class="stack-item">Docker</li>
          <li class="stack-item">Nginx</li>
          <li class="stack-item">CI/CD</li>
        </ul>
      </section>

      <section class="stack-group">
        <h3 class="stack-group-title">DESIGN</h3>

        <ul class="stack-items">
          <li class="stack-item">Figma</li>
          <li class="stack-item">Photoshop</li>
          <li class="stack-item">Illustrator</li>
        </ul>
      </section>

    </div>
  </section>
</template>

<style scoped>
.tech-stack {
  height: 100%;

  padding: 70px var(--page-padding) 75px;

  background: var(--color-background);
  color: var(--color-text);

  user-select: none;
  -webkit-user-select: none;
}


/* =========================
   HEADER
   ========================= */

.tech-stack-header {
  margin-bottom: 50px;
}

.section-number {
  display: block;

  margin-bottom: 8px;

  color: var(--color-text-secondary);

  font-size: 11px;
  font-weight: 400;

  letter-spacing: 0.1em;
}

.title {
  margin: 0;

  font-size: clamp(48px, 4.2vw, 72px);
  font-weight: 800;

  line-height: 0.9;
  letter-spacing: -0.055em;

  transform: scaleY(1.06);
  transform-origin: left bottom;
}


/* =========================
   GROUPS
   ========================= */

.stack-groups {
  display: flex;
  flex-direction: column;

  gap: 36px;
}

.stack-group {
  margin: 0;
}

.stack-group-title {
  margin: 0 0 14px;

  color: var(--color-text-secondary);

  font-size: 12px;
  font-weight: 500;

  line-height: 1;
  letter-spacing: 0.16em;
}


/* =========================
   TECHNOLOGIES
   ========================= */

.stack-items {
  display: flex;
  flex-wrap: wrap;

  gap: 9px;

  margin: 0;
  padding: 0;

  list-style: none;
}

.stack-item {
  padding: 10px 14px;

  border: 1px solid transparent;
  border-radius: 3px;

  background: rgba(17, 17, 17, 0.055);
  color: var(--color-text);

  font-size: 13px;
  font-weight: 400;

  line-height: 1;

  transition:
      background 0.2s ease,
      border-color 0.2s ease,
      transform 0.2s ease;
}

.stack-item:hover {
  border-color: var(--color-border);

  background: transparent;

  transform: translateY(-2px);
}


/* =========================
   TABLET
   ========================= */

@media (max-width: 1000px) {
  .tech-stack {
    padding-top: 65px;
    padding-bottom: 70px;
  }

  .tech-stack-header {
    margin-bottom: 45px;
  }

  .stack-groups {
    gap: 28px;
  }

  .stack-item {
    padding: 8px 11px;

    font-size: 11px;
  }
}


/* =========================
   MOBILE
   ========================= */

@media (max-width: 700px) {
  .tech-stack {
    height: auto;

    padding-top: 60px;
    padding-bottom: 65px;
  }

  .tech-stack-header {
    margin-bottom: 40px;
  }

  .title {
    font-size: 16vw;
  }

  .stack-groups {
    gap: 26px;
  }

  .stack-group-title {
    font-size: 10px;
  }

  .stack-items {
    gap: 7px;
  }

  .stack-item {
    padding: 8px 11px;

    font-size: 11px;
  }
}
</style>