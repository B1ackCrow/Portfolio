<template>
  <section id="projects" class="projects">
    <div class="projects-header">
      <div>
        <span class="projects-number">02.</span>
        <h2 class="projects-title">PROJECTS</h2>
      </div>
    </div>

    <div class="projects-grid">

      <!-- PRIMGIDROMET -->
      <article class="project project--featured">
        <div class="project-media">

          <Transition :name="slideDirection">
            <div
                :key="currentPrimgidrometImage"
                class="primgidromet-slide"
            >
              <img
                  class="project-background primgidromet-background"
                  :src="primgidrometImages[currentPrimgidrometImage]"
                  alt="Primgidromet interface"
              />
            </div>
          </Transition>

          <Transition name="brand-fade">
            <div
                v-if="currentPrimgidrometImage === 0"
                class="primgidromet-brand"
            >
              <img
                  class="primgidromet-logo"
                  src="../assets/images/primgidromet/primgidromet-logo.png"
                  alt=""
              />
            </div>
          </Transition>

          <div class="project-overlay">
            <div class="project-info">
              <a
                  href="https://meteoprim.ru"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="project-link"
              >
                <h3>Primgidromet — Full-Stack Weather Platform</h3>
                <span class="project-link__arrow">↗</span>
              </a>

              <p>Real-time data · Forecasts · Maps · Commercial services</p>
            </div>

            <div class="project-navigation">
              <span class="project-counter">
                {{ String(currentPrimgidrometImage + 1).padStart(2, '0') }}
                /
                {{ String(primgidrometImages.length).padStart(2, '0') }}
              </span>

              <button
                  class="project-navigation__button"
                  type="button"
                  aria-label="Previous image"
                  @click="previousPrimgidrometImage"
              >
                ←
              </button>

              <button
                  class="project-navigation__button"
                  type="button"
                  aria-label="Next image"
                  @click="nextPrimgidrometImage"
              >
                →
              </button>
            </div>
          </div>

        </div>
      </article>


      <!-- RIGHT COLUMN -->
      <div class="projects-secondary">

        <!-- PRYME -->
        <article class="project project--small">
          <div class="project-media">

            <img
                class="project-background pryme-background"
                src="../assets/images/pryme.png"
                alt="Pryme"
            />

            <div class="project-index">
              02
            </div>

            <div class="pryme-brand">
              <div class="pryme-logo">
                PRYME
              </div>

              <div class="pryme-slogan">
                BECOME YOUR BEST
              </div>
            </div>

            <div class="project-small-info">
              <div>
                <h3>Pryme — iOS Fitness App</h3>
                <p>Workout tracking · Progress · Native iOS</p>
              </div>

              <span class="project-status">
                IN DEVELOPMENT
              </span>
            </div>

          </div>
        </article>


        <!-- TRADEFINDER -->
        <article class="project project--small">
          <div class="project-media project-media--light">

            <img
                class="project-background"
                src="../assets/images/tradefinder.png"
                alt="TradeFinder"
            />

            <div class="project-index project-index--dark">
              03
            </div>

            <div class="tradefinder-brand">
              <img
                  class="tradefinder-logo"
                  src="../assets/images/tradefinder-logo.png"
                  alt=""
              />
            </div>

            <div class="project-small-info project-small-info--dark">
              <div>
                <h3>TradeFinder — Marketplace</h3>
                <p>Products · Companies · Search · Admin platform</p>
              </div>

              <span class="project-status">
                IN DEVELOPMENT
              </span>
            </div>

          </div>
        </article>

      </div>
    </div>
  </section>
</template>


<script setup>
import { ref } from 'vue'

import primgidrometCover from '../assets/images/primgidromet/primgidromet.webp'
import primgidrometInterface1 from '../assets/images/primgidromet/interface-image-1.png'
import primgidrometInterface2 from '../assets/images/primgidromet/interface-image-2.png'
import primgidrometInterface3 from '../assets/images/primgidromet/interface-image-3.png'

const primgidrometImages = [
  primgidrometCover,
  primgidrometInterface1,
  primgidrometInterface2,
  primgidrometInterface3
]

const currentPrimgidrometImage = ref(0)
const slideDirection = ref('slide-next')

const nextPrimgidrometImage = () => {
  slideDirection.value = 'slide-next'

  currentPrimgidrometImage.value =
      (currentPrimgidrometImage.value + 1) % primgidrometImages.length
}

const previousPrimgidrometImage = () => {
  slideDirection.value = 'slide-prev'

  currentPrimgidrometImage.value =
      (
          currentPrimgidrometImage.value
          - 1
          + primgidrometImages.length
      ) % primgidrometImages.length
}
</script>


<style scoped>
.projects {
  min-height: 100vh;

  padding: 70px var(--page-padding) 100px;

  background: var(--color-background-dark);
  color: var(--color-text-light);
}


/* =========================
   HEADER
   ========================= */

.projects-header {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;

  margin-bottom: 45px;
}

