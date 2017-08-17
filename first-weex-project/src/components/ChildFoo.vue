<template>
  <div class="wrapper" @click="update">
    <image :src="source" class="logo"></image>
    <text class="title">{{title}}</text>
  </div>
</template>

<style>
  .wrapper { align-items: center; margin-top: 120px; }
  .title { font-size: 48px; }
  .logo { width: 360px; height: 82px; }
</style>

<script>
  export default {
    props: ['source', 'title'],
    methods: {
      update: function (e) {
        this.$emit('onClick', { title : 'Weex'});
      }
    }
  }
</script>
