<script setup>
import mailIcon from '../assets/icons/mail.svg'
import githubIcon from '../assets/icons/github.svg'
import telegramIcon from '../assets/icons/telegram.svg'
</script>

<template>
  <section id="contact" class="contact">
    <div class="contact-content">

      <div class="contact-main">
        <span class="section-number">05.</span>

        <h2 class="title">
          LET'S<br>
          BUILD<br>
          SOMETHING<br>
          <span>GREAT</span>
        </h2>
      </div>

      <div class="contact-list">
        <a href="mailto:mallydenis@icloud.com" class="contact-item">
          <img
              :src="mailIcon"
              class="contact-icon"
              alt=""
              draggable="false"
          >

          <span class="contact-value">
            mallydenis@icloud.com
          </span>
        </a>

        <a href="https://github.com/B1ackCrow" class="contact-item">
          <img
              :src="githubIcon"
              class="contact-icon"
              alt=""
              draggable="false"
          >

          <span class="contact-value">
            github.com/B1ackCrow
          </span>
        </a>

        <a href="https://t.me/DeonisYakovlev" class="contact-item">
          <img
              :src="telegramIcon"
              class="contact-icon"
              alt=""
              draggable="false"
          >

          <span class="contact-value">
            @DeonisYakovlev
          </span>
        </a>
      </div>

    </div>

    <div class="contact-footer">
      <span>© 2026 DENIS MALYY</span>
      <span>FULL-STACK DEVELOPER</span>
    </div>
  </section>
</template>

<style scoped>
.contact {
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  min-height: 370px;

  padding:
      60px
      var(--page-padding)
      28px;

  background: var(--color-background-dark);
  color: var(--color-text-light);

  user-select: none;
  -webkit-user-select: none;
}


/* =========================
   CONTENT
   ========================= */

.contact-content {
  display: grid;
  grid-template-columns: 46% 54%;
  align-items: center;

  flex: 1;
}


/* =========================
   LEFT
   ========================= */

.contact-main {
  align-self: start;
}

.section-number {
  display: block;

  margin-bottom: 16px;

  color: rgba(242, 241, 237, 0.5);

  font-size: 11px;
  font-weight: 400;

  letter-spacing: 0.1em;
}

.title {
  margin: 0;

  font-size: clamp(46px, 4vw, 70px);
  font-weight: 800;

  line-height: 0.82;
  letter-spacing: -0.055em;

  transform: scaleY(1.06);
  transform-origin: left top;
}

.title span {
  color: #555;
}


/* =========================
   CONTACTS
   ========================= */

.contact-list {
  display: flex;
  flex-direction: column;

  gap: 30px;

  width: fit-content;

  /* Контакты чуть ближе к заголовку */
  transform: translateX(-35px);
}


/* =========================
   ITEM
   ========================= */

.contact-item {
  display: flex;
  align-items: center;

  gap: 20px;

  width: fit-content;

  color: var(--color-text-light);

  transition:
      transform 0.25s ease,
      opacity 0.25s ease;
}

.contact-icon {
  width: 22px;
  height: 22px;

  flex-shrink: 0;

  object-fit: contain;
}

.contact-value {
  font-size: 15px;
  font-weight: 400;

  line-height: 1;

  letter-spacing: -0.005em;
}


/* =========================
   HOVER
   ========================= */

.contact-item:hover {
  transform: translateX(5px);
}

.contact-list:hover .contact-item:not(:hover) {
  opacity: 0.4;
}


/* =========================
   FOOTER
   ========================= */

.contact-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;

  margin-top: 35px;

  color: rgba(242, 241, 237, 0.28);

  font-size: 8px;
  font-weight: 400;

  letter-spacing: 0.14em;
}


/* =========================
   TABLET
   ========================= */

@media (max-width: 1000px) {
  .contact {
    min-height: 360px;

    padding-top: 55px;
  }

  .contact-content {
    grid-template-columns: 45% 55%;
  }

  .contact-list {
    transform: translateX(0);
  }

  .title {
    font-size: clamp(44px, 5vw, 62px);
  }
}


/* =========================
   MOBILE
   ========================= */

@media (max-width: 700px) {
  .contact {
    min-height: auto;

    padding-top: 60px;
    padding-bottom: 25px;
  }

  .contact-content {
    display: block;
  }

  .title {
    font-size: 15vw;
  }

  .contact-list {
    gap: 26px;

    margin-top: 60px;

    transform: none;
  }

  .contact-value {
    font-size: 13px;
  }

  .contact-footer {
    margin-top: 70px;

    font-size: 7px;
  }

  .contact-list:hover .contact-item:not(:hover) {
    opacity: 1;
  }
}
</style>