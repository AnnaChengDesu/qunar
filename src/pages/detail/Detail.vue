<template>
    <div>
        <detail-banner></detail-banner>
        <detail-header></detail-header>
        <detail-list :list="list"></detail-list>
        <div class="content-box"></div>
    </div>
</template>

<script>
import Banner from './components/banner'
import Header from './components/Header'
import List from './components/List'
export default {
    name:'Detail',
    data:function(){
        return{
            list:[
                {
                    title:'促销',
                    children:[
                        {
                            title:'峨眉山一日游'
                        },{
                            title:'峨眉山一日游'
                        },{
                            title:'峨眉山一日游'
                        }
                    ]
                },{
                    title:'门票'
                },{
                    title:'金顶索道'
                },{
                    title:'万年寺索道'
                }
            ]
        }
    },
    components:{
        'detail-banner':Banner,
        'detail-header':Header,
        'detail-list':List
    }
}
</script>

<style lang="stylus" scoped>
.content-box{
    height :50rem;
}
</style>