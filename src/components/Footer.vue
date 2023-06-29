<template>
  <section class="footer">
    <div style="width: 12.5rem; margin: auto">
      <hr />
    </div>
    <span style="margin: 30px auto; text-align: center">Made with <span style="color: #41B883">Vue.js</span> and <span style="color: #5e88ea">CSS</span> from the ground up!</span>
    <span @click="toHero" class="copyright">2023 by Riley Wong</span>
  </section>
</template>

<script>
export default {
  name: 'Footer',
  methods: {
    async toHero() {
      await this.$router.push('/')
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }
  }
}
</script>


<style>
.footer {
  padding: 50px 5% 5px;
  background: black;
  color: white;
  display: grid;
}

.copyright {
  font-size: 0.75rem;
  margin: auto 30px 30px;
  text-align: right;
  transition: 0.25s;
}

.copyright::before {
  content: '© ';
}

.copyright:hover{
  cursor: pointer;
  color: var(--secondary)
}
</style>