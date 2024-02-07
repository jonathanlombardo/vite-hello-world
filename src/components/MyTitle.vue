<script>
export default {
  props: {
    msg: String,
  },
};
</script>

<template>
  <h1 class="text-center m-0 py-2 px-5">{{ msg }}</h1>
</template>

<style scoped>
h1 {
  background-image: linear-gradient(to right, #ffe14d, #ffa800);
  border-radius: 10px;
}
</style>
