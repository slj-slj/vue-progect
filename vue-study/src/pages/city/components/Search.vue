<template>
    <div>
        <div class="search">
            <input type="text" placeholder="输入城市名或拼音" class="search-city" v-model="keyword">
        </div>
        <div class="search-content" ref="search" v-show="keyword">
            <ul>
                <li class="search-item border-bottom" v-for="(item,index) of list" :key="index">{{item.name}}</li>
                <li class="search-item search-st" v-show="hasNoData">暂无匹配数据</li>
            </ul>
        </div>
    </div>
   
</template>
<script>
import Bscroll from 'better-scroll'
export default {
    name:'CitySearch',
    props: {
        cities:Object
    },
    data () {
        return {
            keyword:'',
            list:[],
            timer:null
        }
    },
    computed: {
        hasNoData(){
            return !this.list.length
        }
    },
    watch: {
        keyword(){
            if(this.timer){
                clearTimeout(this.timer)
            }
            if(!this.keyword){
                this.list = []
                return
            }
            this.timer = setTimeout(()=>{
                const result = []
                for (let i in this.cities) {
                    this.cities[i].forEach((value)=>{
                        if(value.spell.indexOf(this.keyword) > -1||value.name.indexOf(this.keyword) > -1){
                            result.push(value)
                        }
                    });
                }
                this.list = result
            },100)
        }
    },
    mounted () {
        this.scroll = new Bscroll(this.$refs.search)
    }
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/varibles.styl'
    .search
        padding 0 .1rem
        height $headerHeight
        line-height $headerHeight
        background-color $bgColor
        text-align center
        .search-city
            color:#666
            width 96%
            height .62rem
            line-height .62rem
            padding:0 .1rem
            border-radius .06rem
            box-sizing border-box
    .search-content
        overflow hidden
        position absolute
        top 1.72rem
        left 0
        right 0
        bottom 0
        background-color #fff
        z-index 1
        .search-item
            line-height .62rem
            padding-left .2rem
        .search-st
            text-align center
            line-height 5rem
            font-size 130%
            color #aaa

</style>

