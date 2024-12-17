<template>
  <div style="display: flex; flex-wrap: wrap; gap: 55px" :class="{center: center}">
    <a href="https://www.linkedin.com/in/rileywong510/" target="_blank">
      <img src="@/assets/logos/LinkedIn.svg" alt="LinkedIn link" />
    </a>
    <a href="https://github.com/rileywong311" target="_blank">
      <img src="@/assets/logos/GitHub.svg" alt="GitHub link" />
    </a>
    <a href="https://www.youtube.com/@rileywong510" target="_blank">
      <img src="@/assets/logos/YouTube.svg" alt="YouTube link" />
    </a>
  </div>
</template>

<script>
export default {
  name: 'FormCard',
  props: {
    center: Boolean
  }
  }
</script>


<style scoped>
img {
  width: 50px;
  transition: 0.15s;
}

img:hover {
  transform: scale(1.1);
}

.center {
  justify-content: center;
}

@media screen and (max-width: 425px) {
  img {
    width: 40px;
  }
}

</style>
