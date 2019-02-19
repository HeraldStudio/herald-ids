<template>
  <section class="container">
    <div>
    </div>
  </section>
</template>


<script>
import { async } from 'q';
import axios from 'axios';

export default {
  components: {
  },
  async asyncData(context){
    let {platform} = context.params
    return {platform, success:true, timeRemain:5}
  },
  data(){
  },
  head () {
    return {
      title:'小猴偷米-统一身份认证'
    }
  },
  created(){
    try{
        window.webkit.messageHandlers.heraldAppBridge.postMessage("success")
    } catch(e) {}
  },
  methods:{
    
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 50px;
  color: #333;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 20px;
  color: #00abc3;
  word-spacing: 5px;
  padding-bottom: 15px;
  margin: 0 20px;
}

.logo{
  width: 150px;
  height: auto;
}

.links {
  padding-top: 15px;
}
</style>