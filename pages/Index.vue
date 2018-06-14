<template>
    <div class="page-index">
    </div>
</template>

<script>
function setState(store) {}

export default {
    name: 'index',
    metaInfo: {
        title: 'Home',
        titleTemplate: '%s - Lavas',
        meta: [
            {name: 'keywords', content: 'lavas PWA'},
            {name: 'description', content: '基于 Vue 的 PWA 解决方案，帮助开发者快速搭建 PWA 应用，解决接入 PWA 的各种问题'}
        ]
    },
    async asyncData({store, route}) {
        console.log(store)
        console.log(route)
        setState(store);
    },
    data(){
        return {
            active:0
        }
    },
    created(){
        this.watchActive()
    },
    methods:{
        watchActive(){
            console.log(this.active)
            if(this.active === 0){
                this.$router.push(`/home/${this.active}`)
            }
        }
    },
    watch:{
        "active":"watchActive"
    }
};
</script>

<style lang="stylus" scoped>

.page-index
    display flex
    justify-content center
    align-items center
    flex-direction column

    h2
        font-size 46px
        font-weight 500
        margin-bottom 0

</style>
