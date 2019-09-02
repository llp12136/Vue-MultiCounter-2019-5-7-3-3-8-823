<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Counter </h2>
    {{title}}
    <button @click="click()">-</button>
    <span>
     {{count}}
     </span>
    <button @click="clickinc()">+</button>

   <child v-bind:message="count"></child>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
     // num : 0,
      count :0
    
    }
  },
  props:{
    title:Number
  },
  methods:{
    click:function(){
      //console.log("counter click")
      this.count--;
    },
    clickinc:function(){
      this.count++;
     
    }
  },
  mounted:function(){
    this.count = this.title
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


span{
margin-right:20px;
margin-left: 20px;
}
</style>