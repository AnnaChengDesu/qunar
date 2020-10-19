<template>
    <div>
        <detail-banner :sightName='sightName' :bannerImage="bannerImage" :galleryImages="galleryImages"></detail-banner>
        <detail-header :sightName='sightName'></detail-header>
        <detail-list :list="categoryList"></detail-list>
    </div>
</template>

<script>
import axios from 'axios'
import Banner from './components/banner'
import Header from './components/Header'
import List from './components/List'
export default {
    name:'Detail',
    data:function(){
        return{
            sightName:'',
            bannerImage:'',
            galleryImages:[],
            categoryList:[]
        }
    },
    components:{
        'detail-banner':Banner,
        'detail-header':Header,
        'detail-list':List
    },
    methods:{
        getDetailInfo:function(){
            //axios发送请求带参数两种方式
            // axios.get('/api/detail.json?id=' +this.$route.params.id)
            // axios.get('/qunar_dist/static/mock/detail.json',{
                 axios.get('/api/detail.json',{
                 params:{
                     id:this.$route.params.id
                 }
            }).then(
                this.getDetailInfoSuccess
            )
        },
        getDetailInfoSuccess:function(res){
            if(res.data.ret&&res.data.data){
                var data = res.data.data;
                this.sightName = data.sightName;
                this.bannerImage = data.bannerImage;
                this.galleryImages = data.galleryImages;
                this.categoryList = data.categoryList;
            }
        }
    },
    mounted:function(){
        this.getDetailInfo();
    }
}
</script>

<style lang="stylus" scoped>

</style>