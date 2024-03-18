<script setup lang="ts">
defineProps<{
  msg: string
  msg2: string
}>()
</script>

<template>
  <div class="greetings">
    <h1 class="coral center-text">{{ msg }}</h1>
    <h1 class="coral center-text">{{ msg2 }}</h1>

  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 1.6rem;
  position: relative;
  top: -10px;
}

.coral {
  color: #FFA6AF
}

.center-text{
  text-align: center!important;
}


.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
