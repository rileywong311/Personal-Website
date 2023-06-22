<template>
  <div style="margin: auto; padding: 200px 5%; text-align: center">
    <h1 style="font-weight: 300">
      📩
      <br />
      Recieved. 
      <br />
      <span style="color: var(--secondary); font-weight: 500;">Thank you!</span>
    </h1>
    <router-link to="/"><div style="margin-top: 75px"><span class="return">Go back to main page.</span></div></router-link>
  </div>
</template>

<style>
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