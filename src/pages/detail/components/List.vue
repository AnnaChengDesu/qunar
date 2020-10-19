<template>
    <div class="list">
        <div class="list-item" v-for="(item,index) in list" :key="index">
            
            <div class="list-item-title border-bottom">
                <span class="item-title-icon"></span>
                {{item.title}}
            </div>
            <div class="item-ticket" v-for="(ticketItem,index) in item.ticket" :key="index">
                <div class="ticket-title">
                    {{ticketItem.title}}
                </div>
                <div class="ticket-orderTime">
                    <span class="iconfont time-icon" >&#xe65d;</span>
                    {{ticketItem.orderTime}}
                </div>
                <div class="title-right">
                    <span class="iconfont">&#xe71b;</span>
                    {{ticketItem.right}}
                </div>

                <div class="ticket-price">
                    <div class="price">￥{{ticketItem.price}}</div>
                    <button class="price-order" v-show="item.isShow">立即预定</button>
                </div>
            </div>
        </div>
        <div class="list-price">
            <div class="list-item-title border-bottom">
                <span class="item-title-icon"></span>
                景区票价
            </div>
            <div class="item-ticket" >
                <div class="ticket-title">
                    成人票
                </div>
                <div class="ticket-price">
                    <div class="price">￥220</div>
                </div>
            </div>
            <div class="item-ticket" >
                <div class="ticket-title">
                    成人票（当日订）
                </div>
                <div class="ticket-price">
                    <div class="price">￥220</div>
                </div>
            </div>
            <div class="item-ticket" >
                <div class="ticket-title">
                    儿童票
                </div>
                <div class="ticket-price">
                    <div class="price">￥120</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'DetailList',
    props:{
        list:Array
    },
    data:function(){
        return{
            
        }
    },
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';
div{
    box-sizing :border-box;
}
.list-item-title {
	width: 100%;
	height: .8rem;
	line-height: .8rem;
	font-size: .36rem;
    font-weight :bold
	padding: 0 .2rem;
	text-indent: .4rem;
}

.list-item-title .item-title-icon {
	display: inline-block;
    position: absolute;
    width: .36rem;
    height: .36rem;
    top: .26rem;
    left: .2rem;
    background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
    margin-right: .1rem;
    background-size: .4rem 3rem;
}
.item-ticket{
    position :relative;
    font-size :.3rem;
    width :100%;
    padding :.2rem .3rem;
    line-height :.52rem;
    border-bottom :.05rem solid #eee;
}
.time-icon{
    font-size :.26rem;
}
.item-ticket .ticket-title{
    width :85%;
    line-height :.4rem;
}
.title-right{
    color :$bgColor;
}

.item-ticket .ticket-price {
    position :absolute
    top:25%;
    right :.2rem;
}
.item-ticket .ticket-price .price{
    font-size :.36rem;
    color :orange;
    padding :0 0 0 .15rem ;
}
.item-ticket .ticket-price .price-order{
    color :#fff;
    padding :.1rem .1rem;
    background :orange;
    border-radius :.3rem;
    font-size :.28rem;
}
</style>