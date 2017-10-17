<template>
  <div class="cart">
    <header-bar></header-bar>
    <nav-bar></nav-bar>
    <div class="buyCar">
      <ul>
        <li v-for="(item,index) in cart">
          <good :item="item" :index="index" :chooseBuy="chooseBuy"></good>
        </li>
      </ul>
    </div>
    <div class="footer">
      <div class="f-fx">
        <div class="ft-cb">
          <input id="cb-footer" type="checkbox" class="input-cb">
          <label for="cb-footer" class="footer-cb" ></label>
        </div>
        <div class="qx">全选</div>
        <div class="pay">
          <span class="hj">合计：</span>
          <span class="money">￥0.0</span>
        </div>
        <div class="btn">
          <span>结算</span>
          <span>(</span><span>0</span><span>)</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
  import {mapState, mapActions} from 'vuex'
  import HeaderBar from '../../components/header.vue'
  import NavBar from '../../components/nav.vue'
  import Good from './good.vue'
  import vue from 'vue'

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
      ...mapActions(['getCart']),
      chooseBuy: function (item,index,that) {
        if (item) {
          let checked = item.checked;
          // 勾选

          item.checked = checked === '1' ? '0' : '1';
          this.cart[index] = item;
          //this.$set('cart['+index+']','checked',checked);
          vue.set(this.cart,this.cart);
        } else {
          console.log('缺少所需参数')
        }
      }
    },
    components: {
      HeaderBar,
      NavBar,
      Good
    }
  }
</script>
<style scoped lang="scss">
  .footer {
    cursor: pointer;
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
    border-top: .8rem solid transparent;
    display: flex;

    .input-cb {
      /*display: none;*/
    }

    .footer-cb {
      display: inline-block;
      width: 0.533rem;
      height: 0.533rem;
      cursor: pointer;
      background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACgAAAAoBAMAAAB+0KVeAAAAA3NCSVQICAjb4U/gAAAALVBMVEX///+hprehprehprehprehprehprehprehprehprehprehprehprehprehprd0XKVXAAAAD3RSTlMAESIzRGZ3iJmqu8zd7v8zDtSdAAAACXBIWXMAAAsSAAALEgHS3X78AAAAHHRFWHRTb2Z0d2FyZQBBZG9iZSBGaXJld29ya3MgQ1M26LyyjAAAAPVJREFUKJF1k88KQUEUxg/yrygLG4m8gLKVUlZ28gTyAsrCTskLKLL3BFKysJO1IixkYSMkrr5nMPeie+/0OYuZ6TedP3PONyKWecpjYNWKicO8PVh2zDjYSIHTWi0PmzaAeUkk3gYOP5YAhp9THhh8kyww+90XYHySJXG3w3cwtfYRqjb042FuAdyc1dVQV2sWTScMYm96G+KyhfL34uKGRWQkhL4bhtGVFHJu6MNOKlpIFfQqnbsOFZlcdVh5yuasw/RLsNVhFIKlDiP/IHOniWhJtHj6TNoQ2jraZDoOPjg6YioGLhsqMCpFLloub/oR9C/zBsU0n4PhpWahAAAAAElFTkSuQmCC) no-repeat 0 0;
      background-size: 0.52rem;
    }

    .f-fx {
      width: 100%;
      height: 50px;
      background: #fff;
      border-top: 1px solid #e7e7e7;
      display: flex;
      line-height: 50px;

      .qx {
        flex: 1;
        font-size: 15px;
        justify-content: center;
        align-items: center;
        text-align: center;
      }

      .pay {
        flex: 2;
        align-items: center;
        text-align: right;
        padding: 0 10px;

        .money {
          color: #e17c72;
          font-size: 18px;
        }

      }
      .btn {
        flex: 1;
        text-align: center;
        color: #fff;
        background: #e17c72;
      }

    }
  }
</style>
