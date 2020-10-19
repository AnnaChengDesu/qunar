<template>
    <div class="warning">
        <div class="warning-box">
            <span class="warning-icon iconfont">&#xe658;</span>
            <div class="warning-text">正在开发中...</div>
        </div>
    </div>
</template>

<script>
export default {
    name:'UnderDevelopment'
}
</script>

<style lang="stylus" scoped>
..warning{
    position :relative
}
.warning-box {
    position :absolute;
    top :50%;
    left :50%;
    margin :-1.5rem 0 0 -1.5rem;
    display :flex;
    flex-direction :column;
    align-items :center;
    justify-content: center;
    height :3rem;
    width :3rem;
    background :#eee;
    border-radius :.2rem;
}
.warning-icon{
    font-size :1.5rem;
    margin-bottom :.2rem;
    
    
}
.warning-text{
    font-size :.4rem;
    text-indent :.1rem;
}
</style>