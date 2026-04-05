<script setup>
const scrollTo = (id) => {
  document.getElementById(id)?.scrollIntoView({ behavior: "smooth" });
};
</script>

<template>
  <section id="home" class="hero">
    <div class="hero-content">
      <div class="left">
        <div class="badge">👋 ECE + Web Dev</div>
        <h1>Hi, I'm <span class="accent">Aadi</span></h1>
        <p class="subtitle">Web Dev & DSA Enthusiast</p>
        <p class="meta">Electronics & Communication Engineering<br/>Dr. Harisingh Gour University, Sagar MP</p>
        <div class="btn-row">
          <button class="btn-main" @click="scrollTo('about')">About Me →</button>
          <button class="btn-outline" @click="scrollTo('projects')">My Projects</button>
        </div>
      </div>
      <div class="avatar">🧑‍💻</div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #ffffff;
  padding: 0 3rem;
  border-bottom: 1px solid #f0e8e0;
}

.hero-content {
  max-width: 860px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 3rem;
}

.left { flex: 1; }

.badge {
  display: inline-block;
  padding: 0.35rem 1rem;
  background: #fff3ec;
  color: #ee5711;
  border: 1px solid #ffd5b8;
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 600;
  margin-bottom: 1.2rem;
  letter-spacing: 0.03em;
}

h1 {
  font-size: 3.2rem;
  font-weight: 700;
  color: #1c1209;
  line-height: 1.1;
  margin-bottom: 0.6rem;
}

.accent { color: #ee5711; }

.subtitle {
  font-size: 1.2rem;
  color: #57534e;
  font-weight: 500;
  margin-bottom: 0.5rem;
}

.meta {
  font-size: 0.9rem;
  color: #a8a29e;
  line-height: 1.7;
  margin-bottom: 2rem;
}

.btn-row {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn-main {
  padding: 0.75rem 1.8rem;
  background: #ee5711;
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.25s, transform 0.2s;
}

.btn-main:hover {
  background: #d44e0f;
  transform: translateY(-2px);
}

.btn-outline {
  padding: 0.75rem 1.8rem;
  background: transparent;
  color: #ee5711;
  border: 1.5px solid #ee5711;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.25s;
}

.btn-outline:hover {
  background: #fff3ec;
  transform: translateY(-2px);
}

.avatar {
  width: 220px;
  height: 220px;
  border-radius: 50%;
  background: linear-gradient(135deg, #fff3ec 0%, #ffd0b0 100%);
  border: 3px solid #ee5711;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 5rem;
  flex-shrink: 0;
  animation: floatY 3.5s ease-in-out infinite;
}

@keyframes floatY {
  0%, 100% { transform: translateY(0); }
  50%       { transform: translateY(-12px); }
}

@media (max-width: 640px) {
  .hero { padding: 5rem 1.5rem 3rem; }
  .hero-content { flex-direction: column-reverse; align-items: center; text-align: center; }
  .btn-row { justify-content: center; }
  .avatar { width: 150px; height: 150px; font-size: 3.5rem; }
  h1 { font-size: 2.4rem; }
}
</style>