<template>
  <div class="container">
    <router-view/>
  </div>
</template>

<script>

export default {
  name: 'HomePage',
  components: {
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lexend:wght@100;200;300;400;500;600;700;800;900&display=swap');

.container {
  max-width: 1800px;
  margin: auto;
}

html, body {
  margin: 0px;
  font-family: 'Lexend', sans-serif, system-ui;
  font-weight: 300;
  font-size: 1.1rem;

  --secondary: #004DA6;
  --background: white;
  --background2: #E3E9EF;
  --accent: #c6cbf4;
}

::selection {
  /* background: var(--yellow); */
  background: #F4F0CF;
}

h1 {
  font-size: 4rem;
  font-weight: 700;
  margin: 0;
}

h2 {
  font-size: 2.5rem;
  font-weight: 500;
  margin: 5px 0 5px;
}

h3 {
  font-size: 1.75rem;
  font-weight: 400;
}

h4 {
  font-size: 1.125rem;
  font-weight: 400;
  margin: 0;
}


p {
  line-height: 1.8;
}

.shadow {
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
  transition: 0.5s;
}

.test {
  background: red
}

@media screen and (max-width: 768px) {
  h1 {
    font-size: 2rem;
  }

  h2 {
    font-size: 1.75rem;
  }

  h3 {
    font-size: 1.25rem;
  }

  h4 {
    font-size: 1rem;
  }

  p {
    font-size: 0.875rem;
  }
}
</style>
