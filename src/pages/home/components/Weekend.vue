<template>
    <div class="recommend">
        <div class="recommend-title">
            周末去哪儿
        </div>
        <ul>
            <router-link to='/detail' tag="li"   class="list-item" v-for="item in recommedList" :key="item.id">
                <div class="item-img">
                    <img  :src="item.imgUrl" alt="">
                </div>

                <div class="item-info">
                        <div class="info-title">{{item.title}}</div>  
                        <div class="info-comment">{{item.comment}}</div>                      
                </div>
            </router-link>
        </ul>   
    </div>
</template>

<script>

export default {
    name:'HomeWeekend',
    data(){
        return{
            recommedList:[
                {
                    id:'001',
                    imgUrl:'https://imgs.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
                    title:'京城溜娃必去',
                    comment:'德智体美劳全面发展的亲子日，这些地方该去看看…'
                },
                {
                    id:'002',
                    imgUrl:'https://imgs.qunarzz.com/sight/source/1811/7e/476589267ebb41.jpg_r_640x214_bf599709.jpg',
                    title:'京城周末撒欢',
                    comment:'在帝都过周末，不仅仅是城中游！'
                },
                {
                    id:'003',
                    imgUrl:'https://imgs.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
                    title:'帝都必打卡',
                    comment:'来北京必去的景点非这些地方莫属'
                }
            ]
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';
@import '~styles/mixin.styl';

    div{
        box-sizing :border-box;
    }
    .recommend{
        background-color :#fff;
    }
    .recommend-title{
        width :100%;
        height :.8rem;
        line-height :.8rem;
        font-size :.28rem;
        padding-left :.2rem;
        background :#eee
    }
   
    
    .list-item .item-img{
        width :100%;
        height :0;
        padding-bottom :37.1%;
       
    }
      .list-item .item-img img {
          width :100%;
         
      }
    .list-item .item-info{
        padding :.14rem .2rem .2rem;
    }

   
    .item-info .info-title{
        width :190px;
        height :.48rem;
        line-height :.48rem;
        font-size :.28rem;
        ellipsis();
    }
    .item-info .info-comment{
        width :100%;
        height :.42rem;
        line-height :.42rem;
        font-size :.24rem;
        color :$lightTxt;
    }

</style>