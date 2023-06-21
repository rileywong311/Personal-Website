<template>
  <div class="shadow" style="display: flex; flex-wrap: wrap-reverse; justify-content: center; column-gap: 75px; max-width: 1200px; margin: auto; padding: 25px; border-radius: 25px">
    <div style="width: min(500px, 90vw)">
      <h3>{{ name }}</h3>
      <p>{{ description }}</p>
    </div>
    <div>
      <iframe v-if="media" class="video" allow="fullscreen;" :src="media" />
      <div v-else style="width: min(480px, 90vw); height: calc(min(480px, 90vw) / 1.77); background: black" />
      <div style="text-align: right; margin: 25px 0">
        <a :href="link" target="_blank" style="text-decoration: none; color: black">
          <span style="border: 2px solid black; border-radius: 999px; padding: 5px 25px 5px; margin: 25px">
            GitHub
            <img src="@/assets/link.svg" style="margin-left: 5px; width: 15px"/>
          </span>
        </a>
      </div>
    </div>
  </div>
</template>



<script>
export default {
  name: 'ProjectCard',
  props:  {
    media: String,
    name: String,
    description: String,
    link: String,
  }
}
</script>



<style scoped>
.video {
  --width: min(480px, 90vw);
  
  width: var(--width);
  height: calc(var(--width) / 1.77);
  /* border: 5px solid black; */
  border: none;
}

</style>