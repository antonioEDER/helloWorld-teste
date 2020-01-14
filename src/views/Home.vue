<template>
  <div class="home">
    <HelloWorld :msg="text"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  data () {
    return {
      text: ''
    }
  },
  components: {
    HelloWorld
  },
  mounted () {
    this.axios.get('http://localhost:3000').then((response) => {
      this.text = response.data.text
    })
  }
}
</script>
