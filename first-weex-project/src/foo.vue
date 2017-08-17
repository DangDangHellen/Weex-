<template>
  <div>
    <div v-for='item in sourceArr'>
      <ChildFoo :source="item.logoUrl" :title='item.title' v-on:onClick="handleClick( $event, item.title )"></ChildFoo>
    </div>  
  </div>
</template>

<script>
  import ChildFoo from './components/ChildFoo.vue'
  export default {
    components: {
      ChildFoo
    },
    data: {
      sourceArr: [{
        logoUrl: 'https://alibaba.github.io/weex/img/weex_logo_blue@3x.png',
        title: 'Hello Weex'
      },
      {
        logoUrl: 'http://img.pconline.com.cn/images/upload/upc/tx/photoblog/1604/18/c19/20473373_1460987030407_mthumb.jpg',
        title: 'The First Beautiful Picture'
      },{
        logoUrl: 'http://pic1.win4000.com/wallpaper/9/573c07c8ad68e.jpg',
        title: 'The Second Beautiful Picture'
      },{
        logoUrl: 'http://img4.imgtn.bdimg.com/it/u=1809612223,3499405207&fm=26&gp=0.jpg',
        title: 'The Third Beautiful Picture'
      }]
    },
    methods: {
      handleClick( event, item) {
        console.log(event);
        for(var i = 0; i < this.sourceArr.length; i++) {
          if(this.sourceArr[i].title == item) {
            this.sourceArr[i].title = event.title;
          }
        }
      }
    }
  }
</script>
