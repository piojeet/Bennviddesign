import { ref } from "vue";

<template>
  <div class="home">
    <!-- Main Content -->
    <section ref="grid" class="grid-container">
      <!-- Card 1: Profile - Takes 2 columns -->
      <!-- @click="$router.push('/about')" -->
      <div class="card profile-card">
        <div class="profile-content">
          <div class="profile-image">
            <img src="@/assets/img/portfoliopic1.jpg" alt="Profile Picture" />
          </div>
          <div class="profile-info">
            <h6>A WEB DEVELOPER</h6>
            <h2>Marcus<br>Bennvid.</h2>
            <p>I am a Web Designer based in Sweden.</p>
            <!-- <svg xmlns="http://www.w3.org/2000/svg" class="enter-btn" width="20" height="20" viewBox="0 0 24 24"
              fill="none" stroke="#ffffff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M13 17l5-5-5-5M6 17l5-5-5-5" />
            </svg> -->
          </div>
        </div>
      </div>

      <div class="card banner-card">
        <span>AVAILABLE FOR FREELANCE WORK</span>
      </div>

      <!-- Card 2: Credentials -->
      <CredentialsCard />

      <!-- Card 3: Certifications -->
      <div class="card project-card" @click="$router.push('/projects')">
        <div class="card-img">
          <img src="@/assets/img/projects-logo.png" style="max-width: 100%; scale:0.8;" alt="Projects Icon">
        </div>
        <div class="card-content">
          <h6>Showcase</h6>
          <h4>Projects</h4>
          <svg xmlns="http://www.w3.org/2000/svg" class="enter-btn" width="20" height="20" viewBox="0 0 24 24"
            fill="none" stroke="#ffffff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M13 17l5-5-5-5M6 17l5-5-5-5" />
          </svg>
        </div>
      </div>


      <!-- Card 4: Download CV -->
      <div class="mid-row">
        <div class="card download-card" @click="$router.push('/cv')">
          <div class="card-img">
            <img src="@/assets/img/cv-download-dark.png" alt="Download Icon"
              style="max-width: 100%; max-height: 80px; margin:auto;"></img>
          </div>
          <div class=" card-content">
            <h6>My CV</h6>
            <h4>Download</h4>
            <svg xmlns="http://www.w3.org/2000/svg" class="enter-btn" width="20" height="20" viewBox="0 0 24 24"
              fill="none" stroke="#ffffff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M13 17l5-5-5-5M6 17l5-5-5-5" />
            </svg>
          </div>
        </div>

        <!-- Card 5: Services -->
        <div class="card services-card" @click="$router.push('/services')">
          <div class="card-icon" style="color: white;">
            <span class="ico uiux"></span>
            <span class="ico brand"></span>
            <span class="ico code"></span>
            <span class="ico launch"></span>
          </div>
          <div class="card-content">
            <h6>Specialization</h6>
            <h4>Services Offering</h4>
            <svg xmlns="http://www.w3.org/2000/svg" class="enter-btn" width="20" height="20" viewBox="0 0 24 24"
              fill="none" stroke="#ffffff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M13 17l5-5-5-5M6 17l5-5-5-5" />
            </svg>
          </div>
        </div>

        <!-- Card 6: Profiles/Social -->
        <ProfilesCard>
          <template #githubIcon>
            <!-- klistra in din GitHub svg här -->
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" style="width: 50px;">
              <path fill="#ffffff" d="..." />
            </svg>
          </template>

          <template #linkedinIcon>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" style="width: 50px;">
              <path fill="#ffffff" d="..." />
            </svg>
          </template>

          <template #xIcon>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" style="width: 50px;">
              <path fill="#ffffff" d="..." />
            </svg>
          </template>
        </ProfilesCard>


      </div>
      <div class="bottom-row">
        <div class="card package-card" @click="$router.push('/services')">
          <div class="package">
            <h4>Base</h4>
            <p class="package-sub">For simple, modern websites.</p>

            <p class="package-item">1–3 pages</p>
            <p class="package-item">Mobile-friendly</p>
            <p class="package-item">Fast delivery</p>

            <p class="package-price">
              <span class="from">from</span>
              <span class="amount">5&nbsp;000 SEK</span>
            </p>
          </div>

          <div class="package">
            <h4>Standard</h4>
            <p class="package-sub">For growing businesses.</p>

            <p class="package-item">4–6 pages</p>
            <p class="package-item">Custom layout</p>
            <p class="package-item">SEO-ready</p>

            <p class="package-price">
              <span class="from">from</span>
              <span class="amount">7&nbsp;500 SEK</span>
            </p>
          </div>

          <div class="package">
            <h4>Premium</h4>
            <p class="package-sub">For a complete online presence.</p>

            <p class="package-item">Custom design</p>
            <p class="package-item">SEO</p>
            <p class="package-item">Integrations</p>

            <p class="package-price">
              <span class="from">from</span>
              <span class="amount">10&nbsp;000 SEK</span>
            </p>
          </div>

          <svg xmlns="http://www.w3.org/2000/svg" class="enter-btn" width="20" height="20" viewBox="0 0 24 24"
            fill="none" stroke="#ffffff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M13 17l5-5-5-5M6 17l5-5-5-5" />
          </svg>
        </div>
        <LetsWork />
      </div>
    </section>
  </div>
