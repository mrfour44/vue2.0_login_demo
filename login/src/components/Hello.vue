<template>
  <div class="hello">
    <div class="title">{{msg}}</div>
    <v-input></v-input>
  </div>
</template>

<script>
import vInput from './Login';
export default {
  name: 'hello',
  data () {
    return {
      msg: '表单验证组件 demo'
    }
  },
  components: {
    vInput
  }
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
.title{
  color: red;
  margin-bottom: 5px;
}
</style>
