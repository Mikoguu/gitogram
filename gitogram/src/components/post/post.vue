<template>
  <div class="c-post">
    <div class="x-container">
      <div class="post-header">
        <slot name="post-header"/>
      </div>
      <div class="post-content">
          <slot name="post-content"/>
      </div>
    </div>
  </div>
</template>

<style lang="scss" src="./post.scss"></style>