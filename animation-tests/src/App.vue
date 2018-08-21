<template>
  <div id="app">    
    <transition name="menu-popover">
      <div v-if="showFirstText">
        More time. More Money.
      </div>
    </transition>    
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {      
      showFirstText: false
    }    
  },
  methods: {
    toggleShowFirstText() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          this.showFirstText = true;
        }, 3000),
        reject({ 
          // An error occurred.
        });
      });      
    }
  },
  mounted() {
    this.toggleShowFirstText();
  }
}
</script>

<style>
  .menu-popover-enter,
  .menu-popover-leave-to {    
    opacity: 0;    
    transform: translateX(300px);
  }

  .menu-popover-enter-to,
  .menu-popover-leave {    
    opacity: 1;    
    transform: translateX(0px);
  }

  .menu-popover-enter-active,
  .menu-popover-leave-active {    
    transition-property: transform,opacity;
    transition-duration: 2s;
    transition-timing-function: ease-out;
  }
</style>
