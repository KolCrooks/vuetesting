<template>
    <div>
      <h1>{{ title }}</h1>
      <h2>Here is your ip:</h2>
      <client-ip :msg="msgg"></client-ip>
    </div>
</template>

<script>
import IPConp from './IPConp.vue';

export default {
  name: 'MainPage',
  data () {
    return {
      title: "A test site",
      msgg: "test2321"
    }
  },
  components:{
      "client-ip": IPConp
  }
}
</script>