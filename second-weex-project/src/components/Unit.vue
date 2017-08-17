<template>
    <div class='box' @click="handleClick(id)">
      <image :src="source" class='barImg'></image>
      <text class="txt">{{text}}</text>
    </div>
</template>

<style scoped>
  .box {
    /*text-align:center;*/
  }
  .barImg {
    width:80px;
    height:80px;
  }
  .txt{
    text-align:center;
    width:100px;
  }
</style>

<script>
  export default {
    props: ['source', 'text', 'id'],
    methods: {
      handleClick: function (id) {
        //console.log('unit组件');
        //console.log(id);
        this.$emit('onClick', { id : id});
      }
    }
  }
</script>
