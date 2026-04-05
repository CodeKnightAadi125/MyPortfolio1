<script setup>
const scrollTo = (id) => {
  document.getElementById(id)?.scrollIntoView({ behavior: "smooth" });
};
</script>

<template>
  <section id="about" class="about-section">
    <div class="about-content">
      <h2 class="animated-title">About Me . . . . . . </h2>
      <p class="intro fade-in">
        I am Aditya, currently pursuing
        <strong class="accent">Electronics & Communication Engineering (ECE)</strong> from
        <strong class="entity">Dr. Harisingh Gour University</strong>, Sagar, MP.
        Alongside, I am enhancing my programming skills by learning
        <strong>Data Structures & Algorithms in Java</strong> and
        <strong>Web Development</strong>. I enjoy learning technologies that combine
        electronics with software, like drones and automation systems.
      </p>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  min-height: 80vh;
  display: flex;
  align-items: flex-start;
  justify-content: center;
  padding: 6rem 2rem 2rem 2rem;
  background-color: #ffffff;
  color: #475569;
  text-align: center;
}

.about-content { max-width: 800px; }

.animated-title {
  font-size: 3rem;
  margin-bottom: 1rem;
  display: inline-block;
  overflow: hidden;
  white-space: nowrap;
  color: #0f172a;
  border-right: 3px solid #ee5711;
  animation: typing 2s steps(20) forwards, blink 0.7s infinite step-end;
}

@keyframes typing {
  from { width: 0; }
  to   { width: 100%; }
}

@keyframes blink {
  50% { border-color: transparent; }
}

.fade-in {
  opacity: 0;
  animation: fadeUp 2s forwards;
  animation-delay: 2s;
  font-size: 1.8rem;
  line-height: 1.8;
  margin-top: 1rem;
  color: #475569;
}

@keyframes fadeUp {
  0%   { opacity: 0; transform: translateY(20px); }
  100% { opacity: 1; transform: translateY(0); }
}

strong.accent { color: #ee5711; }

strong.entity {
  color: #0f172a;
  font-weight: 600;
}
</style>