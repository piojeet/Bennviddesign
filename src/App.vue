<template>
  <!-- Header -->
  <header class="header">
    <div class="nav-container">
      <img :src="logo" alt="Logo" class="logo" @click="$router.push('/')" style="cursor: pointer;" />
      <!-- <span>Your success, built with code</span> -->
      <nav class="nav-menu" :class="{ 'is-open': mobileMenuOpen }">
        <div class="menu-top">
          <button class="menu-close" type="button" aria-label="Close navigation" @click="mobileMenuOpen = false">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" class="bi bi-x-lg"
              viewBox="0 0 16 16">
              <path
                d="M2.146 2.854a.5.5 0 1 1 .708-.708L8 7.293l5.146-5.147a.5.5 0 0 1 .708.708L8.707 8l5.147 5.146a.5.5 0 0 1-.708.708L8 8.707l-5.146 5.147a.5.5 0 0 1-.708-.708L7.293 8z" />
            </svg>
          </button>
        </div>
        <div class="menu-links">
          <router-link to="/" class="menu-link" @click="mobileMenuOpen = false"><span class="nav-icon">

              <svg width="20" height="20" fill="none" stroke="currentColor" stroke-linecap="round"
                stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path d="M5 10v10a1 1 0 0 0 1 1h12a1 1 0 0 0 1-1V10"></path>
                <path d="M9 21a1 1 0 0 0 1-1v-4a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1v4a1 1 0 0 0 1 1"></path>
                <path d="m3 12 2-2 7-7 7 7 2 2"></path>
              </svg></span><span>Home</span><b>
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-chevron-right-icon lucide-chevron-right">
                <path d="m9 18 6-6-6-6" />
              </svg>
            </b></router-link>
          <router-link to="/credentials" class="menu-link" @click="mobileMenuOpen = false"><span class="nav-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-square-user-icon lucide-square-user">
                <rect width="18" height="18" x="3" y="3" rx="2" />
                <circle cx="12" cy="10" r="3" />
                <path d="M7 21v-2a2 2 0 0 1 2-2h6a2 2 0 0 1 2 2v2" />
              </svg>
            </span><span>Credentials</span><b>
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-chevron-right-icon lucide-chevron-right">
                <path d="m9 18 6-6-6-6" />
              </svg>
            </b></router-link>
          <router-link to="/projects" class="menu-link" @click="mobileMenuOpen = false"><span class="nav-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-laptop-icon lucide-laptop">
                <path
                  d="M18 5a2 2 0 0 1 2 2v8.526a2 2 0 0 0 .212.897l1.068 2.127a1 1 0 0 1-.9 1.45H3.62a1 1 0 0 1-.9-1.45l1.068-2.127A2 2 0 0 0 4 15.526V7a2 2 0 0 1 2-2z" />
                <path d="M20.054 15.987H3.946" />
              </svg>
            </span><span>Projects</span><b>
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-chevron-right-icon lucide-chevron-right">
                <path d="m9 18 6-6-6-6" />
              </svg>
            </b></router-link>
          <router-link to="/cv" class="menu-link" @click="mobileMenuOpen = false"><span class="nav-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-file-user-icon lucide-file-user">
                <path
                  d="M6 22a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h8a2.4 2.4 0 0 1 1.704.706l3.588 3.588A2.4 2.4 0 0 1 20 8v12a2 2 0 0 1-2 2z" />
                <path d="M14 2v5a1 1 0 0 0 1 1h5" />
                <path d="M16 22a4 4 0 0 0-8 0" />
                <circle cx="12" cy="15" r="3" />
              </svg>
            </span><span>CV</span><b>
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-chevron-right-icon lucide-chevron-right">
                <path d="m9 18 6-6-6-6" />
              </svg>
            </b></router-link>
          <router-link to="/services" class="menu-link" @click="mobileMenuOpen = false"><span class="nav-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-code-xml-icon lucide-code-xml">
                <path d="m18 16 4-4-4-4" />
                <path d="m6 8-4 4 4 4" />
                <path d="m14.5 4-5 16" />
              </svg>
            </span><span>Services</span><b>
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-chevron-right-icon lucide-chevron-right">
                <path d="m9 18 6-6-6-6" />
              </svg>
            </b></router-link>
          <router-link to="/contact" class="menu-link" @click="mobileMenuOpen = false"><span class="nav-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-mail-icon lucide-mail">
                <path d="m22 7-8.991 5.727a2 2 0 0 1-2.009 0L2 7" />
                <rect x="2" y="4" width="20" height="16" rx="2" />
              </svg>
            </span><span>Contact</span><b>
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                class="lucide lucide-chevron-right-icon lucide-chevron-right">
                <path d="m9 18 6-6-6-6" />
              </svg>
            </b></router-link>
        </div>
        <div class="menu-work-card">
          <div class="work-icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
              stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
              class="lucide lucide-move-up-right-icon lucide-move-up-right">
              <path d="M13 5H19V11" />
              <path d="M19 5L5 19" />
            </svg>
          </div>
          <div>
            <h3>Let’s work <em>together</em></h3>
            <p>Get in touch and receive a fixed-price quote.</p>
            <button @click="$router.push('/contact'); mobileMenuOpen = false">Let’s Talk</button>
          </div>
        </div>
        <div class="menu-socials">
          <a href="https://github.com/bennviddesign" aria-label="GitHub">
            <svg width="25" height="25" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
              stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M16.25 22.5v-3.865a3.361 3.361 0 0 0-.94-2.607c3.14-.35 6.44-1.538 6.44-6.99a5.43 5.43 0 0 0-1.5-3.746 5.058 5.058 0 0 0-.09-3.765s-1.18-.35-3.91 1.478a13.397 13.397 0 0 0-7 0C6.52 1.177 5.34 1.527 5.34 1.527a5.058 5.058 0 0 0-.09 3.765 5.43 5.43 0 0 0-1.5 3.775c0 5.413 3.3 6.602 6.44 6.991a3.366 3.366 0 0 0-.94 2.577V22.5">
              </path>
              <path d="M9.25 19.503c-5 1.498-5-2.496-7-2.996"></path>
            </svg>
          </a>
          <a href="https://linkedin.com/in/marcus-bennvid" aria-label="LinkedIn">
            <svg width="25" height="25" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
              stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
              <path d="M2 9h4v12H2z"></path>
              <path d="M4 2a2 2 0 1 0 0 4 2 2 0 1 0 0-4z"></path>
            </svg>
          </a>
          <a href="https://x.com/Bennviddesign" aria-label="X">
            <svg xmlns="http://www.w3.org/2000/svg" width="25" height="25" fill="currentColor" class="bi bi-twitter-x"
              viewBox="0 0 16 16">
              <path
                d="M12.6.75h2.454l-5.36 6.142L16 15.25h-4.937l-3.867-5.07-4.425 5.07H.316l5.733-6.57L0 .75h5.063l3.495 4.633L12.601.75Zm-.86 13.028h1.36L4.323 2.145H2.865z" />
            </svg>
          </a>
        </div>
        <!-- <router-link to="/blog">Blog</router-link> -->
      </nav>
      <button class="menu-backdrop" :class="{ 'is-open': mobileMenuOpen }" aria-label="Close navigation"
        @click="mobileMenuOpen = false"></button>
      <div class="nav-con-box">
        <button class="cta-button" @click="$router.push('/contact')">Let’s Talk</button>
        <button class="menu-toggle" type="button" :aria-expanded="mobileMenuOpen" aria-label="Toggle navigation"
          @click="mobileMenuOpen = !mobileMenuOpen">
          <span></span><span></span><span></span>
        </button>
      </div>

    </div>
  </header>

  <!-- Only this part changes -->
  <main class="page-stage">
    <div class="site-container">
      <RouterView v-slot="{ Component, route }">
        <Transition name="flip" mode="out-in">
          <section class="page-face" :key="route.fullPath">
            <component :is="Component" />
          </section>
        </Transition>
      </RouterView>
    </div>
  </main>

  <!-- <router-view /> -->
  <footer>
    <p>© 2025 Bennviddesign</p>
  </footer>
