<template>
    <div class="goods-info" @click="goGoodsPage()">
        <div class="goods-image">
            <img v-lazy="goodsImage" width="90%" />
        </div>
        <div class="goods-name">{{goodsName}}</div>
        <div class="goods-price">￥{{goodsPrice}}</div>
    </div>
</template>

<script>
    export default {
         props:['goodsImage','goodsName','goodsPrice','goodsId'],
         methods:{
             goGoodsPage(){
                //  跳转到详情页面并传递参数
                 this.$router.push({name:'GoodDetail',query:{goodsId:this.goodsId}})
             }
         }
    }
</script>

<style scoped>
 .goods-name{
        padding: 0 8px;
       overflow: hidden;
       text-overflow: ellipsis;
       white-space:nowrap; 
    }
</style>