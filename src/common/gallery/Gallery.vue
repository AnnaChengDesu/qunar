<template>
    <div class="gallery-container" @click="handleCloseGallery" >
        <div class="img-wrapper">
            
        <swiper :options="swiperOptions">
            <swiper-slide v-for="(item,index) in imgsList" :key="index">
                <img class="gallery-img" :src="item">
            </swiper-slide>
           
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    
        </div>
    </div>
</template>

<script>

export default {
    name:'Gallery',
    props:['imgsList'],
    data(){
        return{
            swiperOptions: {
                pagination:'.swiper-pagination',
                paginationType : 'fraction',
                observer:true,
                observeParents:true
            }
        }
    },
    methods: {
        handleCloseGallery:function(){
            this.$emit('closeGallery');
        }
    },
}
</script>

<style lang="stylus" scoped>
div{
    display :flex;
}
.gallery-container >>> .swiper-container{
    width :100%;
    height :100%;  
    position :absolute;
    top :0;
    left :0;
}
.gallery-container >>> .swiper-slide{
    flex-direction :column;
    justify-content :center;
}
.gallery-container{
    display :flex;
    flex-direction :column;
    justify-content :center;
    position :fixed;
    top:0;
    left :0;
    bottom :0;
    right :0;
    background :rgba(0,0,0,.9rem);
    z-index :99
}
.gallery-container .img-wrapper{
    width :100%;
    height :0;
    padding-bottom :100%;
}
.gallery-container .img-wrapper img{
    width :100%;
}
.gallery-container .img-wrapper .swiper-pagination{
    bottom :.48rem;
    justify-content :center;
    color :#fff
}
</style>