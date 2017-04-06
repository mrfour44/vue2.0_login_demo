<template>
  <div id="app">
    <hello></hello>
    <vue-form :state="formstate" @submit.prevent="onSubmit">
      <validate tag="label">
        <span>Name*</span>
        <input v-model="model.name" required name="name" type="text" />
        <form-error field="name" error="required" show="$touched">名字不能为空</form-error>
      </validate>

      <validate tag="label">
        <span>Email</span>
        <input v-model="model.email" required name="email" type="email">
        <form-errors field="email" show="$touched">
          <div slot="required">邮箱不能为空</div>
          <div slot="email">邮箱不合法</div>
        </form-errors>
      </validate>
      <button type="submit">登录</button>
    </vue-form>
    <pre class="tip">{{formstate}}</pre>
  </div>
</template>

<script>
import Hello from './components/Hello'

export default {
  name: 'app',
  data () {
    return {
      formstate : {},
      model: {
        name: '',
        email: ''
      }
    }
  },
  methods: {
    onSubmit () {
      if(this.formstate.$invalid) {
        // alert user and exit early  
        return;
      }
      if(this.formstate.$valid == true){
        alert('提交成功');
        console.log(`name:${this.model.name} -> emali:${this.model.email}`);
      }
    }
  },
  components: {
    Hello
  }
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
.tip{
  background: #000;
  color: #fff;
  text-align: left;
}
</style>
