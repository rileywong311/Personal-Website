<template>
  <div>
    <a href="https://www.linkedin.com/in/rileywong510/" target="_blank">
      <img src="@/assets/logos/LinkedIn.svg" alt="LinkedIn link" />
    </a>
    <a href="https://github.com/rileywong311" target="_blank">
      <img src="@/assets/logos/GitHub.svg" alt="GitHub link" />
    </a>
    <a href="https://www.youtube.com/@rileywong8319" target="_blank">
      <img src="@/assets/logos/YouTube.svg" alt="YouTube link" />
    </a>
  </div>
</template>

<style scoped>
img {
  width: 50px;
  margin-right: 60px;
  transition: 0.8s;
}

img:hover {
  transform: scale(1.2);
}

@media screen and (max-width: 425px) {
  img {
    width: 40px;
    margin-right: 50px;
  }
}

</style>
