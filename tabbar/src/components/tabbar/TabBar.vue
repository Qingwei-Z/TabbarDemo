<template>
  <div id="tab-bar">
      <slot></slot>
  </div>
</template>

<script>
export default {
  name:"TabBar"
}
</script>

<style>
#tab-bar{
    display: flex;
    background-color: #f2f2f2;

    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;

    /* box-shadow: 
    h-shadow v-shadow blur     spread    color inset;
    水平     垂直     模糊距离  阴影尺寸   颜色
    */
    box-shadow: 0 -3px 1px rgba(100, 100, 100, .1);

  }
  
  

</style>