</template>

<script>
import logo from "@/assets/img/logo-dark-nopadding.png";

export default {
  data() {
    return {
      logo,
      mobileMenuOpen: false,
    };
  },
  watch: {
    mobileMenuOpen(isOpen) {
      document.body.classList.toggle("menu-open", isOpen);
    },
  },
  beforeUnmount() {
    document.body.classList.remove("menu-open");
  },
};
</script>

<style lang="scss">
.page-stage {
  /* Gör att mittdelen känns som en fast "yta" */
  perspective: 1200px;
  /* Justera så det matchar din design */
  // padding: 24px 0;
  min-height: calc(100vh - 140px);
  /* tweak: header+footer */
  display: flex;
  justify-content: center;
  align-items: center;
}

.page-face {
  transform-style: preserve-3d;
  backface-visibility: hidden;
  will-change: transform, opacity;
}

/* Flip transition */
.flip-enter-active,
.flip-leave-active {
  // transition: transform 520ms ease, opacity 320ms ease;
  transition: transform 620ms cubic-bezier(.22, .61, .36, 1),
    opacity 400ms ease;
}

.flip-enter-from {
  transform: rotateY(90deg);
  opacity: 0;
}

.flip-leave-to {
  transform: rotateY(-90deg);
  opacity: 0;
}

