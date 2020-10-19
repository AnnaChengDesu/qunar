<template>
    <div class="recommend">
        <div class="recommend-title">
            <span class="iconfont icon-heart">&#xe85c;</span>
            猜你喜欢
        </div>
        <ul>
            <router-link v-for="item in recommendList" 
                         :to="'/detail/' +item.id" 
                         tag="li"   
                         class="list-item" 
                         :key="item.id">
                <div class="item-img">
                    <img  :src="item.imgUrl" alt="">
                </div>
                <div class="item-img-tag">{{item.tag}}</div>
                <div class="item-info">
                    <div class="inner-box">
                        <div class="info-title">{{item.title}}</div>
                        <div class="info-commend">
                            <span class="iconfont icon-star">&#xe60a;</span>
                            <span class="iconfont icon-star">&#xe60a;</span>
                            <span class="iconfont icon-star">&#xe60a;</span>
                            <span class="iconfont icon-star">&#xe60a;</span>
                            <span class="iconfont icon-star">&#xe60a;</span>
                            <span class="comment-num">{{item.commentNum}}条评论</span>
                        </div>
                        <div class="info-price">
                            <span class="price">￥<em class="">{{item.price}}</em></span>起

                            <span class="district">{{item.district}}</span>
                        </div>
                    </div>
                </div>
            </router-link>
        </ul>   
    </div>
</template>

<script>

export default {
    name:'HomeRecommend',
    props:['recommendList'],
    
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
        font-size :.32rem;
        

    }
    .recommend-title  .icon-heart{
        color : #e5404f;
        margin-left :.1rem;
    }
    .list-item{
        position:relative;
        display :flex;
        width :100%;
        height :2.4rem;
        
    }
    .list-item .item-img{
        
        width :2.4rem;
        height :2.4rem;
        padding :.2rem;
    }
      .list-item .item-img img {
          width :100%;
          height :100%;
      }
      .list-item .item-img-tag{
          position :absolute;
          top:.2rem;
          left :.2rem;
          width :1.02rem;
          height :.38rem;
          background-image :url(https://img1.qunarzz.com/piao/fusion/1802/20/2ba6d10b17972e02.png);
          background-size :100% 100%;
          font-size :.25rem;
          line-height :.38rem;
          color :#fff;
      }
    .list-item .item-info{
        flex :1;
        padding :.4rem .1rem;
    }

    .list-item .item-info .inner-box{
        width :100%;
        height :100%;
    }
    .item-info .inner-box .info-title{
        width :190px;
        height :.6rem;
        line-height :.6rem;
        font-size :.32rem;
        ellipsis();
    }
    .item-info .inner-box .info-commend{
        width :100%;
        height :.4rem;
        line-height :.4rem;
        font-size :.24rem;
    }
    .inner-box .info-commend .icon-star{
        font-size :.2rem;
        color :#ffd436;
    }

    .inner-box .info-commend .comment-num{
        color :$lightTxt;
    }
    .inner-box .info-price{
        position :relative;
        padding-top :.15rem;
    }
    .inner-box .info-price .price{
        
        color :#ff8300
    }
    .inner-box .info-price .price em {
        font-size :.4rem;
    }
    .inner-box .info-price .district{
        position :absolute;
        right : .24rem;
        bottom :.05rem;
        font-size :.24rem;
    }
</style>