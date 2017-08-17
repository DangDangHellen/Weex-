<template>
  <div>
    <div class='imgs' v-for="index in imgList" v-if="data === index.id">
      <image class='mainImg' :src='index.src'></image>
    </div>
      <ToolBar v-on:onClick="handleClick"></ToolBar>   
  </div>
</template>
<style scoped>
  .img { width:100%; }
  .mainImg { width:750px; height: 1200px; }
</style>
<script>
  //import ChildFoo from './components/ChildFoo.vue'
  import ToolBar from './components/ToolBar.vue'
  export default {
    components: {
      //ChildFoo,
      ToolBar
    },
    data: {
      data: 0,
      imgList: [{
          src: 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1502951398859&di=dc4de37c4b70e1125c8ce2197cf56668&imgtype=0&src=http%3A%2F%2Fpic25.nipic.com%2F20121210%2F10296294_202307038355_2.jpg',
          id: 0
        }, {
          src: 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1503546141&di=906dad75daf58b97b9d40beabc61173e&imgtype=jpg&er=1&src=http%3A%2F%2Fi-7.vcimg.com%2Ftrim%2Fe0e59ad2e396578195834745f1c1d1b3188951%2Ftrim.jpg',
          id: 1
        }, {
          src: 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1502951444584&di=8fa66548a105054fb96ea985a8ea2507&imgtype=0&src=http%3A%2F%2Fi3.letvimg.com%2Fcms%2F201409%2F15%2F206fafc2f6f246d7af25eadf076bb153.jpg',
          id: 2
        }, {
          src: 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1502951356398&di=0d4ea994caa02fe94babc18478cbab4c&imgtype=0&src=http%3A%2F%2Fimg.lenovomm.com%2Fs3%2Fimg%2Fapp-img-lestore%2F0593-2015-07-04060507-1436004307836.jpg%3FisCompress%3Dtrue%26width%3D320%26height%3D480%26quantity%3D1%26rotate%3Dtrue',
          id: 3
        }]
    },
    methods: {
      handleClick( data ) {
        //console.log('父组件');
        //console.log(data.data);
        this.data = data.data;
      }
    }
  }
</script>