</template>

<script>
import CredentialsCard from "@/components/CredentialsCard.vue";
import ProfilesCard from "@/components/ProfilesCard.vue";
import LetsWork from "@/components/LetsWork.vue";

export default {
  name: "HomeView",
  components: { CredentialsCard, ProfilesCard, LetsWork },

};


</script>

<style scoped>
.ico {
  width: 64px;
  height: 64px;
  display: inline-block;
  background-color: white;
  -webkit-mask: center/contain no-repeat;
  mask: center/contain no-repeat;
}

.ico.uiux {
  -webkit-mask-image: url('../assets/svg/uiux.svg');
  mask-image: url('../assets/svg/uiux.svg');
}

.ico.brand {
  -webkit-mask-image: url('../assets/svg/brand.svg');
  mask-image: url('../assets/svg/brand.svg');
}

.ico.code {
  -webkit-mask-image: url('../assets/svg/code.svg');
  mask-image: url('../assets/svg/code.svg');
}

.ico.launch {
  -webkit-mask-image: url('../assets/svg/launch.svg');
  mask-image: url('../assets/svg/launch.svg');
  transform: scale(0.8);
}

.home {
  background: #0a0a0a;
  min-height: 80vh;
  color: #ffffff;
  padding: 40px 0;
  display: flex;
  align-items: center;
}

/* Grid Layout */
.grid-container {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  grid-template-rows: auto auto;
  grid-template-areas: "profile banner banner" "profile cred cert" "bottom  bottom bottom";
  gap: 20px;
  max-width: 1200px;
  margin: 0 auto;
}

.bottom-row {
  grid-column: 1/ -1;
  display: grid;
  grid-template-columns: 2.5fr 1.5fr;
  gap: 20px;
}

.letswork-card {
  display: flex;
  align-items: center;
  /* justify-content: center; */
}

/* Second row with 4 cards */
.mid-row {
  grid-column: 1 / -1;
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  grid-area: bottom;
  gap: 20px;
}

/* Grid positioning */
.profile-card {
  grid-area: profile;
}

.credentials-card {
  grid-area: cred;
  display: grid
}

.project-card {
  grid-area: cert;
  display: grid
}

.card-content {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: flex-start;
  gap: 1rem;

  h4,
  h6 {
    margin: 0;
  }
}

.banner-card {
  height: 30px;
  padding: 5px !important;
  grid-area: banner;
  display: flex;

  span {
    margin: auto;
    display: flex;
    justify-content: center;
  }
}

