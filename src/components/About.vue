<template>
  <section id="about" class="about card">
    <div class="intro-layout">
      <div class="intro-text">
        <p class="eyebrow">🎓 IT Architecture & Cloud Computing Student</p>
        <h1>Hi, I'm Ikbel Bouzouita</h1>
        <p class="lead">
          Passionate about cloud infrastructures, DevOps, and software development. I have experience in virtualization, infrastructure supervision, web development, and artificial intelligence. I'm eager to deepen my skills in digital engineering and data engineering in an international technological environment.
        </p>
      </div>

      <img
        class="profile-photo"
        src="https://media.licdn.com/dms/image/v2/C5603AQGsfEntvEOYUw/profile-displayphoto-shrink_400_400/profile-displayphoto-shrink_400_400/0/1647527165578?e=1776297600&v=beta&t=IQnvr4BR0lvzp4UtPo5YZ4yNtKrJ-gwbOH4cSviMGA0"
        alt="Ikbel Bouzouita profile photo"
        loading="lazy"
      />
    </div>
    <div class="meta">
      <span>📍 Manar 1, Tunis, 2062</span>
      <span>🗣️ Arabic (Native) · French (Good) · English (Good) · Spanish (Intermediate)</span>
      <span>✅ Available for opportunities</span>
    </div>
  </section>
</template>

<script>
export default {
  name: 'About'
}
</script>

<style scoped>
.card {
  background: linear-gradient(160deg, var(--white), var(--bg-1));
  color: var(--text-primary);
  border: 1px solid var(--line);
  border-radius: 18px;
  padding: 2.5rem 2rem;
  box-shadow: var(--glow), 0 20px 45px rgba(0, 0, 0, 0.08);
}

.intro-layout {
  display: grid;
  grid-template-columns: 1fr auto;
  align-items: center;
  gap: 1.5rem;
}

.intro-text {
  min-width: 0;
}

.eyebrow {
  display: inline-block;
  padding: 0.35rem 0.8rem;
  border-radius: 999px;
  background: rgba(109, 40, 217, 0.1);
  color: var(--primary);
  font-size: 0.85rem;
  margin-bottom: 1rem;
  font-weight: 500;
}

.profile-photo {
  width: 150px;
  height: 150px;
  object-fit: cover;
  object-position: center top;
  border-radius: 999px;
  border: 3px solid var(--primary-light);
  box-shadow: 0 10px 25px rgba(109, 40, 217, 0.15);
  margin-inline: auto;
}

h1 {
  margin: 0;
  font-size: clamp(1.8rem, 4vw, 3rem);
  color: var(--text-primary);
  font-weight: 700;
  line-height: 1.2;
}

.lead {
  margin-top: 1rem;
  font-size: 1.1rem;
  line-height: 1.8;
  max-width: 900px;
  color: var(--text-secondary);
}

.meta {
  margin-top: 1.4rem;
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}

.meta span {
  padding: 0.35rem 0.65rem;
  border-radius: 8px;
  background: rgba(109, 40, 217, 0.05);
  border: 1px solid var(--line);
  font-size: 0.9rem;
  color: var(--text-secondary);
}

@media (max-width: 768px) {
  .intro-layout {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .intro-text {
    order: 2;
  }

  .profile-photo {
    order: 1;
  }

  .profile-photo {
    width: 96px;
    height: 96px;
  }

  .meta {
    justify-content: center;
  }
}
</style>