<template>
  <section id="projects" class="projects-section">
    <div class="projects-content">
      <h2 class="projects-title">Projects</h2>

      <div class="featured-card">
        <div class="featured-badge">⭐ Featured Project</div>
        <div class="featured-body">
          <div class="featured-left">
            <h3 class="card-title">KaizenLife — Daily Habit Tracker</h3>
            <p class="card-desc">
              Kaizen means <em>continuous improvement</em> in Japanese. This app
              helps you build daily habits, track streaks, and stay consistent —
              one small step at a time. Built entirely with vanilla HTML, CSS and JavaScript.
            </p>
            <div class="tag-row">
              <span class="tag">HTML</span>
              <span class="tag">CSS</span>
              <span class="tag">JavaScript</span>
            </div>
            <div class="link-row">
              <a class="btn-main" href="https://codeknightaadi125.github.io/KaizenOS/" target="_blank">Live Demo →</a>
              <a class="btn-outline" href="https://github.com/CodeKnightAadi125/KaizenOS" target="_blank">GitHub</a>
            </div>
          </div>
          <div class="featured-icon">🌱</div>
        </div>
      </div>

      <div class="cards-grid">
        <div class="small-card" v-for="project in clones" :key="project.title">
          <div class="small-icon">{{ project.icon }}</div>
          <h3 class="card-title">{{ project.title }}</h3>
          <p class="card-desc">{{ project.desc }}</p>
          <div class="tag-row">
            <span class="tag" v-for="t in project.tags" :key="t">{{ t }}</span>
          </div>
          <div class="link-row">
            <a class="btn-main" :href="project.demo" target="_blank">Live Demo →</a>
            <a class="btn-outline" :href="project.github" target="_blank">GitHub</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const clones = [
  {
    icon: '🛒',
    title: 'Amazon UI Clone',
    desc: "Frontend clone of Amazon's homepage including navbar, hero banner, product cards, and footer — fully responsive.",
    tags: ['HTML', 'CSS'],
    demo: 'https://codeknightaadi125.github.io/Amazon/',
    github: 'https://github.com/CodeKnightAadi125/Amazon',
  },
]
</script>

<style scoped>
.projects-section {
  background: #ffffff;
  padding: 5rem 2rem;
}

.projects-content {
  max-width: 900px;
  margin: 0 auto;
}

.projects-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: #1c1209;
  text-align: center;
  display: inline-block;
  width: 100%;
  margin-bottom: 0.5rem;
}

.projects-title::after {
  content: '';
  display: block;
  width: 50px;
  height: 3px;
  background: #ee5711;
  margin: 0.5rem auto 2.5rem;
  border-radius: 2px;
}

.featured-card {
  background: #fff8f5;
  border: 1.5px solid #ffd5b8;
  border-radius: 16px;
  padding: 2rem;
  margin-bottom: 1.5rem;
  transition: transform 0.3s, box-shadow 0.3s;
}

.featured-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 32px rgba(238, 87, 17, 0.1);
}

.featured-badge {
  display: inline-block;
  padding: 0.3rem 0.9rem;
  background: #fff3ec;
  color: #ee5711;
  border: 1px solid #ffd5b8;
  border-radius: 999px;
  font-size: 0.78rem;
  font-weight: 600;
  margin-bottom: 1.2rem;
}

.featured-body {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 2rem;
}

.featured-left { flex: 1; }

.featured-icon {
  font-size: 5rem;
  flex-shrink: 0;
  opacity: 0.85;
}

.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.2rem;
}

.small-card {
  background: #ffffff;
  border: 1px solid #f0e8e0;
  border-radius: 14px;
  padding: 1.5rem;
  transition: transform 0.3s, border-color 0.3s;
}

.small-card:hover {
  transform: translateY(-4px);
  border-color: #ee5711;
}

.small-icon {
  font-size: 2rem;
  margin-bottom: 0.8rem;
}

.card-title {
  font-size: 1.1rem;
  font-weight: 700;
  color: #1c1209;
  margin-bottom: 0.5rem;
}

.card-desc {
  font-size: 0.88rem;
  color: #78716c;
  line-height: 1.7;
  margin-bottom: 1rem;
}

.tag-row {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  margin-bottom: 1.2rem;
}

.tag {
  padding: 0.25rem 0.75rem;
  background: #fff3ec;
  color: #c2410c;
  border: 1px solid #ffd5b8;
  border-radius: 999px;
  font-size: 0.75rem;
  font-weight: 500;
}

.link-row {
  display: flex;
  gap: 0.7rem;
  flex-wrap: wrap;
}

.btn-main {
  padding: 0.5rem 1.2rem;
  background: #ee5711;
  color: white;
  border-radius: 8px;
  font-size: 0.85rem;
  font-weight: 600;
  text-decoration: none;
  transition: background 0.2s, transform 0.2s;
}

.btn-main:hover {
  background: #d44e0f;
  transform: translateY(-1px);
}

.btn-outline {
  padding: 0.5rem 1.2rem;
  background: transparent;
  color: #ee5711;
  border: 1.5px solid #ee5711;
  border-radius: 8px;
  font-size: 0.85rem;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.2s;
}

.btn-outline:hover {
  background: #fff3ec;
  transform: translateY(-1px);
}

@media (max-width: 600px) {
  .featured-body { flex-direction: column; }
  .featured-icon { font-size: 3rem; }
}
</style>