<template>
    <div class="icons-wrapper">
        <div class="wrapper">
            <swiper ref="mySwiper" :options="swiperOptions">
                
                <swiper-slide v-for="(page,idx) in pages" :key="idx">
                    <router-link tag="div" 
                                class="icon-box" 
                                v-for="item in page" 
                                :key="item.id"
                                :to="'/detail/' +item.id">
                        <div class="icon-img-box" >
                        <img class="icon-img" :src="item.imgUrl" alt="">
                        </div>
                        <p class="icon-text">{{item.description}}</p>
                    </router-link>
                    
                </swiper-slide>

                <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
        </div>
        
    </div>
</template>

<script>

export default {
    name:'HomeIcons',
    props:{
        iconsList:Array
    },
    data(){
        return{
            swiperOptions: {
                pagination:'.swiper-pagination'
                
            },
            
        }
    },
    computed:{
        pages:function(){
            var pages = [];
            this.iconsList.forEach(function(elem,idx){
                var page = Math.floor(idx/8);
                if(!pages[page]){
                    pages[page] = [];
                }
                pages[page].push(elem);
            })
            return pages;
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';
@import '~styles/mixin.styl';
.wrapper >>> .swiper-container{
    overflow :visible
}

.icons-wrapper {
    width:100%;
    padding-top :2%;
    padding-bottom:12%;
    margin-bottom :.2rem;
    background-color :#fff;
}
.icons-wrapper .icon-box{
    position:relative;
    float:left;
    width:25%;
    height:0;
    padding-bottom:25%;
    
}
.icons-wrapper .icon-img-box{
    position :absolute;
   
    left :0;
    right:0;
    bottom :.52rem;
    
}
.icons-wrapper .icon-box .icon-text{
    position :absolute;
    bottom :.1rem;
    left :0;
    right :0;
    height :.44rem;
    line-height :.44rem;
    text-align :center;
    color :$darkTxt;
    ellipsis();
}
.icons-wrapper .icon-img-box img{
    display :block;
    height :1.1rem;
    margin : 0 auto;
}
.wrapper{
    position :relative;
}
.wrapper .swiper-pagination{
     position :absolute;
     bottom :-.5rem;
     left :0;
}
</style>