<template>
  <div class="wrapper">
    <div class='wrapperBox'>
      <div class='box' v-for='item in List'>
        <Unit :source='item.src' :text='item.text' :id='item.id' v-on:onClick="changeChannel"></Unit>
      </div>
    </div>   
  </div>
</template>

<style scoped>
  .wrapper { align-items: center; margin-top: 120px; width:100%;}
  .wrapperBox { align-items: center; margin-top: 120px; flex-direction: row; position: fixed; bottom: 0px;  width:100%; background-color: white ; padding-top:20px;}
  .box{ width: 25%; margin-left: 10px;}
  Unit {
    justify-content: center;
  }
</style>

<script>
  import Unit from './Unit.vue';
  export default {
    components: {
      Unit
    },
    data () {
      return {
        data: 0,
        List: [{
          src: 'https://github.com/DangDangHellen/Weex-/blob/master/movies.png?raw=true',
          text: '电 影',
          id: 0
        }, {
          src: 'https://github.com/DangDangHellen/Weex-/blob/master/juji.png?raw=true',
          text: '剧 集',
          id: 1
        }, {
          src: 'https://github.com/DangDangHellen/Weex-/blob/master/zongyi.png?raw=true',
          text: '综 艺',
          id: 2
        }, {
          src: 'https://github.com/DangDangHellen/Weex-/blob/master/Dongman.png?raw=true',
          text: '动 漫',
          id: 3
        }],
        imgList: [{
          src: 'https://github.com/DangDangHellen/Weex-/blob/master/movies.png?raw=true',
          id: 0
        }, {
          src: 'https://github.com/DangDangHellen/Weex-/blob/master/juji.png?raw=true',
          id: 1
        }, {
          src: 'https://github.com/DangDangHellen/Weex-/blob/master/zongyi.png?raw=true',
          id: 2
        }, {
          src: 'https://github.com/DangDangHellen/Weex-/blob/master/Dongman.png?raw=true',
          id: 3
        }]
      }
    },
    methods: {
      changeChannel: function (data) {
        //console.log('Toolbar组件');
        this.$emit('onClick', { data: data.id});
      }
    }
  }
</script>
