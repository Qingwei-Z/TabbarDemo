<template>
<div class="tab-bar-item" @click="itemClick">
  <div  v-if="!isActive" >
    <slot name="icon"></slot>
    </div>
  <div v-else>
    <slot name="icon-active"></slot>
  </div>
  <div :style="activeStyle">
    <slot name="text"></slot>
  </div>
</div>
</template>

<script>
export default {
  name :"TabBarItem",
  props:{
    path:String,
    activeColor:{
        type:String,
        default:'red'
    },

  },
  data() {
    return {
/*       isActive:true */
    }
  },
  computed:{
    isActive(){
      return this.$route.path.indexOf(this.path) !==-1
    },
    activeStyle(){
      return this.isActive ? {color: this.activeColor} : {}
    }
  },
  methods: {
    itemClick(){
      this.$router.replace(this.path).catch(err => err)
    }
  },  

}
</script>

<style>
  .tab-bar-item{
    /* 均等分 */
    flex: 1;
    /* 居中 */
    text-align: center;
    height: 49px;
    font-size: 14px;

  }

  .tab-bar-item img {
    width: 24px;
    height: 24px;
    margin-bottom: 3px;
    /* 
    属性设置元素的垂直对齐方式
    middle	把此元素放置在父元素的中部。
     */
    vertical-align: middle;
  }

  .active{
    color: red;
  }
</style>