.card,
.credentials-card,
.certifications-card,
.download-card,
.services-card,
.profiles-card,
.fourth-card,
.banner-card {
  background:
    radial-gradient(600px circle at 0% 0%, rgba(255, 255, 255, 0.06), rgba(255, 255, 255, 0) 38%),
    linear-gradient(180deg, #1a1a1a, #0e0e0e) !important
    /* box-shadow: 0 10px 30px rgba(0, 0, 0, .35); */
}

/* Base Card Styling */
.card {
  border-radius: 20px;
  padding: 30px;
  transition: transform 0.3s, box-shadow 0.3s;
  cursor: pointer;
  /* text-align: center; */
  position: relative;
  overflow: hidden;
}

.card:hover {
  transform: translateY(-5px);
  /* box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5); */
}


/* Profile Card Specific */
.profile-card {
  text-align: left;
  display: flex;
  align-items: center;
}

.profile-content {
  display: flex;
  align-items: center;
  gap: 25px;
}

.profile-image {
  flex-shrink: 0;
}

.profile-image img {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  padding: 4px;
}

.profile-info h6 {
  margin-bottom: 10px;
}

.profile-info h2 {
  margin-bottom: 15px;
}

/* Bottom row*/
.package-card {
  display: flex;
  justify-content: space-between;

}

.package h4 {
  margin-bottom: 6px;
}

/* “Fake bullets” */
.package-item {
  margin: 3px 0;
  opacity: 0.85;
  position: relative;
  padding-left: 14px;
  line-height: 1 !important;
}

.package-item::before {
  content: "–";
  position: absolute;
  left: 0;
  top: 0;
}

.package-price {
  margin-top: auto;
  padding-top: 12px;
  display: flex;
  gap: 8px;
  align-items: baseline;
  opacity: 1;
}

.package-price .from {
  opacity: 0.6;
  font-size: 11px;
  letter-spacing: 1px;
  text-transform: uppercase;
}

.package-price .amount {
  font-size: 16px;
  font-weight: 800;
}

.letswork-card .cta-sub {
  margin-top: 10px;
  opacity: 0.6;
  font-size: 0.95rem;
  line-height: 1;
}


/* Responsive Design */
@media (max-width: 1024px) {
  .home {
    padding: 12px;
    padding-bottom: 40px;
  }

  .grid-container {
    grid-template-columns: 1fr 1fr;
    grid-template-areas:
      "profile profile"
      "banner banner"
      "cred cert"
      "bottom bottom";
    gap: 20px;
    width: 100%;
    max-width: 960px;
  }

  .profile-card {
    grid-area: profile;
    min-height: 224px;
  }

  .banner-card {
    grid-area: banner;
    min-height: 32px;
  }

  .credentials-card {
    grid-area: cred;
    min-height: 182px;
  }

  .project-card {
    grid-area: cert;
    min-height: 182px;
  }

  .mid-row {
    grid-area: bottom;
    grid-column: 1 / -1;
    grid-template-columns: 1fr 2fr;
    grid-template-areas:
      "download services"
      "profiles profiles";
  }

  .download-card {
    grid-area: download;
    min-height: 180px;
  }

  .services-card {
    grid-area: services;
    min-height: 180px;
  }

  .profiles-card {
    grid-area: profiles;
    min-height: 146px;
  }

  .bottom-row {
    grid-column: 1 / -1;
    grid-template-columns: 1fr;
    grid-template-rows: auto auto;
  }

  .package-card {
    min-height: 236px;
  }

  .letswork-card {
    min-height: 118px;
  }
}

@media (max-width: 768px) {
  .grid-container {
    grid-template-columns: 1fr;
    grid-template-areas:
      "profile"
      "banner"
      "cred"
      "cert"
      "bottom";
    padding: 0;
    gap: 20px;
  }

  .bottom-row {
    grid-template-columns: 1fr;
  }

  .mid-row {
    grid-template-columns: 1fr;
    grid-template-areas:
      "download"
      "services"
      "profiles";
  }

  .profile-content {
    flex-direction: row;
    gap: 20px;
    text-align: left;
  }

  .profile-card {
    text-align: center;
    min-height: 196px;
    padding-left: 38px;
  }

  .card {
    padding: 25px;
  }

  .profile-image img {
    width: 100px;
    height: 100px;
  }
}

@media (max-width: 425px) {
  .profile-card {
    min-height: 270px;
    padding: 25px 30px;
    align-items: flex-start;
    text-align: center;
  }

  .profile-card::before {
    display: none;
  }

  .profile-content {
    width: 100%;
    flex-direction: column;
    align-items: flex-start;
    gap: 16px;
  }

  .profile-image {
    align-self: center;
  }

  .package-card {
    min-height: 0;
    padding: 20px;
    flex-direction: column;
    align-items: stretch;
  }

  .package+.package {
    margin-top: 14px;
    padding-top: 14px;
    border-top: 1px solid rgba(255, 255, 255, 0.12);
  }

  .package h4 {
    margin-bottom: 6px;
  }

  .package-price {
    margin-top: 10px;
    padding-top: 0;
  }

  .package-card .enter-btn {
    display: none;
  }

  .card[data-v-9ea40744] {
    padding: 20px;
  }

  .card h2 {
    font-size: 28px;
  }

  .card p {
    font-size: 14px;
  }

  .profile-info {
    margin: auto;
    text-align: center;
  }
}
</style>
