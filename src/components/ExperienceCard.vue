<template>
  <div style="padding: 10px 0 10px">
    <span style="display: grid; grid-template-columns: auto 1fr">
      <span style="grid-column: 1">{{ dates }}</span>
      <svg style="grid-column: 2; margin-left: 15px; width: 100%; height: 22.5px">
        <line x1="0%" y1="50%" x2="90%" y2="50%" style="stroke: black"/>
      </svg>
    </span>
    <div class="experience-info">
      <h3 style="margin: 5px 0">{{ position }}</h3>
      <h4>{{ org }}</h4>
      <slot />
    </div>
  </div>

  <!-- <div class="shadow" style="width: min(500px, 90vw); border-radius: 30px; background: var(--background); padding: 25px">
    <div style="text-align: right; color: var(--secondary); font-weight: 200;">
      <p style="margin: 0">{{ dates }}</p>
    </div>
    <div>
      <h3 style="margin: 5px 0">{{ position }}</h3>
      <h4>{{ org }}</h4>
      <slot />
    </div>
  </div> -->
</template>


<script>
export default {
  name: 'ExperienceCard',
  props:  {
    dates: String,
    position: String,
    org: String,
    description: String,
    link: String,
  }
}
</script>

<style scoped>
.experience-info {
  margin-left: 30px;
}

@media screen and (max-width: 1200px) {
  .experience-info {
    margin-left: 0px;
  }
}

</style>