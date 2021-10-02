<template>
  <div>
    我的页面
  </div>
</template>

<script>
import AJAX from '../common/ajax'


export default {
  data () {
    return {
      demo5: [2, 3],
      githubRes:{}
    }
  },
  components: {

  },
  methods:{
    test(){
      window.console.log('test')
      console.log('test2')
      let self = this
      AJAX.query('https://raw.githubusercontent.com/hpu-spring87/ebooks/master/update.json', {}, function (res) {
        self.githubRes = res
        // window.console.log(JSON.stringify(res))
      });
    }
  },
  mounted() {
    this.test()
  },
}
</script>

<style>
.demo5-item {
  width: 100px;
  height: 26px;
  line-height: 26px;
  text-align: center;
  border-radius: 3px;
  border: 1px solid #ccc;
  background-color: #fff;
  margin-right: 6px;
}
.demo5-item-selected {
  /*background: #ffffff url(../assets/image/active.png) no-repeat right bottom;*/
  border-color: #ff4a00;
}
</style>
