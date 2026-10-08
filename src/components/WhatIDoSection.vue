<script setup>
import whatIDoImage from '../assets/images/what-i-do.png'
</script>

<template>
  <section id="what-i-do" class="what-i-do">

    <!-- LEFT -->
    <div class="what-i-do-main">
      <header class="what-i-do-header">
        <span class="section-number">03.</span>
        <h2 class="title">WHAT I DO</h2>
      </header>

      <div class="timeline">

        <article class="item">
          <div class="item-marker">
            <span class="item-dot"></span>
          </div>

          <span class="item-number">01</span>

          <div class="item-info">
            <h3 class="item-title">
              WEB DEVELOPMENT
            </h3>

            <p class="item-text">
              Building modern web applications from interface to backend,
              with a focus on performance, maintainability and real-world use.
            </p>
          </div>
        </article>


        <article class="item">
          <div class="item-marker">
            <span class="item-dot"></span>
          </div>

          <span class="item-number">02</span>

          <div class="item-info">
            <h3 class="item-title">
              BACKEND DEVELOPMENT
            </h3>

            <p class="item-text">
              Designing APIs, database architecture and server-side systems,
              from application logic to deployment and production infrastructure.
            </p>
          </div>
        </article>


        <article class="item">
          <div class="item-marker">
            <span class="item-dot"></span>
          </div>

          <span class="item-number">03</span>

          <div class="item-info">
            <h3 class="item-title">
              iOS DEVELOPMENT
            </h3>

            <p class="item-text">
              Building native iOS applications with Swift and SwiftUI,
              focusing on clean interfaces, performance and intuitive user experience.
            </p>
          </div>
        </article>


        <article class="item">
          <div class="item-marker">
            <span class="item-dot"></span>
          </div>

          <span class="item-number">04</span>

          <div class="item-info">
            <h3 class="item-title">
              PRODUCT DEVELOPMENT
            </h3>

            <p class="item-text">
              Turning ideas into working digital products — from architecture
              and technical decisions to development, deployment and further iteration.
            </p>
          </div>
        </article>

        <article class="item">
          <div class="item-marker">
            <span class="item-dot"></span>
          </div>

          <span class="item-number">05</span>

          <div class="item-info">
            <h3 class="item-title">
              UI & VISUAL DESIGN
            </h3>

            <p class="item-text">
              Designing clean interfaces, layouts and visual concepts,
              from early prototypes to polished assets for digital products.
            </p>
          </div>
        </article>

      </div>
    </div>


    <!-- RIGHT IMAGE -->
    <div class="what-i-do-visual">
      <img
          :src="whatIDoImage"
          alt=""
          draggable="false"
      />
    </div>

  </section>
</template>


<style scoped>
.what-i-do {
  display: grid;
  grid-template-columns: minmax(0, 1fr) 43%;

  background: var(--color-background);
  color: var(--color-text);

  user-select: none;
  -webkit-user-select: none;
}


/* =========================
   MAIN
   ========================= */

.what-i-do-main {
  padding:
      70px
      45px
      75px
      var(--page-padding);
}


/* =========================
   HEADER
   ========================= */

.what-i-do-header {
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
   TIMELINE
   ========================= */

.timeline {
  position: relative;

  max-width: 520px;
}

.timeline::before {
  content: '';

  position: absolute;

  top: 7px;
  bottom: 7px;
  left: 4px;

  width: 1px;

  background: var(--color-border);
}


/* =========================
   ITEM
   ========================= */

.item {
  position: relative;

  display: grid;
  grid-template-columns: 36px 42px minmax(0, 1fr);

  align-items: start;

  min-height: 105px;
}

.item:last-child {
  min-height: auto;
}


/* =========================
   MARKER
   ========================= */

.item-marker {
  position: relative;

  z-index: 2;

  padding-top: 5px;
}

.item-dot {
  display: block;

  width: 9px;
  height: 9px;

  border-radius: 50%;

  background: var(--color-text);

  box-shadow:
      0 0 0 5px var(--color-background);

  transition: transform 0.25s ease;
}


/* =========================
   NUMBER
   ========================= */

.item-number {
  padding-top: 4px;

  color: var(--color-text-secondary);

  font-size: 10px;
  font-weight: 400;

  line-height: 1;
  letter-spacing: 0.08em;
}


/* =========================
   INFO
   ========================= */

.item-info {
  padding-bottom: 30px;
}

.item-title {
  margin: 0;

  font-size: clamp(17px, 1.35vw, 22px);
  font-weight: 600;

  line-height: 1.05;
  letter-spacing: -0.035em;

  transition: transform 0.25s ease;
}

.item-text {
  max-width: 420px;

  margin-top: 9px;

  color: var(--color-text-secondary);

  font-size: 12px;
  font-weight: 400;

  line-height: 1.5;

  transition: color 0.25s ease;
}


/* =========================
   IMAGE
   ========================= */

.what-i-do-visual {
  position: relative;

  min-width: 0;

  overflow: hidden;

  background: var(--color-background);
}

.what-i-do-visual img {
  position: absolute;

  inset: 0;

  width: 100%;
  height: 100%;

  object-fit: cover;
  object-position: center;

  transition:
      transform 0.8s cubic-bezier(0.2, 0.7, 0.2, 1);

  filter: brightness(0.94) contrast(1.03);
}

.what-i-do-visual:hover img {
  transform: scale(1.025);
}


/* =========================
   HOVER
   ========================= */

.item:hover .item-dot {
  transform: scale(1.35);
}

.item:hover .item-title {
  transform: translateX(4px);
}

.item:hover .item-text {
  color: var(--color-text);
}


/* =========================
   TABLET
   ========================= */

@media (max-width: 1000px) {
  .what-i-do {
    grid-template-columns: minmax(0, 1fr) 34%;
  }

  .what-i-do-main {
    padding:
        65px
        30px
        70px
        var(--page-padding);
  }

  .what-i-do-header {
    margin-bottom: 45px;
  }

  .item {
    min-height: 100px;
  }

  .item-text {
    max-width: 330px;
  }
}


/* =========================
   MOBILE
   ========================= */

@media (max-width: 700px) {
  .what-i-do {
    display: block;
  }

  .what-i-do-main {
    padding:
        60px
        var(--page-padding)
        65px;
  }

  .what-i-do-header {
    margin-bottom: 40px;
  }

  .title {
    font-size: 16vw;
  }

  .what-i-do-visual {
    display: none;
  }

  .timeline {
    max-width: 100%;
  }

  .timeline::before {
    left: 3px;
  }

  .item {
    grid-template-columns:
        30px
        35px
        minmax(0, 1fr);

    min-height: 110px;
  }

  .item-dot {
    width: 7px;
    height: 7px;

    box-shadow:
        0 0 0 4px var(--color-background);
  }

  .item-info {
    padding-bottom: 30px;
  }

  .item-title {
    font-size: 18px;
  }

  .item-text {
    max-width: 360px;

    margin-top: 7px;

    font-size: 11px;
  }

  .item:hover .item-title {
    transform: none;
  }
}
</style>