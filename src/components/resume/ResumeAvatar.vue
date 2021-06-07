<template>
    <div class="avatar">
        <img :src="block.text">
      </div>
</template>

<script>
export default {
  props: ['block']
}
</script>

<style scoped>
  .avatar {
    display: flex;
    justify-content: center;
  }

  .avatar img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
</style>