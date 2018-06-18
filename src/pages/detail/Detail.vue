<template>
  <div class="detail">
    <detail-banner :sightName="sightName"
                   :bannerImg="bannerImg"
                   :bannerImgs="gallaryImgs"></detail-banner>
    <detail-header></detail-header>
    <detail-ticket :tickets="tickets"></detail-ticket>
  </div>
</template>

<script>
  import DetailBanner from './components/Banner'
  import DetailHeader from './components/Header'
  import DetailTicket from './components/Ticket'
  import axios from 'axios'

  export default {
    name: "Detail",
    components: {
      DetailBanner,
      DetailHeader,
      DetailTicket
    },
    data() {
      return {
        sightName: '',
        bannerImg: '',
        gallaryImgs: [],
        tickets: []
      }
    },
    methods: {
      getDetailInfo() {
        axios.get('/api/detail.json', {
          params: {
            id: this.$route.params.id
          }
        }).then(this.handleGetDataSucc)
      },
      handleGetDataSucc(res) {
        res = res.data
        if (res.ret && res.data) {
          const data = res.data
          this.sightName = data.sightName
          this.bannerImg = data.bannerImg
          this.gallaryImgs = data.gallaryImgs
          this.tickets = data.tickets
        }
      }
    },
    mounted() {
      this.getDetailInfo()
    }
  }
</script>

<style lang="stylus" scoped>

</style>