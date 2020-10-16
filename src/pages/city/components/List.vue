<template>
    <div class="list" ref="listWrapper">
        <div>
            <div class="hot-city" >
                <div class="hot-city-title" >
                    热门城市
                </div>
                <ul class="clearfixed" >
                    <li v-for="item in computedCities" :key="item.id" >{{item.name}}</li>
                </ul>
            </div>
            <div class="alphabet-menu">
                <div class="alphabet-menu-title">
                    字母排序
                </div>
                <ul class="clearfixed">
                    <li v-for="(item,index) in letters" :key="index" @click="handleLetter">{{item}}</li>
                    
                    
                </ul>
            </div>
            <div class="alphabet-list" v-for="(item,key) in cities" :key="key" :ref="key">
                <div class="alphabet-list-title">{{key}}</div>
                <ul class="clearfixed">
                    <li v-for="innerItem in item" :key="innerItem.id">{{innerItem.name}}</li>
                    
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
    name:'CityList',
    props:{
        hotCities:Array,
        cities:Object
    },
    data:function(){
        return{
            letter:[]
        }
    }
    ,
    computed:{
        letters:function(){
            var letters = [];
            for(var i in this.cities){
                letters.push(i);
            }
            return letters
        },
        computedCities:function(){
            var result = [],
                length = this.hotCities.length,
                item;
            
            for(var i = 0; i<length;i++){
                var resObj = {};
                item = this.hotCities[i];
                resObj.name = item.name;
                result.push(resObj);

                if(item.order===1){
                    resObj.borderType = "";
                }else if(item.order === 2||item.order === 3){
                    resObj.borderType = "border-left";
                }else if(item.order % 3 === 1){
                    resObj.borderType = 'border-top';
                }else{
                    resObj.borderType = 'bordet-topleft';
                }
            }
            return result;
        }
    },
    mounted:function(){
        this.scroll = new BScroll(this.$refs.listWrapper,{
            click:true
        });
        
    },
    methods:{
        handleLetter:function(e){
            this.letter = e.target.innerText;
        }
    },
    watch:{
        letter:function(){
            var elem = this.$refs[this.letter][0];
            this.scroll.scrollToElement(elem);
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';
div{
    box-sizing :border-box;
}

.clearfixed::after{
    content :"";
    clear :both;
    display :block;
}

.list{
    position :absolute;
    top:.88rem;
    left :0;
    right :0;
    bottom :0;
    overflow :hidden;
}

.hot-city{
    width :100%;
    height :4.32rem;
    
}

.hot-city .hot-city-title,
.alphabet-list .alphabet-list-title,
.alphabet-menu .alphabet-menu-title{
    padding :0 .2rem;
    width :100%;
    height :.72rem;
    line-height :.72rem;
    padding :0 .2rem;
    background-color :#f5f5f5;
}

.hot-city .hot-city-title
{
    width :100%;
    height :.72rem;
    line-height :.72rem;
    padding :0 .2rem;
    font-size :.26rem;
    color :$darkTxt;
    
}

.hot-city ul li {
    float :left;
    width :33.33%;
    height :.9rem;
    line-height :.9rem;
    text-align :center;
    
}

.alphabet-menu ul{
    
    margin :.3rem 0;
}

.alphabet-menu ul li {
    float :left;
    width :16.66%;
    height :.9rem;
    line-height :.9rem;
    text-align:center;
}

.alphabet-list ul li {
    float :left;
    width :25%;
    height :.9rem;
    line-height :.9rem;
    text-align :center;
}
</style>