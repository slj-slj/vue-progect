<template>
    <div>
        <detail-banner 
            :sightName="sightName" 
            :bannerImg="bannerImg" 
            :gallaryImgs="gallaryImgs"
        ></detail-banner>
        <detail-header></detail-header>
        <div class="content">
            <detail-card></detail-card>
            <detail-list :list="List"></detail-list>
        </div>
    </div>
</template>
<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import DetailCard from './components/Card'
import axios from 'axios'

export default {
    name:'Detail',
    components: {
        DetailBanner,
        DetailHeader,
        DetailList,
        DetailCard
    },
    data(){
        return{
            sightName:'',
            bannerImg:'',
            gallaryImgs:[],
            List:[]
        }
    },
    mounted () {
        this.getDetailInfo()
    },
    methods:{
        getDetailInfo(){
            axios.get('/api/detail.json',{
                params:{
                    id:this.$route.params.id
                }
            }).then(this.handleGetDatialSucc)
        },
        handleGetDatialSucc(res){
            res =res.data
            if(res.ret && res.data){
                const data =res.data
                this.sightName = data.sightName
                this.bannerImg = data.bannerImg
                this.gallaryImgs = data.gallaryImgs
                this.List = data.categoryList
                
            }
            console.log(res.data)
        }
    }
}
</script>
<style lang="stylus" scoped>
    .content
        height 10rem
</style>


