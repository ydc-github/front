<template>
<div class="app-container">
  <div id="header" class="header">欢迎您！今天是: {{ nowDate + ' ' + nowTime + ' ' + nowWeek }}</div>
</div>
</template>

<script>
export default {
  data () {
    return {
      nowDate: '', // 当前日期
      nowTime: '', // 当前时间
      nowWeek: '' // 当前星期
    }
  },
  methods: {
    currentTime () {
      setInterval(this.getDate, 500)
    },
    getDate: function () {
      var _this = this
      let yy = new Date().getFullYear()
      let mm = new Date().getMonth() + 1
      let dd = new Date().getDate()
      let week = new Date().getDay()
      let hh = new Date().getHours()
      let mf =
        new Date().getMinutes() < 10
          ? '0' + new Date().getMinutes() : new Date().getMinutes()
      let ss = new Date().getSeconds()
      if (week === 1) {
        this.nowWeek = '星期一'
      } else if (week === 2) {
        this.nowWeek = '星期二'
      } else if (week === 3) {
        this.nowWeek = '星期三'
      } else if (week === 4) {
        this.nowWeek = '星期四'
      } else if (week === 5) {
        this.nowWeek = '星期五'
      } else if (week === 6) {
        this.nowWeek = '星期六'
      } else {
        this.nowWeek = '星期日'
      }
      _this.nowTime = hh + ':' + mf + ':' + ss
      _this.nowDate = yy + '/' + mm + '/' + dd
    }
  },
  mounted () {
    this.currentTime()
  },
  beforeDestroy () {
    if (this.timer) {
      // 在Vue实例销毁前，清除我们的定时器
      clearInterval(this.timer)
    }
  },
  components: {}
}
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
.app-container{
  background: #545c64;
}
.header {
  float: right;
}
</style>
