<script>
import inputTag from "./components/inputTag.vue"

export default {
  components : {
    inputTag,
  },
  methods : {
    handleOnTagsChange(tags) {
      console.log(tags);
    }
  }
}
</script>

<template>
  <div class="container">
    <inputTag :onTagsChange="handleOnTagsChange" />
  </div>
</template>

<style scoped>
  body{
    background-color: #51e5b8;
  }

  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 300px;
  }
</style>
