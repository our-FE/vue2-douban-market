<template>
  <div class="cart">
    <header-bar></header-bar>
    <nav-bar></nav-bar>
    <good :cart="cart"></good>
  </div>
</template>

<script type="text/javascript">
  import {mapState, mapActions} from 'vuex'
  import HeaderBar from '../../components/header.vue'
  import NavBar from '../../components/nav.vue'
  import Good from './good.vue'


  export default {
    computed: {
      //映射State
      ...mapState([
        'cart',
      ])
    },
    mounted() {
      //获取热门商品列表
      this.getCart();
    },
    methods: {
      ...mapActions(['getCart'])
    },
    components: {
      HeaderBar,
      NavBar,
      Good
    }
  }
</script>
<style scoped>
  .login_false .login_false{
    text-align: center;
    padding: 1rem 0;
    border-bottom: 1px solid #9d9d9d;
    background-color: #f8f8fe;
  }
  .login_false .login_entry{
    padding: 20px;
    text-align: center;
    border-bottom: 1px solid #9d9d9d;
    background-color: #fff;
  }
  .login_false .login_entry .login_tip2{
    color: #4a4a4a;
  }
  .login_false .login_entry .btn_login{
    display: block;
    padding: 10px 0;
    text-align: center;
    margin: 15px 0;
    color: #fff;
    font-size: 14px;
    border-radius: 5px;
    background-color: #68cb78;
  }
  .login_false .login_entry .btn_regist{
    color: #9d9d9d;
  }
  .login_false .login_entry .btn_regist a{
    color: #68cb78;
  }
  .login_false .anonymous{
    text-align: center;
    color: #9b9b9b;
    padding-top: 2rem;
  }
  .login_false .anonymous p{
    padding: 5px 0;
  }
  .login_false .anonymous a{
    color: #68cb78;
  }
</style>
