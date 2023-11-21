<template>
  <div class="c-post-item">
    <button class="post-header">
      <img :src="avatar" class="post-header-img" alt="username avatar">
      <div class="post-header-username">{{ username }}</div>
    </button>
      <div class="post-content">
        <h2>{{ framework }}</h2>
      </div>
  </div>
</template>

<script>
export default {
  props: {
    avatar: {
      type: String,
      required: true
    },
    username: {
      type: String,
      required: true
    },
    framework: {
      type: String,
      required: true
    },
    framework: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped src="./postItem.scss"></style>