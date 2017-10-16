<template>
  <div class="buyCar">
    <ul>
      <li v-for="(product,index) in hotProducts" class="car_item">
        <!--<div class="car_item">-->
        <div class="car_choose"><p><input :id="index" type="checkbox" class="input-box"><label :for="index"></label></p>
        </div>
        <a :href="product.url+'/'+product.id" class="car_img">
          <img :src="product.src" height="300" width="300">
        </a>
        <div class="car_detail">
          <h3 class="pdt_title">
            <a :href="product.url">{{product.title}}</a>
          </h3>
          <p class="car_price">
            <span class="pdt_new_price">{{product.newPrice}}</span>
            <del class="pdt_old_price">{{product.oldPrice}}</del>
          </p>
        </div>
        <!--</div>-->
      </li>
    </ul>
    <div class="footer">
      <div class="f-fx">
          <div class="ft-cb">
            <input id="cb-footer" type="checkbox" class="input-cb">
            <label for="cb-footer" class="footer-cb"></label>
          </div>
          <div class="qx" >全选</div>
          <div class="pay">
              <span class="hj">合计：</span>
              <span class="money">￥0.0</span>
          </div>
          <div class="btn" >
            <span>结算</span>
            <span>(</span><span>0</span><span>)</span>
          </div>
        </div>
    </div>
  </div>
</template>
<script type="text/javascript">
  export default {
    name: 'good',
    props: ['hotProducts']
  }
</script>
<style lang="scss">
  .buyCar {
    .car_choose {
      .input-box {
        display: none;
      }
      p {
        flex: 1;
      }
      label {
        display: inline-block;
        width: 0.533rem;
        height: 0.533rem;
        cursor: pointer;
        background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACgAAAAoBAMAAAB+0KVeAAAAA3NCSVQICAjb4U/gAAAALVBMVEX///+hprehprehprehprehprehprehprehprehprehprehprehprehprehprd0XKVXAAAAD3RSTlMAESIzRGZ3iJmqu8zd7v8zDtSdAAAACXBIWXMAAAsSAAALEgHS3X78AAAAHHRFWHRTb2Z0d2FyZQBBZG9iZSBGaXJld29ya3MgQ1M26LyyjAAAAPVJREFUKJF1k88KQUEUxg/yrygLG4m8gLKVUlZ28gTyAsrCTskLKLL3BFKysJO1IixkYSMkrr5nMPeie+/0OYuZ6TedP3PONyKWecpjYNWKicO8PVh2zDjYSIHTWi0PmzaAeUkk3gYOP5YAhp9THhh8kyww+90XYHySJXG3w3cwtfYRqjb042FuAdyc1dVQV2sWTScMYm96G+KyhfL34uKGRWQkhL4bhtGVFHJu6MNOKlpIFfQqnbsOFZlcdVh5yuasw/RLsNVhFIKlDiP/IHOniWhJtHj6TNoQ2jraZDoOPjg6YioGLhsqMCpFLloub/oR9C/zBsU0n4PhpWahAAAAAElFTkSuQmCC) no-repeat 0 0;
        background-size: 0.52rem;
      }
    }
    .car_item {
      background: #f5f5f5;
      display: flex;
      padding: 10px 20px;
      margin-bottom: 5px;
    }
    .car_img {
      flex: 1;
      border: 10px solid #fff;
      img {
        width: 80px;
        height: 80px;
      }
    }
    .car_detail {
      padding: 10px;
      box-sizing: border-box;
      flex: 5;
      .car_price {
        .pdt_new_price {
          color: #e17c72;
          font-size: 17px;
          &:first-letter {
            font-size: 12px;
          }
        }
      }
    }
    .footer{
      cursor: pointer;
      position: fixed;
      left: 0;
      right: 0;
      bottom: 0;
      border-top: .8rem solid transparent;
      display: flex;
      .input-cb{
        /*display: none;*/
      }
      .footer-cb{
        display: inline-block;
        width: 0.533rem;
        height: 0.533rem;
        cursor: pointer;
        background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACgAAAAoBAMAAAB+0KVeAAAAA3NCSVQICAjb4U/gAAAALVBMVEX///+hprehprehprehprehprehprehprehprehprehprehprehprehprehprd0XKVXAAAAD3RSTlMAESIzRGZ3iJmqu8zd7v8zDtSdAAAACXBIWXMAAAsSAAALEgHS3X78AAAAHHRFWHRTb2Z0d2FyZQBBZG9iZSBGaXJld29ya3MgQ1M26LyyjAAAAPVJREFUKJF1k88KQUEUxg/yrygLG4m8gLKVUlZ28gTyAsrCTskLKLL3BFKysJO1IixkYSMkrr5nMPeie+/0OYuZ6TedP3PONyKWecpjYNWKicO8PVh2zDjYSIHTWi0PmzaAeUkk3gYOP5YAhp9THhh8kyww+90XYHySJXG3w3cwtfYRqjb042FuAdyc1dVQV2sWTScMYm96G+KyhfL34uKGRWQkhL4bhtGVFHJu6MNOKlpIFfQqnbsOFZlcdVh5yuasw/RLsNVhFIKlDiP/IHOniWhJtHj6TNoQ2jraZDoOPjg6YioGLhsqMCpFLloub/oR9C/zBsU0n4PhpWahAAAAAElFTkSuQmCC) no-repeat 0 0;
        background-size: 0.52rem;
      }
      .f-fx{
        width: 100%;
        height: 50px;
        background: #fff;
        border-top: 1px solid #e7e7e7;
        display: flex;
        line-height:50px;
        .qx{
          flex: 1;
          font-size: 15px;
          justify-content: center;
          align-items: center;
          text-align: center;
        }
        .pay{
          flex: 2;
          align-items: center;
          text-align: right;
          padding: 0 10px;
          .money{
            color: #e17c72;
            font-size: 18px;
          }

        }
        .btn{
          flex: 1;
          text-align: center;
          color: #fff;
          background: #e17c72;
        }
      }
    }

  }
</style>
