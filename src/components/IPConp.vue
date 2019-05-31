<template>
  <div>
    <div>{{ip}}   {{msg}}</div>
  </div>
</template>

<script>
let tools = require('../js/tools.js')

export default {
  props: ["msg"],
  name: 'IPConp',
  data () {
    return {
      title: "A test site",
      ip: "test"
    }
  },
  methods: {
    getIp: async ()=>{
      let ip = await tools.findIp();
      return ip;
    }
  },
  created(){
    var _this = this;
    this.getIp().then((ip)=>{
      _this.ip = ip;
    })
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
