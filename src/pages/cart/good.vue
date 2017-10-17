<template>
  <div class="car_item">
    <div class="car_choose">
      <!--<p>-->
        <input :id="index" type="checkbox" class="input-box" >
        <label :for="index" :class="{'checkbox-on':item.checked === '1'}"  @click="choose(item,index)"></label>
      <!--</p>-->
    </div>
    <a :href="item.url+'/'+item.id" class="car_img">
      <img :src="item.src" height="300" width="300">
    </a>
    <div class="car_detail">
      <h3 class="pdt_title">
        <a :href="item.url">{{item.title}}</a>
      </h3>
      <p class="car_price">
        <span class="pdt_new_price">{{item.newPrice}}</span>
        <del class="pdt_old_price">{{item.oldPrice}}</del>
      </p>
    </div>
  </div>

</template>
<script type="text/javascript">
//  let data = {
//    isChecked:false
//  };
  export default {
    name: 'good',
    props: ['item','index','chooseBuy'],
//    data() {
//      return data
//    },
    methods: {
      choose: function(item,index){
//        data.isChecked = !data.isChecked;
        this.chooseBuy(item,index,this);
      }
    }

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
      label.checkbox-on{
        display: inline-block;
        width: 0.533rem;
        height: 0.533rem;
        cursor: pointer;
        background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACgAAAAoCAMAAAC7IEhfAAAAA3NCSVQICAjb4U/gAAAAh1BMVEX/////UAD/UAD/UAD/UAD/UAD/UAD/UAD/UAD/UAD/UAD/UAD/////+vj/9fD/8ev/8On/7OP/6d//5Nj/4NL/3s//2cj/1MH/zLX/w6f/wKP/upv/t5b/rYf/qID/oXb/mWb/jlr/jFj/dTb/cC//biz/bSr/aCP/XhT/Wg7/Vgn/UQL/UADQOR1YAAAALXRSTlMAESJEd4iZqrvM3e7///////////////////////////////////////////9INcYgAAAACXBIWXMAAAsSAAALEgHS3X78AAAAHHRFWHRTb2Z0d2FyZQBBZG9iZSBGaXJld29ya3MgQ1M26LyyjAAAARJJREFUOI2N1et2wiAMAOBApVZg7j7dzbn71Lz/8w0qcsKtJr/EfgcIDSkADdGpQaMLPahOQCtkb5CE6WWdzbGIeYXOTOncrLOMicp0YdJkq2LRcogLwXOJbK4bVo95TDvEkJGs5kvDSM7CcXF53iH6KXsO7N3RnN2hDyOgaz/9evyIvztQTfe5tBeH00DB0HLfl9au42gAPeFW+zjUMOEeduSPBiwchdvbbdtReGNtkD+lQ5LMmw3y97p0mh7Pq5PvR3efOXc89MBH6d3dX56dSl/hi5NXNedeYVoUXtacK4qszJ6qzpdZVriHzXPFjYXLvgr8y8W+rvwGwG8p7CbFb3v8Rgr81gzsZj9ulX4+0kf/qVXH8bP2GwMAAAAASUVORK5CYII=) no-repeat 0 0;
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

  }
</style>
