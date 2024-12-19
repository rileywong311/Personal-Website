<template>
  <div style="pointer-events: none; position: absolute; top: 0; width: 100%; height: 100%">
    <div v-if="clicks>0" class="clicks">{{ clicks }}</div>
    <div v-if="clicks>9" @click="openShop" class="shop-icon"><img src="@/assets/clicker/shop.png" style="width: 100%" alt="Shop" /></div>
    <dialog ref="dialog" class="shop" style="position: relative; padding: 10px">
      <div style="width: 100%; height: 100%">
        <span class="shop-close" @click="closeShop">&#10006;</span>
        <br />
        <br />
        <div>
          <div v-for="role in Object.keys(roles)"
          class="shop-item" :class="getPrice(role) <= clicks ? 'can-buy' : 'cannot-buy'"
          @click="purchase(role)">
            <span style="width: 40%">{{ roles[role]['name'] }} (x{{ roles[role]['count'] }})</span>
            <span>Next Cost: {{ getPrice(role) }}</span>
          </div>
        </div>
        <br />
        <br />
        <span class="delete" @click="deleteClicks">Delete Clicks</span>
        <br />
        <br />
      </div>
    </dialog>
  </div>
</template>


<script>
export default {
  name: 'Clicker',
  props:  {
    clicks: Number,
  },
  data: () => {
    return {
      roles: {
        'interns': {name: 'Interns', count: 0, price: 15},
        'juniors': {name: 'Junior Developers', count: 0, price: 100},
        'seniors': {name: 'Senior Developers', count: 0, price: 500},
        'leads': {name: 'Tech Leads', count: 0, price: 5000},
        'ctos': {name: 'CTOs', count: 0, price: 25000},
        'ceos': {name: 'CEOs', count: 0, price: 100000},
        'rileys': {name: 'Riley Wong', count: 0, price: 99999999},
      }
    }
  },
  async mounted() {
    this.$refs.dialog.addEventListener('click', (e) => {
      if(e.target == this.$refs.dialog) {
        this.closeShop();
      }
    })
  },
  methods: {
    getPrice(role) {
      return Math.round(this.roles[role]['price'] * (1.15 ** this.roles[role]['count']))
    },
    async purchase(role) {
      if (this.getPrice(role) > this.clicks) {
        return;
      }
      this.$emit('spend-clicks', this.getPrice(role))
      this.roles[role]['count'] += 1;
      localStorage.setItem(role, this.roles[role]['count']);
    },
    async openShop() {
      this.$refs.dialog.showModal()
      for (let role in this.roles) {
        this.roles[role]['count'] = Number(localStorage.getItem(role))
      }
    },
    async closeShop() {
      this.$refs.dialog.close()
    },
    async deleteClicks() {
      this.closeShop()
      for (let role in this.roles) {
        localStorage.removeItem(role);
      }
      this.$emit('delete-clicks');
    },
  }
}
</script>


<style scoped>
  .clicks {
    pointer-events: all;
    position: absolute;
    top: 0;
    right: 0;
  }

  .shop-icon {
    pointer-events: all;
    position: absolute;
    top: 0;
    left: 0;
    width: 30px;
  }

  .shop-close {
    pointer-events: all;
    position: absolute;
    top: 5px;
    right: 10px;
    font-size: 35px;
  }

  .delete {
    pointer-events: all;
    color: darkred;
    font-size: 1rem;
  }

  .shop-icon:hover,
  .shop-close:hover,
  .delete:hover {
    cursor: pointer;
    transform: scale(0.9);
  }

  .shop {
    pointer-events: all;
    width: min(500px, 90vw);
    height: min(400px, 75vw);
  }
  
  .shop-item {
    display: flex;
    gap: 15px;
    padding: 20px 10px 20px;
    border-top: 2px solid black;
  }

  .shop-item:hover {
    cursor: pointer;
    filter: brightness(1.3)
  }

  .shop-item:last-child {
    border-bottom: 2px solid black;
  }

  .can-buy {
    background-color: green;
  }

  .cannot-buy {
    background-color: darkred;
  }

</style>