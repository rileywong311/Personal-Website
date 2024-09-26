<template>
  <div class="card-container" v-if="images && images.length">
    <div v-for="(image, index) in images" 
         :key="index" 
         :class="['card', getCardClass(index)]"
         @click="nextCard">
      <img :src="require(`@/${image}`)" alt="About me image" />
    </div>
  </div>
</template>


<script>
export default {
  name: 'Carousel',
  props: {
    images: {
      type: Array,
      required: true,
      default: () => []
    }
  },
  data() {
    return {
      currentIndex: 0,
      previousIndex: null,
      intervalId: null
    };
  },
  mounted() {
    this.startAutoShuffle();
  },
  methods: {
    nextCard() {
      this.previousIndex = this.currentIndex;
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
      this.stopAutoShuffle();
      this.startAutoShuffle();
    },
    startAutoShuffle() {
      this.intervalId = setInterval(() => {
        this.nextCard();
      }, 5000);
    },
    stopAutoShuffle() {
      clearInterval(this.intervalId);
    },
    getCardClass(index) {
      if (index === this.currentIndex) {
        return 'is-top';
      } else if (index === this.previousIndex) {
        return 'is-leaving';
      } else {
        return 'is-hidden';
      }
    }
  },
  beforeDestroy() {
    this.stopAutoShuffle();
  }
};
</script>


<style scoped>
.card-container {
  position: relative;
  --width: min(90vw, 600px);
  width: var(--width);
  height: calc(var(--width) * 2/3);
  overflow: hidden;
}

.card-container:hover {
  cursor: pointer;
}

.card {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 100%;
  transition: transform 1s, opacity 1s;
}

.card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.is-top {
  left: 0;
  /* opacity: 1; */
  transform: translateX(0);
  z-index: 2;
}

.is-leaving {
  left: 0;
  /* opacity: 0; */
  transform: translateX(-100%);
  transition: transform 1s, opacity 1s ease-out;
  z-index: 1;
}

.is-hidden {
  /* opacity: 0; */
  transform: translateX(100%);
  z-index: 0;
}
</style>
