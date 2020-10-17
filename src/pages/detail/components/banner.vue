<template>
    
        <div>
            <div class="banner">
            <img class="banner-img" @click="handleGallery" src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg" alt="">
            <div class="banner-info">
                <div class="banner-number">
                    <span class="iconfont banner-icon">&#xe60b;</span>
                    8</div>
                <div class="banner-title">故宫（AAA景区）</div>
            </div>
            
        </div>
        <common-gallery :imgsList="imgsList" 
                        v-show="isShow" 
                        :closeGallery="handleGallery"></common-gallery>
        </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
    name:'DetailBanner',
    components:{
        'common-gallery':CommonGallery
    },
    data:function(){
        return {
            isShow:false,
            imgsList:['//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg',
            '//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg']
        }
    },
    methods:{
        handleGallery:function(){
            this.isShow = !this.isShow;
        },
        
    }
}
</script>

<style lang="stylus" scoped>
.banner{
    position :relative;
    width :100%;
    height :0;
    padding-bottom :55%;
    background-color #eee;
    
}
.banner-img{
    width :100%;
}

.banner .banner-info{
    position :absolute;
    bottom :0;
    left :0;
    right :0;
    color :#fff;
    line-height :.4rem;
    padding :0 .2rem .2rem;
    background :linear-gradient(to bottom,rgba(0,0,0,0),rgba(0,0,0,.6))
}

.banner .banner-info .banner-number{
    width :1.2rem;
    height :.6rem;
    line-height :.6rem;  
    text-align :center;
    border-radius :.2rem;
    background-color :  rgba(0,0,0,.5);
    font-size :.24rem;
}

.banner .banner-info .banner-number .banner-icon{
    font-size :.35rem;
}

.banner .banner-info .banner-title{
    width :100%;
    height :.6rem;
    line-height :.6rem;    
    font-size :.36rem;
    text-shadow :0 1px 2px rgba(0,0,0,0,.7);
}
</style>
