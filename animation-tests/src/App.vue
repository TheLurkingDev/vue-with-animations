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
    transform: rotateZ(50deg);
  }

  .menu-popover-enter-to,
  .menu-popover-leave {    
    opacity: 1;    
    transform: rotateZ(0deg);
  }

  .menu-popover-enter-active,
  .menu-popover-leave-active {
    transition: opacity, transform 3s ease-out;
  }
</style>
