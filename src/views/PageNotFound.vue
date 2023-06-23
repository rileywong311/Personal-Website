<template>
  <div style="margin: auto; padding: 200px 5%; text-align: center">
    <h1 style="font-weight: 300">
      <span style="font-weight: 400">404</span>
      <br />
      Page not found.
    </h1>
    <router-link to="/"><div style="margin-top: 75px"><span class="return">Go to main page.</span></div></router-link>
  </div>
</template>


<style scoped>
  .return {
    color: var(--secondary);
    padding: 15px 45px 15px;
    border-radius: 999px;
    transition: 0.5s;
  }

  .return:hover {
    box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
  }
</style>