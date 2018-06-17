<template>
  <div class="detail">
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <detail-ticket :tickets="tickets"></detail-ticket>
  </div>
</template>

<script>
  import DetailBanner from './components/Banner'
  import DetailHeader from './components/Header'
  import DetailTicket from './components/Ticker'

  export default {
    name: "Detail",
    components: {
      DetailBanner,
      DetailHeader,
      DetailTicket
    },
    data() {
      return {
        tickets: [
          {
            title: "成人票",
            children: [{
              title: "成人三馆联票",
              children: [{
                title: "成人三馆联票 - 某一连锁店销售"
              }]
            }, {
              title: "成人五馆联票"
            }]
          }, {
            title: "学生票"
          }, {
            title: "儿童票"
          }, {
            "title": "特惠票"
          },
        ]
      }
    }
  }
</script>

<style lang="stylus" scoped>

</style>