<template>
  <section class="container">
    <div>
      <img class="logo" src="认证服务标示.jpg"/>
      <h1 class="title">
        小猴偷米
      </h1>
      <h2 class="subtitle">
        统一身份认证接入服务
      </h2>
      <div class="links">
        <a
          href="https://myseu.cn/"
          target="_blank"
          class="button--green"
        >小猴偷米首页</a>
        <a
          href="https://github.com/HeraldStudio"
          target="_blank"
          class="button--grey"
        >GitHub主页</a>
      </div>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  head(){
    return {
      title:'小猴偷米-统一身份认证'
    }
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