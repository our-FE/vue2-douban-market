<template>
  <div class="toast">{{message}}</div>
</template>
<script type="text/javascript">


  export default {
    name:'toast',
    props:['message']
  }
</script>
<style scoped>
  .toast{
    background: #000;
    opacity: 0.4;
    padding: 5px 10px;
    text-align: center;
    color: #fff;
    font-size: 12px;
  }
</style>
