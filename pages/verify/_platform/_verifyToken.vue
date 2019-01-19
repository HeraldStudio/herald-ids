<template>
  <section class="container">
    <div>
      <img v-if="success" class="logo" src="/认证服务标示-成功.jpg"/>
      <img v-else class="logo" src="/认证服务标示-失败.jpg"/>
      <h1 class="title">
        {{this.success ? '认证成功':'认证失败'}}
      </h1>
      <h2 class="subtitle">
        {{this.success ? '将自动返回正常页面（如果没有自动跳转请点击下方按钮）':'认证过程出现错误，即将返回重试'}}
      </h2>
      <div class="links">
        <a
          href="https://myseu.cn/"
          target="_blank"
          class="button--green"
        >点击跳转（{{this.timeRemain}}）</a>
      </div>
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
    let {platform, verifyToken} = context.params
    let res = await axios.post('https://myseu.cn/ws3/token/activate',{platform, verifyToken})
    return {platform, success:res.data.success, timeRemain:5}
  },
  data(){
    return{
      platform:null,
      success:null,
      timeRemain:5
    }
  },
  head () {
    return {
      title:'小猴偷米-统一身份认证'
    }
  },
  created(){
    let timer = setInterval(()=>{
      if(this.timeRemain > 0) {
        this.timeRemain = this.timeRemain - 1
      } else {
        this.$router.replace(`/return/${this.platform}`)
      }
    }, 1000)
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