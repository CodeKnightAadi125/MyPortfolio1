<script setup>
import { ref } from 'vue'

const links = [
  { name: 'Home',     id: 'home'     },
  { name: 'About',    id: 'about'    },
  { name: 'Skills',   id: 'skills'   },
  { name: 'Projects', id: 'projects' },
  { name: 'Contact',  id: 'contact'  },
]

const menuOpen = ref(false)

const scrollTo = (id) => {
  document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' })
  menuOpen.value = false
}

const toggleMenu = () => {
  menuOpen.value = !menuOpen.value
}
</script>

<template>
  <nav class="navbar">

    <div class="logo-block" @click="scrollTo('home')">
      <h2 class="logo">Aadi<span class="logo-accent">.dev</span></h2>
      <p class="logo-tag">ECE · Web Dev · DSA</p>
    </div>

    <ul class="nav-links">
      <li v-for="link in links" :key="link.name">
        <a @click="scrollTo(link.id)">{{ link.name }}</a>
      </li>
    </ul>

    <button
      class="hamburger"
      @click="toggleMenu"
      :class="{ open: menuOpen }"
      aria-label="Toggle menu"
    >
      <span></span>
      <span></span>
      <span></span>
    </button>

    <div class="mobile-menu" :class="{ open: menuOpen }">
      <ul>
        <li v-for="link in links" :key="link.name">
          <a @click="scrollTo(link.id)">{{ link.name }}</a>
        </li>
      </ul>
    </div>

  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 999;
  background: rgba(255, 255, 255, 0.88);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border-bottom: 1px solid #f0e8e0;
  padding: 0.8rem 3rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-block {
  display: flex;
  flex-direction: column;
  gap: 0.15rem;
  cursor: pointer;
  flex-shrink: 0;
}

.logo {
  font-size: 1.9rem;
  font-weight: 800;
  color: #1c1209;
  letter-spacing: -0.03em;
  line-height: 1;
  margin: 0;
}

.logo-accent { color: #ee5711; }

.logo-tag {
  font-size: 1rem;
  color: hsla(60, 2%, 34%, 0.921);
  font-weight: 600;
  letter-spacing: 0.04em;
  margin: 0;
  padding-left: 2px;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 2.5rem;
  margin: 0;
  padding: 0;
}

.nav-links a {
  text-decoration: none;
  color: #57534e;
  cursor: pointer;
  position: relative;
  font-size: 1.1rem;
  font-weight: 600;
  transition: color 0.25s;
}

.nav-links a:hover { color: #1c1209; }

.nav-links a::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  background: #ee5711;
  left: 0;
  bottom: -4px;
  border-radius: 2px;
  transition: width 0.3s ease;
}

.nav-links a:hover::after { width: 100%; }

.hamburger {
  display: none;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 5px;
  width: 36px;
  height: 36px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
  z-index: 1001;
  background-color:#ee5711;
  border-radius: 8px;
}

.hamburger span {
  display: block;
  width: 22px;
  height: 2px;
  background: #1c1209;
  border-radius: 2px;
  transition: transform 0.3s ease, opacity 0.3s ease;
  transform-origin:center;
}

.hamburger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.hamburger.open span:nth-child(2) { opacity: 0; transform: scaleX(0); }
.hamburger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

/* Replace .mobile-menu styles with this */
.mobile-menu {
  display: none;
  position: fixed;
  top: 60px;          /* sits just below navbar */
  right: 1.5rem;      /* aligned to the right */
  width: 180px;
  background: #ffffff;
  border: 1px solid #f0e8e0;
  border-radius: 12px;
  box-shadow: 0 8px 24px rgba(0,0,0,0.08);
  z-index: 1000;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.25s ease, transform 0.25s ease;
  transform: translateY(-8px);
}

.mobile-menu.open {
  opacity: 1;
  pointer-events: all;
  transform: translateY(0);
}

.mobile-menu ul {
  list-style: none;
  padding: 0.5rem 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0;
}

.mobile-menu a {
  display: block;
  font-size: 1rem;        /* smaller than before */
  font-weight: 600;
  color: #1c1209;
  text-decoration: none;
  cursor: pointer;
  padding: 0.75rem 1.2rem;
  transition: color 0.2s, background 0.2s;
  border-radius: 8px;
}

.mobile-menu a:hover {
  color: #ee5711;
  background: #fff3ec;
}

@media (max-width: 640px) {
  .navbar { padding: 0.8rem 1.5rem; }
  .nav-links { display: none; }
  .hamburger { display: flex; }
  .mobile-menu { display: flex; }
  .logo { font-size: 1.5rem; }
  .logo-tag { display: none; }
}
</style>