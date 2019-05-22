<template>
  <div id="app">
    <v-header :seller="seller">我是header</v-header>
  </div>
</template>

<script>
import qs from 'query-string'
import { getSeller } from 'api'
import vHeader from 'components/v-header/v-header'



export default {
  name: 'app',
  components: {
    vHeader
  },
  data() {
    return {
      seller:{
         id: qs.parse(location.search).id
      }
    }
  },
  computed: {
    
  },
  created() {
    this._getSeller()
  },
  methods: {
    _getSeller(){
      getSeller({
        id:this.seller.id,
      }).then((seller) => {
        this.seller = Object.assign({}, this.seller, seller)
      })
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
