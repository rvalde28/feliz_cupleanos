<template>
    <div id="app">
        <flicking v-model="index" @move-end="onMoveEnd">
            <div class="panel">Panel 1</div>
            <div class="panel">Panel 2</div>
            <div class="panel">Panel 3</div>
        </flicking>
    </div>
  </template>
  
  <script>
  import Flicking from "@egjs/vue3-flicking";
  
  export default {
    components: {
      Flicking,
    },
    data() {
      return {
        index: 0,
      };
    },
  };
  </script>
  
  <style>
  .panel {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  </style>