.projects-number {
  display: block;

  margin-bottom: 8px;

  color: #777;

  font-size: 11px;
  font-weight: 400;
  letter-spacing: 0.1em;
}

.projects-title {
  margin: 0;

  font-size: clamp(48px, 4.2vw, 72px);
  font-weight: 800;

  line-height: 0.9;
  letter-spacing: -0.055em;

  transform: scaleY(1.06);
  transform-origin: left bottom;
}


/* =========================
   GRID
   ========================= */

.projects-grid {
  display: grid;
  grid-template-columns: 1.8fr 1fr;

  gap: 16px;
}

.projects-secondary {
  display: grid;
  grid-template-rows: 1fr 1fr;

  gap: 16px;
}


/* =========================
   PROJECT
   ========================= */

.project {
  min-width: 0;
}

.project-media {
  position: relative;

  width: 100%;
  height: 100%;

  overflow: hidden;

  background: #181818;

  border: 1px solid rgba(255, 255, 255, 0.16);
}

.project--featured .project-media,
.project--small .project-media {
  aspect-ratio: 16 / 9;
}


/* =========================
   BACKGROUNDS
   ========================= */

.project-background {
  position: absolute;

  inset: 0;

  width: 100%;
  height: 100%;

  object-fit: cover;
}

.primgidromet-slide {
  position: absolute;
  inset: 0;

  width: 100%;
  height: 100%;
}

.primgidromet-background {
  transition: transform 0.8s cubic-bezier(0.2, 0.7, 0.2, 1);
}

.project--featured:hover .primgidromet-background {
  transform: scale(1.025);
}

/* Hover только для маленьких проектов */

.project--small .project-background {
  transition: transform 0.8s cubic-bezier(0.2, 0.7, 0.2, 1);
}

.project--small:hover .project-background {
  transform: scale(1.04);
}


/* =========================
   PRIMGIDROMET
   ========================= */

.primgidromet-brand {
  position: absolute;

  z-index: 2;

  top: 50%;
  left: 50%;

  display: flex;
  flex-direction: column;
  align-items: center;

  gap: 14px;

  transform: translate(-50%, -50%);

  pointer-events: none;

  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.25));
}

.primgidromet-logo {
  width: 105px;
  height: auto;
}

.primgidromet-title {
  margin: 0;

  color: white;

  font-size: 21px;
  font-weight: 600;

  letter-spacing: -0.02em;

  text-shadow: 0 1px 4px rgba(0, 0, 0, 0.25);
}


/* =========================
   FEATURED INFO
   ========================= */

.project-overlay {
  position: absolute;

  z-index: 3;

  left: 0;
  right: 0;
  bottom: 0;

  display: flex;
  align-items: flex-end;
  justify-content: space-between;

  padding: 80px 18px 18px;

  background:
      linear-gradient(
          to bottom,
          transparent 0%,
          rgba(0, 0, 0, 0.08) 25%,
          rgba(0, 0, 0, 0.78) 100%
      );

  pointer-events: none;
}

.project-overlay h3 {
  margin: 0;

  color: white;

  font-size: clamp(18px, 1.6vw, 27px);
  font-weight: 600;

  letter-spacing: -0.03em;
}

.project-overlay p {
  margin: 5px 0 0;

  color: rgba(255, 255, 255, 0.6);

  font-size: 11px;
  font-weight: 300;
}


/* =========================
   NAVIGATION
   ========================= */

.project-navigation {
  display: flex;
  align-items: center;

  gap: 8px;

  pointer-events: auto;
}

.project-counter {
  margin-right: 6px;

  color: rgba(255, 255, 255, 0.55);

  font-size: 9px;
  font-weight: 400;

  letter-spacing: 0.08em;
}

.project-navigation__button {
  width: 38px;
  height: 38px;

  display: flex;
  align-items: center;
  justify-content: center;

  padding: 0;

  border: 1px solid rgba(255, 255, 255, 0.25);
  border-radius: 50%;

  background: rgba(10, 10, 10, 0.55);
  color: white;

  font-size: 16px;

  cursor: pointer;

  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);

  transition:
      background 0.2s ease,
      color 0.2s ease,
      border-color 0.2s ease;
}

.project-navigation__button:hover {
  background: white;
  color: #111;

  border-color: white;
}


/* =========================
   PROJECT INDEX
   ========================= */

.project-index {
  position: absolute;

  z-index: 3;

  top: 16px;
  right: 16px;

  color: rgba(255, 255, 255, 0.6);

  font-size: 10px;

  letter-spacing: 0.08em;
}

.project-index--dark {
  color: rgba(0, 0, 0, 0.5);
}


/* =========================
   PRYME
   ========================= */

.pryme-brand {
  position: absolute;

  z-index: 2;

  top: 50%;
  left: 50%;

  display: flex;
  flex-direction: column;
  align-items: center;

  transform: translate(-50%, -50%);

  color: #dfd0c1;

  pointer-events: none;
}

