<template>
    <div class="sw-wrapper">
        <swiper v-if="isSwiperShow" :options="swiperOptions">
    
            <swiper-slide  v-for="item in swiperList" :key="item.id">
                <img class="swiper-img" :src="item.imgUrl" alt="">
            </swiper-slide>

            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
  
</template>

<script>
export default {
    name:'HomeSwiper',
    props:{
        swiperList: Array
    },
    data(){
        return{

            swiperOptions: {
                pagination:'.swiper-pagination',
                loop : true,
                autoplay : 3000,
            },
            // swiperList:[
            //     {
            //         id:'001',
            //         imgUrl:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1741962166,2931076665&fm=26&gp=0.jpg'
            //     },
            //     {
            //         id:'002',
            //         imgUrl:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3007711878,1609779217&fm=26&gp=0.jpg'
            //     },
            //     {
            //         id:'003',
            //         imgUrl:'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=3546725438,588397521&fm=26&gp=0.jpg'
            //     },
            //     {
            //         id:'004',
            //         imgUrl:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=4279633132,3623017093&fm=15&gp=0.jpg'
            //     },

            // ]
        }
    },
    computed:{
        isSwiperShow:function(){
            return this.swiperList.length
        }
    }
}
</script>

<style lang="stylus" scoped>
    .sw-wrapper >>> .swiper-pagination-bullet-active{
        background-color:rgba(255,255,255,.6);
    }
    .sw-wrapper{
        overflow:hidden;
        width:100%;
        height:100%;
        background:#eee;
    }
    .sw-wrapper .swiper-img{
        width:100%;
        height:100%;
    }
</style>