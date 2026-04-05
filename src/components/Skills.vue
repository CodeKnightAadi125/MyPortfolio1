<template>
  <section id="skills" class="skills-section">
    <div class="skills-content">
      <h2 class="skills-title">Skills</h2>
      <div class="categories-wrapper">
        <div
          class="category-block"
          v-for="(category, index) in skillCategories"
          :key="index"
          :style="{ animationDelay: index * 0.2 + 's' }"
        >
          <div class="category-header">
            <span class="category-icon">{{ category.icon }}</span>
            <h3 class="category-title">{{ category.title }}</h3>
          </div>
          <div class="pills-row">
            <span
              class="pill"
              v-for="(skill, i) in category.skills"
              :key="skill"
              :style="{ animationDelay: (index * 0.2 + i * 0.08) + 's' }"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skillCategories = [
  { icon: '☕', title: 'Languages', skills: ['Java', 'JavaScript', 'C'] },
  { icon: '🌐', title: 'Web Development', skills: ['HTML', 'CSS', 'Vue.js', 'Tailwind CSS'] },
  { icon: '🧠', title: 'DSA / CS Fundamentals', skills: ['Arrays', 'Linked Lists', 'Recursion', 'Sorting', 'Searching'] },
  { icon: '🛠️', title: 'Tools', skills: ['Git', 'GitHub', 'VS Code', 'Eclipse'] },
]
</script>

<style scoped>
.skills-section {
  background: linear-gradient(160deg, #ffffff 0%, #fff3ec 60%, #ffe8d6 100%);
  padding: 5rem 2rem;
  color: #0f172a;
}

.skills-content {
  max-width: 860px;
  margin: 0 auto;
  text-align: center;
}

.skills-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 0.5rem;
  display: inline-block;
}

.skills-title::after {
  content: '';
  display: block;
  width: 50px;
  height: 3px;
  background-color: #ee5711;
  margin: 0.5rem auto 2.5rem;
  border-radius: 2px;
}

.categories-wrapper {
  display: flex;
  flex-direction: column;
  gap: 2.5rem;
  text-align: left;
}

.category-block { animation: fadeUp 0.6s ease both; }

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}

.category-header {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  margin-bottom: 0.9rem;
}

.category-icon { font-size: 1.3rem; }

.category-title {
  font-size: 1.6rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.1em;
}

.pills-row {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
}

.pill {
  display: inline-block;
  padding: 0.5rem 1.2rem;
  border-radius: 999px;
  font-size: 0.9rem;
  font-weight: 500;
  background-color: #ffffff;
  color: #1e293b;
  border: 1.5px solid #e2d5cc;
  box-shadow: 0 1px 3px rgba(238, 87, 17, 0.07);
  transition: all 0.25s ease;
  animation: popIn 0.4s ease both;
  cursor: default;
}

.pill:hover {
  background-color: #ee5711;
  color: #ffffff;
  border-color: #ee5711;
  transform: translateY(-2px);
}

@keyframes popIn {
  from { opacity: 0; transform: scale(0.85); }
  to   { opacity: 1; transform: scale(1); }
}
</style>