.pryme-logo {
  padding-left: 0.48em;

  font-size: clamp(19px, 1.8vw, 31px);
  font-weight: 500;

  line-height: 1;

  letter-spacing: 0.48em;

  white-space: nowrap;
}

.pryme-slogan {
  margin-top: 12px;
  padding-left: 0.42em;

  font-size: 6px;
  font-weight: 400;

  letter-spacing: 0.42em;

  white-space: nowrap;

  opacity: 0.75;
}


/* =========================
   TRADEFINDER
   ========================= */

.project-media--light {
  background: #e9eef5;
}

.tradefinder-brand {
  position: absolute;

  z-index: 2;

  top: 50%;
  left: 50%;

  display: flex;
  flex-direction: column;
  align-items: center;

  gap: 10px;

  transform: translate(-50%, -50%);

  pointer-events: none;
}

.tradefinder-logo {
  width: 100px;
  height: auto;

  object-fit: contain;
}

.tradefinder-name {
  color: #0e2a53;

  font-size: 17px;
  font-weight: 600;

  letter-spacing: -0.02em;
}


/* =========================
   SMALL PROJECT INFO
   ========================= */

.project-small-info {
  position: absolute;

  z-index: 3;

  top: 16px;
  left: 16px;

  color: white;
}

.project-small-info h3 {
  margin: 0;

  font-size: clamp(16px, 1.3vw, 22px);
  font-weight: 600;

  letter-spacing: -0.03em;
}

.project-small-info p {
  margin: 4px 0 0;

  color: rgba(255, 255, 255, 0.55);

  font-size: 9px;
  font-weight: 300;
}

.project-small-info--dark {
  color: #111;
}

.project-small-info--dark p {
  color: rgba(0, 0, 0, 0.5);
}

.project-status {
  display: inline-block;

  margin-top: 9px;
  padding: 4px 7px;

  border: 1px solid rgba(255, 255, 255, 0.25);

  font-size: 7px;
  font-weight: 500;

  letter-spacing: 0.1em;
}

.project-small-info--dark .project-status {
  border-color: rgba(0, 0, 0, 0.2);
}

.project-link {
  display: inline-flex;
  align-items: center;
  gap: 5px;

  color: inherit;
  text-decoration: none;

  pointer-events: auto;
}

.project-link__arrow {
  display: inline-block;

  font-size: px;
  font-weight: 300;
  line-height: 1;

  transition: transform 0.25s ease;
}


/* =========================
   SLIDER
   ========================= */

.slide-next-enter-active,
.slide-next-leave-active,
.slide-prev-enter-active,
.slide-prev-leave-active {
  transition:
      transform 0.55s cubic-bezier(0.65, 0, 0.35, 1);
}


/* NEXT */

.slide-next-enter-from {
  transform: translateX(100%);
}

.slide-next-enter-to {
  transform: translateX(0);
}

.slide-next-leave-from {
  transform: translateX(0);
}

.slide-next-leave-to {
  transform: translateX(-100%);
}


/* PREVIOUS */

.slide-prev-enter-from {
  transform: translateX(-100%);
}

.slide-prev-enter-to {
  transform: translateX(0);
}

.slide-prev-leave-from {
  transform: translateX(0);
}

.slide-prev-leave-to {
  transform: translateX(100%);
}


/* =========================
   BRAND FADE
   ========================= */

.brand-fade-enter-active,
.brand-fade-leave-active {
  transition: opacity 0.25s ease;
}

.brand-fade-enter-from,
.brand-fade-leave-to {
  opacity: 0;
}


/* =========================
   TABLET
   ========================= */

@media (min-width: 701px) and (max-width: 1200px) {
  .projects {
    min-height: auto;
    padding-top: 55px;
    padding-bottom: 70px;
  }

  .projects-grid {
    /* оставляем текущую композицию */
    width: 100%;
  }
}

@media (max-width: 1000px) {
  .projects {
    padding-top: 65px;
  }

  .projects-header {
    margin-bottom: 45px;
  }

  .projects-grid {
    grid-template-columns: 1.5fr 1fr;
  }

  .primgidromet-logo {
    width: 85px;
  }

  .primgidromet-title {
    font-size: 18px;
  }
}


/* =========================
   MOBILE
   ========================= */

@media (max-width: 700px) {
  .projects {
    min-height: auto;

    padding-top: 60px;
    padding-bottom: 70px;
  }

  .projects-header {
    margin-bottom: 40px;
  }

  .projects-title {
    font-size: 16vw;
  }

  .projects-grid {
    grid-template-columns: 1fr;
  }

  .projects-secondary {
    grid-template-columns: 1fr;
    grid-template-rows: auto;

    gap: 16px;
  }

  .project-overlay {
    padding: 60px 14px 14px;
  }

  .project-counter {
    display: none;
  }

  .project-navigation__button {
    width: 34px;
    height: 34px;
  }

  .primgidromet-logo {
    width: 70px;
  }

  .primgidromet-title {
    font-size: 16px;
  }
}
</style>