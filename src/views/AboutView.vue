<template>
  <div class="about">
    <div class="site-container">
      <!-- Title row -->
      <!-- <header class="about-header">
        <h1 class="about-title">
          <span class="spark">✳</span>
          Self-summary
          <span class="spark">✳</span>
        </h1>
      </header> -->

      <!-- Top row: photo + summary -->
      <section class="about-top">
        <div class="card about-photo">
          <div class="photo-frame">
            <!-- Byt ut src till din bild -->
            <img src="@/assets/img/portfoliopic1.jpg" alt="Profile photo" />
          </div>
        </div>

        <div class="card about-summary">
          <div class="summary-kicker">
            <span class="kicker-mark">✦</span>
          </div>

          <h2 class="summary-name">Marcus Bennvid</h2>
          <p class="summary-text">
            I’m a Sweden-based web developer & designer focused on clean UI, solid UX and fast,
            maintainable builds. I enjoy crafting premium-feeling interfaces with reusable components.
          </p>
        </div>
      </section>

      <!-- Middle row: experience + education -->
      <section class="about-mid">
        <div class="card about-block">
          <h6 class="block-title">Experience</h6>

          <div class="timeline">
            <div class="item">
              <p class="meta">2023 – Present</p>
              <h4 class="role">Freelance Web Designer & Developer</h4>
              <p class="org">Bennviddesign</p>
            </div>

            <div class="item">
              <p class="meta">2021 – 2023</p>
              <h4 class="role">Front-End Developer</h4>
              <p class="org">Client projects / collaborations</p>
            </div>
          </div>
        </div>

        <div class="card about-block">
          <h6 class="block-title">Education</h6>

          <div class="timeline">
            <div class="item">
              <p class="meta">2020 – 2021</p>
              <h4 class="role">Web Development (focused studies)</h4>
              <p class="org">Online / bootcamp / self-driven</p>
            </div>

            <div class="item">
              <p class="meta">2018 – 2020</p>
              <h4 class="role">Design + Branding (foundation)</h4>
              <p class="org">Projects + continuous learning</p>
            </div>
          </div>
        </div>
      </section>

      <!-- Bottom row: profiles + cta + credentials -->
      <section class="about-bottom">
        <ProfilesCard />
        <LetsWork />
        <CredentialsCard />
      </section>
    </div>
  </div>
</template>

<script setup>
import { useRouter } from "vue-router";
import ProfilesCard from "@/components/ProfilesCard.vue";
import CredentialsCard from "@/components/CredentialsCard.vue";
import LetsWork from "@/components/LetsWork.vue";

const router = useRouter();
const go = (path) => router.push(path);
</script>

<style scoped>
/* Page wrapper */
.about {
  padding: 28px 0 40px;
}

/* Same max width as your header/nav */
.site-container {
  max-width: 1200px;
  margin: 0 auto;
}

/* Title */
.about-header {
  display: flex;
  justify-content: center;
  margin: 10px 0 18px;
}

.about-title {
  margin: 0;
  font-weight: 900;
  letter-spacing: 0.04em;
  font-size: clamp(34px, 5vw, 56px);
  text-align: center;
}

.spark {
  opacity: 0.6;
  margin: 0 10px;
}

/* Top layout */
.about-top {
  display: grid;
  grid-template-columns: 360px 1fr;
  gap: 20px;
  align-items: stretch;
}

/* Photo card */
.about-photo {
  padding: 24px;
  display: grid;
  place-items: center;
}

.photo-frame {
  width: 100%;
  aspect-ratio: 1 / 1;
  border-radius: 22px;
  overflow: hidden;
  padding: 10px;
}

.photo-frame img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 18px;
  display: block;
}

/* Summary card */
.about-summary {
  padding: 26px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  min-height: 240px;
}

.summary-kicker {
  opacity: 0.6;
  margin-bottom: 10px;
}

.summary-name {
  margin: 0 0 10px;
  font-size: 30px;
  line-height: 1.1;
}

.summary-text {
  margin: 0;
  opacity: 0.85;
  line-height: 1.6;
  max-width: 70ch;
}

/* Mid layout */
.about-mid {
  margin-top: 20px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.about-block {
  padding: 26px;
}

.block-title {
  margin: 0 0 18px;
  opacity: 0.75;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  font-size: 11px;
}

/* Timeline */
.timeline {
  display: grid;
  gap: 18px;
}

.item .meta {
  margin: 0 0 6px;
  opacity: 0.55;
  font-size: 12px;
  letter-spacing: 0.04em;
}

.item .role {
  margin: 0 0 6px;
  font-size: 16px;
}

.item .org {
  margin: 0;
  opacity: 0.75;
}

/* Bottom row */
.about-bottom {
  margin-top: 20px;
  display: grid;
  grid-template-columns: 300px 1fr 300px;
  gap: 20px;
}

/* CTA card */
.about-cta {
  padding: 26px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: relative;
}

.cta-kicker {
  opacity: 0.6;
  margin-bottom: 14px;
}

.cta-title {
  margin: 0 0 10px;
  font-size: 36px;
  line-height: 1.05;
}

.accent {
  color: #28517c;
}

.cta-sub {
  margin: 0;
  opacity: 0.75;
}

.arrow {
  position: absolute;
  right: 18px;
  bottom: 16px;
  opacity: 0.5;
}

/* Responsive */
@media (max-width: 1100px) {
  .about-bottom {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 900px) {
  .about-top {
    grid-template-columns: 1fr;
  }

  .about-mid {
    grid-template-columns: 1fr;
  }
}
</style>
