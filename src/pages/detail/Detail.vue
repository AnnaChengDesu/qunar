<template>
    <div>
        <detail-banner></detail-banner>
        <detail-header></detail-header>
        <div class="content-box"></div>
    </div>
</template>

<script>
import Banner from './components/banner'
import Header from './components/Header'
export default {
    name:'Detail',
    components:{
        'detail-banner':Banner,
        'detail-header':Header
    }
}
</script>

<style lang="stylus" scoped>
.content-box{
    height :50rem;
}
</style>