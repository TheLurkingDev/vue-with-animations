<template>
  <div id="app">
    {{ text }} 
    <button @click="toggleShow">Show</button>
    <transition name="menu-popover">
      <ul class="menu-popover" v-if="show">
        <li>Payments</li>
        <li>Subscriptions</li>
        <li>Connect</li>
      </ul>
    </transition>    
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      text: 'Hello world.',
      show: false
    }    
  },
  methods: {
    toggleShow() {
      this.show = !this.show;
    }
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
