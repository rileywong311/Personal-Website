<template>
  <div style="display: flex; flex-wrap: wrap-reverse; justify-content: center; column-gap: 75px; max-width: 1200px; margin: auto;">
    <div style="width: min(500px, 90vw)">
      <h3>{{ name }}</h3>
      <slot />
    </div>
    <div>
      <iframe v-if="media && type === 'vid'" class="media shadow" allow="fullscreen;" :src="media" alt="video"/>
      <img v-else-if="media && type === 'img'" class="media shadow" :src="require(`../assets/${media}`)" alt="picture"/>
      <div v-else style="width: min(480px, 90vw); height: calc(min(480px, 90vw) / 1.77); background: black" />
      <div style="margin: 25px 0; display: flex; flex-wrap: wrap; justify-content: right; row-gap: 25px">
        <span v-for="link in links">
        <a :href="link.link" target="_blank" style="text-decoration: none; color: black">
            <span style="border: 2px solid black; border-radius: 999px; padding: 5px 25px 5px; margin-right: 15px; background: var(--a-background); color: var(--a-color)">
              {{ link.name }}
              <img src="@/assets/link.svg" style="margin-left: 5px; width: 15px; filter: invert(var(--a-invert))"/>
            </span>
          </a>
        </span>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: 'ProjectCard',
  props:  {
    media: String,
    type: String,
    name: String,
    links: Array,
  }
}
</script>


<style scoped>
.media {
  --width: min(480px, 90vw);
  
  width: var(--width);
  height: calc(var(--width) / 1.77);
  /* border: 5px solid black; */
  border: none;
  object-fit: cover;
}

img, span {
  transition: 1s
}

a:hover {
  --a-invert: 1;
  --a-color: white;
  --a-background: black;
}

</style>