/* General Styles */

.header {
  padding-top: 20px;
  top: 0;
  width: 100%;
  z-index: 1000;
}

.logo {
  width: 275px;
}

span {
  font-size: 12px;
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: auto;
}

.nav-menu {
  display: flex;
  gap: 20px;
  /* Space between links */
}

.menu-links {
  display: flex;
  gap: 20px;
}

.menu-top,
.menu-work-card,
.menu-socials,
.nav-icon,
.menu-link b,
.menu-backdrop {
  display: none;
}

.nav-menu a {
  text-decoration: none;
  font-size: 16px;
  font-weight: 500;
  color: #ffffff;
  /* Link color white */
  transition: color 0.3s ease;
}

.nav-menu a:hover {
  color: #28517c;
  /* Change color on hover */
}

.cta-button {
  background-color: #fff;
  color: #000;
  padding: 10px 20px;
  border-radius: 20px;
  border: none;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.cta-button:hover {
  background-color: #007bff;
  /* Button hover background */
  color: #fff;
  /* Button hover text color */
}

.menu-toggle {
  display: none;
}

footer {
  text-align: center;
  padding: 0px 0px 10px 0px;
  font-size: 14px;
  opacity: 0.6;
}

body.menu-open {
  overflow: hidden;
}

.nav-con-box {
  display: flex;
  gap: 1rem;
  align-items: center;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .nav-container {
    max-width: 960px;
    padding: 12px;
  }

  .logo {
    width: 200px;
  }
}

@media (max-width: 768px) {
  .header {
    padding-top: 0;
    min-height: 65px;
  }

  .nav-container {
    position: relative;
    min-height: 65px;
    padding: 0 12px;
  }

  .logo {
    width: 130px;
  }

  .menu-toggle {
    display: flex;
    width: 32px;
    height: 32px;
    padding: 6px;
    border: 0;
    background: transparent;
    cursor: pointer;
    flex-direction: column;
    justify-content: center;
    gap: 5px;
  }

  .menu-toggle span {
    display: block;
    width: 20px;
    height: 2px;
    background: #fff;
    border-radius: 1px;
  }

  .menu-backdrop {
    display: block;
    position: fixed;
    inset: 0;
    z-index: 1100;
    border: 0;
    background: rgba(0, 0, 0, 0.68);
    opacity: 0;
    pointer-events: none;
    transition: opacity 360ms ease;
  }

  .menu-backdrop.is-open {
    opacity: 1;
    pointer-events: auto;
  }

  .nav-menu {
    display: flex;
    position: fixed;
    top: 0;
    right: 0;
    z-index: 1101;
    width: min(390px, 88vw);
    min-height: 100dvh;
    padding: 1rem;
    border-left: 1px solid rgba(255, 255, 255, 0.25);
    background:
      radial-gradient(480px circle at 0% 0%, rgba(255, 255, 255, 0.08), transparent 46%),
      linear-gradient(180deg, #181818, #101010);
    flex-direction: column;
    gap: 0;
    opacity: 0;
    visibility: hidden;
    pointer-events: none;
    transform: translateX(100%);
    transition: transform 420ms cubic-bezier(.22, .61, .36, 1), opacity 300ms ease, visibility 0s linear 420ms;
  }

  .nav-menu.is-open {
    opacity: 1;
    visibility: visible;
    pointer-events: auto;
    transform: translateX(0);
    transition: transform 420ms cubic-bezier(.22, .61, .36, 1), opacity 300ms ease;
  }

  .menu-top {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    gap: 14px;
    margin-bottom: 1rem;
  }

  .menu-talk,
  .menu-work-card button {
    border: 0;
    border-radius: 999px;
    padding: 9px 18px;
    color: #111;
    background: #fff;
    font-weight: 700;
    cursor: pointer;
  }

  .menu-close {
    width: 40px;
    height: 40px;
    position: relative;
    border: 1px solid #ffffff;
    border-radius: 8px;
    background: transparent;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #ffffff;
  }

  .menu-links {
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .nav-menu .menu-link {
    display: grid;
    grid-template-columns: 32px 1fr auto;
    align-items: center;
    min-height: 61px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.16);
    color: #fff;
    font-size: 16px;
    font-weight: 650;
  }

  .nav-menu .menu-link:hover {
    color: #fff;
  }

  .nav-icon,
  .menu-link b {
    display: block;
  }

  .nav-icon {
    color: #fff;
    font-size: 24px;
    font-weight: 300;
    line-height: 1;
  }

  .menu-link b {
    color: #bbb;
    font-size: 30px;
    font-weight: 300;
  }

  .menu-work-card {
    display: flex;
    gap: 14px;
    margin-top: 20px;
    padding: 20px 16px;
    border: 1px solid rgba(255, 255, 255, 0.16);
    border-radius: 14px;
  }

  .work-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    flex: 0 0 40px;
    height: 40px;
    border: 1px solid rgba(255, 255, 255, 0.7);
    border-radius: 50%;
    font-size: 25px;
  }

  .menu-work-card h3 {
    margin: 2px 0 8px;
    font-size: 20px;
    line-height: 1.05;
  }

  .menu-work-card h3 em {
    display: block;
    color: #2c76bb;
    font-style: normal;
  }

  .menu-work-card p {
    margin: 0 0 14px;
    color: #ddd;
    font-size: 13px;
    line-height: 1.4;
  }

  .menu-work-card button {
    padding: 8px 18px;
  }

  .menu-socials {
    display: flex;
    gap: 16px;
    margin-top: auto;
    padding-top: 16px;
    border-top: 1px solid rgba(255, 255, 255, 0.2);
  }

  .menu-socials a {
    display: grid;
    place-items: center;
    width: 47px;
    height: 47px;
    border: 1px solid rgba(255, 255, 255, 0.18);
    border-radius: 8px;
    color: #fff;
    font-size: 16px;
    font-weight: 700;
    text-decoration: none;
  }

  .cta-button {
    padding: 8px 18px;
    font-size: 14px;
  }

}

@media (max-width: 768px) and (max-height: 700px) {
  .nav-menu {
    padding: 16px 22px;
    overflow-y: auto;
  }

  .menu-top {
    margin-bottom: 18px;
  }

  .nav-menu .menu-link {
    min-height: 48px;
  }

  .menu-work-card {
    margin-top: 16px;
    padding: 14px;
  }

  .work-icon {
    flex-basis: 42px;
    height: 42px;
    font-size: 21px;
  }

  .menu-work-card h3 {
    margin: 0 0 5px;
    font-size: 18px;
  }

  .menu-work-card p {
    margin-bottom: 10px;
    font-size: 12px;
  }

  .menu-work-card button {
    padding: 7px 15px;
  }

  .menu-socials {
    margin-top: 16px;
    padding-top: 12px;
  }

  .menu-socials a {
    width: 40px;
    height: 40px;
  }
}
</style>
