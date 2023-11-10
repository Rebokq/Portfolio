<!-- components/BottomNav.vue -->
<template>
    <div id="mySidenav" class="sidenav" @click.stop="preventClose">
      <a class="closebtn" @click="closeNav">&times;</a>
      <a href="#">About</a>
      <a href="#">Services</a>
      <a href="#">Clients</a>
      <a href="#">Contact</a>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      closeNav() {
        this.$emit('close-nav');
      },
      preventClose(event) {
        event.stopPropagation();
      }
    }
  };
  </script>
  
  <style scoped>
  /* Styles for your BottomNav component */
  .sidenav {

  background-color: rgb(0, 0, 0);

}
  </style>
  