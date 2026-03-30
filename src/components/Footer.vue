<template>
  <footer class="main-footer">
    <p>© {{ currentYear }} Ikbel Bouzouita — IT Architecture & Cloud Computing Student ⚡</p>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      currentYear: new Date().getFullYear()
    };
  }
}
</script>

<style scoped>
.main-footer {
  margin-top: 2rem;
  padding: 1.25rem;
  text-align: center;
  color: var(--text-muted);
  background: var(--bg-1);
  border-top: 1px solid var(--line);
  box-shadow: 0 -10px 35px rgba(109, 40, 217, 0.08);
}

p {
  margin: 0;
  font-size: 0.95rem;
  letter-spacing: 0.3px;
}
</style>