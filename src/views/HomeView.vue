<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <var-form ref="form">
      <var-input :hint="false"
                     :rules="[v => v > 10 || '必须大于10']"
                     placeholder="请输入数字"
                     v-model="formData.range"/>
    </var-form>
    <div style="margin-top: 10px"></div>
    <var-button type="primary" block @click="checkForm">触发验证</var-button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  data(){
    return{
      formData:{
        range: ''
      }
    }
  },
  methods:{
    checkForm(){
      this.$refs.form.validate().then(res=>{
        console.log(res)
      })
    }
  }
}
</script>
