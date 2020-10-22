<template>
    <div class="header">
        <div class="header-left">
            <span class="iconfont">&#xe624;</span>
        </div>
        <div class="header-middle">
            <span class="iconfont search-icon">&#xe632;</span>
            <div class="kw">搜索景点门票</div>
            <input type="text" class="header-input">
        </div>
        <router-link to="/city">
            <div class="header-right">
            {{this.city}}
            <span class="iconfont">&#xe6aa;</span>
            </div>
        </router-link>
        
    </div>
</template>

<script>
import { mapState} from 'vuex'
export default {
    name:'HomeHeader',
    computed:mapState([
        'city'
    ])
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';
.header{
    display: flex;
    width: 100%;
    height: 0.88rem;
    color: #fff;
    background: $bgColor;
}
.header .header-left{
    width: .8rem;
    height: 100%;
    line-height: .88rem;
    text-align: center;
}
.header .header-middle{
    position: relative;
    flex:1;
    margin: .14rem 0;
}
.header .header-middle .search-icon{
    position:absolute;
    top: .13rem;
    left: .2rem;
    color: #e4e7ea;
}

.header .header-middle .kw{
    position: absolute;
    top: .18rem;
    left: .65rem;
    color: #e4e7ea;
}

.header .header-middle .header-input{
    height: 100%;
    width: 100%;
    border-radius: .05rem;
    text-indent :.15rem;
}

.header .header-right{
    min-width:1.12rem;
    padding:0 .1rem;
    height: 100%;
    line-height: .88rem;
    text-align: center;
    color #fff;
}
</style> 