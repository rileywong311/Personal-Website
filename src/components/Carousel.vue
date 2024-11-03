<template>
  <div class="card-container" v-if="images && images.length">
    <div 
      v-for="(image, index) in images" 
      :key="index" 
      :class="['card', getCardClass(index)]"
      @click="nextCard"
    >
      <img :src="require(`@/${image}`)" alt="About me image" />
    </div>

    <!-- Bubbles positioned below the cards -->
    <div class="carousel-indicators">
      <span 
        v-for="(image, index) in images" 
        :key="'indicator-' + index" 
        :class="['indicator', { active: index === currentIndex }]" 
        @click="goToSlide(index)"
      ></span>
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
    goToSlide(index) {
      this.previousIndex = this.currentIndex;
      this.currentIndex = index;
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
  height: calc(var(--width) * 2/3 + 30px); /* Added space for indicators */
  overflow: hidden;
}

.card:hover,
.indicator:hover {
  cursor: pointer;
}

.card {
  position: absolute;
  width: 100%;
  height: calc(var(--width) * 2/3);
  top: 0;
  left: 100%;
  transition: transform 1s, opacity 1s ease-out;
}

.card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.is-top {
  left: 0;
  transform: translateX(0);
  z-index: 2;
}

.is-leaving {
  left: 0;
  opacity: 0;
  transform: translateX(-100%);
  transition: transform 1s, opacity 1s ease-out;
  z-index: 1;
}

.is-hidden {
  transform: translateX(100%);
  z-index: 0;
}

.carousel-indicators {
  display: flex;
  justify-content: center;
  position: absolute;
  bottom: 5px;
  width: 100%;
  margin-top: 10px;
}

.indicator {
  --size: 12px;
  width: var(--size);
  height: var(--size);
  margin: 0 5px;
  border: black 1px solid;
  border-radius: 50%;
  cursor: pointer;
  transition: background-color 0.3s;
}

.indicator.active {
  background-color: black;
}
</style>
