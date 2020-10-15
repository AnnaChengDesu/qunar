<template>
    <div class="icons-wrapper">
        <div class="wrapper">
            <swiper ref="mySwiper" :options="swiperOptions">
                
                <swiper-slide v-for="(page,idx) in pages" :key="idx">
                    <div class="icon-box" v-for="item in page" :key="item.id">
                    <div class="icon-img-box" >
                    <img class="icon-img" :src="item.iconUrl" alt="">
                    </div>
                    <p class="icon-text">{{item.text}}</p>
                    </div>
                </swiper-slide>

                <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
        </div>
        
    </div>
</template>

<script>

export default {
    name:'HomeIcons',
    data(){
        return{
            swiperOptions: {
                pagination:'.swiper-pagination'
                
            },
            iconList:[
                {
                    id:'001',
                    iconUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/158387fe5376294f3776d01358d6b73b.png',
                    text:'景点门票'
                },
                {
                    id:'002',
                    iconUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/69e8b07cb2d438c5530aebd4c8e3abd3.png',
                    text:'一日游'
                },
                {
                    id:'003',
                    iconUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/b526fe902327e59922374bf24927a87c.png',
                    text:'颐和园'
                },
                {
                    id:'004',
                    iconUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/ba632a670497c3393a864595c5411ca1.png',
                    text:'八达岭长城'
                },
                {
                    id:'005',
                    iconUrl:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/5ffcd4a916f764f678263b27c1e2e00c.png',
                    text:'天坛公园'
                },
                {
                    id:'006',
                    iconUrl:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/d706a4d71c57c53ee8863b75a7af30cf.png',
                    text:'圆明园'
                },
                {
                    id:'007',
                    iconUrl:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/bd121884123cceb4da978047423421ce.png',
                    text:'恭王府'
                },
                {
                    id:'008',
                    iconUrl:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/aba25fb84648c130561afa5398d3552a.png',
                    text:'北野动物园'
                },
                {
                    id:'009',
                    iconUrl:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/1d15805633ee19ea51246ff7b0ee216d.png',
                    text:'景山公园'
                },
                {
                    id:'010',
                    iconUrl:'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/aba25fb84648c130561afa5398d3552a.png',
                    text:'北京动物园'
                }
            ]
        }
    },
    computed:{
        pages:function(){
            var pages = [];
            this.iconList.forEach(function(elem,idx){
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
    top:0;
    left :0;
    right:0;
    bottom :.44rem;
    
}
.icons-wrapper .icon-box .icon-text{
    position :absolute;
    bottom :0;
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
    height :100%;
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