<template>
    <ul class="list">
        <li 
            class="item" 
            v-for="item of letters" 
            :key="item" 
            :ref="item"
            @click="handleLetterClick"
            @touchstart="handleTouchStart"
            @touchmove="handleTouchMove"
            @touchend="handleTouchEnd"
            >
                {{item}}
            </li>
    </ul>
</template>
<script>
export default {
    name:'CityAlphabet',
    props:{
        cities:Object,

    },
    data(){
        return{
            touchStatus:false,
            startY:0,
            timer:null
        }
    },
    updated () {
        this.startY = this.$refs['A'][0].offsetTop
    },
    computed: {
        letters(){
            const letters = []
            for(let i in this.cities){
                letters.push(i)
            }
            return letters
        }
    },
    methods: {
        handleLetterClick(e){
            this.$emit('change',e.target.innerText)
        },
        handleTouchStart(){
            this.touchStatus = true
        },
        handleTouchMove(e){
            if(this.touchStatus = true){
                if(this.timer){
                    clearTimeout(this.timer)
                }
                this.timer = setTimeout(()=>{
                    const touchY = e.touches[0].clientY - 69
                    const index = Math.floor((touchY-this.startY)/20)
                    if(index >= 0 && index < this.letters.length)
                        this.$emit('change',this.letters[index])
                    // console.log(index)
                },16)
            }
        },
        handleTouchEnd(){

        }
    }
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/style/varibles.styl'
    .list
        position absolute
        top 1.72rem
        right 0
        bottom 0
        width .4rem
        display flex
        flex-direction column
        justify-content center
        .item
            line-height 0.38rem
            color $bgColor
            text-align center

</style>

