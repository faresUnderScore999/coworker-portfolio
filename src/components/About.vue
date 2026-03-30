<template>
  <section id="about" class="about">
    <div class="intro-layout">
      <div class="intro-text">
        <span class="eyebrow">🎓 IT Architecture & Cloud Computing Student</span>
        <h1>Hi, I'm Ikbel Bouzouita</h1>
        <p class="lead">
          Passionate about cloud infrastructures, DevOps, and software development. 
          I have experience in virtualization, infrastructure supervision, web development, 
          and artificial intelligence. I'm eager to deepen my skills in digital engineering 
          and data engineering in an international technological environment.
        </p>
      </div>
      <div class="profile-wrapper">
        <img 
          class="profile-photo" 
          src="https://media.licdn.com/dms/image/v2/C5603AQGsfEntvEOYUw/profile-displayphoto-shrink_400_400/profile-displayphoto-shrink_400_400/0/1647527165578?e=1776297600&v=beta&t=IQnvr4BR0lvzp4UtPo5YZ4yNtKrJ-gwbOH4cSviMGA0" 
          alt="Ikbel Bouzouita profile photo" 
          loading="lazy" 
        />
        <div class="profile-badge">Open to Work</div>
      </div>
    </div>
    <div class="meta">
      <span class="meta-item">📍 Manar 1, Tunis, 2062</span>
      <span class="meta-item">🗣️ Arabic (Native) · French (Good) · English (Good) · Spanish (Intermediate)</span>
      <span class="meta-item available">✅ Available for opportunities</span>
    </div>
  </section>
</template>

<script>
export default {
  name: 'About'
}
</script>

<style scoped>
.about {
  background: linear-gradient(145deg, var(--white), var(--primary-50));
}

.intro-layout {
  display: grid;
  grid-template-columns: 1fr auto;
  align-items: center;
  gap: 2.5rem;
}

.intro-text {
  min-width: 0;
}

.eyebrow {
  display: inline-block;
  padding: 0.4rem 1rem;
  border-radius: var(--radius-full);
  background: var(--primary-100);
  color: var(--primary-dark);
  font-size: 0.85rem;
  font-weight: 600;
  margin-bottom: 1rem;
  letter-spacing: 0.3px;
}

.profile-wrapper {
  position: relative;
}

.profile-photo {
  width: 160px;
  height: 160px;
  object-fit: cover;
  object-position: center top;
  border-radius: var(--radius-xl);
  border: 4px solid var(--white);
  box-shadow: var(--shadow-lg), 0 0 0 4px var(--primary-100);
  transition: transform var(--transition-base), box-shadow var(--transition-base);
}

.profile-photo:hover {
  transform: scale(1.03) rotate(1deg);
  box-shadow: var(--shadow-lg), 0 0 0 6px var(--primary-light);
}

.profile-badge {
  position: absolute;
  bottom: -8px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--secondary);
  color: var(--white);
  font-size: 0.75rem;
  font-weight: 600;
  padding: 0.35rem 0.85rem;
  border-radius: var(--radius-full);
  white-space: nowrap;
  box-shadow: var(--shadow-md);
}

h1 {
  margin: 0;
  font-size: clamp(1.8rem, 4vw, 2.75rem);
  color: var(--text-primary);
  font-weight: 700;
  line-height: 1.2;
}

.lead {
  margin-top: 1rem;
  font-size: 1.1rem;
  line-height: 1.75;
  max-width: 800px;
  color: var(--text-secondary);
}

.meta {
  margin-top: 1.5rem;
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
}

.meta-item {
  padding: 0.45rem 0.85rem;
  border-radius: var(--radius-md);
  background: var(--panel);
  border: 1px solid var(--line-light);
  font-size: 0.9rem;
  color: var(--text-secondary);
  transition: all var(--transition-base);
}

.meta-item:hover {
  background: var(--panel-strong);
  border-color: var(--primary-light);
}

.meta-item.available {
  background: rgba(13, 148, 136, 0.1);
  border-color: rgba(13, 148, 136, 0.2);
  color: var(--secondary-dark);
  font-weight: 500;
}

@media (max-width: 768px) {
  .intro-layout {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 1.5rem;
  }

  .intro-text {
    order: 2;
  }

  .profile-wrapper {
    order: 1;
  }

  .profile-photo {
    width: 120px;
    height: 120px;
  }

  .meta {
    justify-content: center;
  }

  .meta-item {
    font-size: 0.85rem;
  }
}
</style>