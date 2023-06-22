<template>
  <div class="shadow" style="width: min(500px, 90vw); border-radius: 30px; background: var(--background); padding: 25px">
    <div style="text-align: right; color: var(--secondary); font-weight: 200;">
      <p style="margin: 0">{{ dates }}</p>
    </div>
    <div>
      <h3 style="margin: 5px 0">{{ role }}</h3>
      <h4>{{ org }}</h4>
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  name: 'ExperienceCard',
  props:  {
    dates: String,
    role: String,
    org: String,
    description: String,
    link: String,
  }
}
</script>

<style scoped>

</style>