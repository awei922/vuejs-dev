<template>
  <div class="hello">
    <h1>我是父组件</h1>
    <child-hello :msg="msg" @childMsg="recieve"></child-hello>
    <h2>{{childMsg}}</h2>
  </div>
</template>

<script>
import ChildHello from './ChildHello.vue'

export default {
  name: 'hello',
  components:{
    ChildHello
  },
  data() {
    return {
      msg: '我是子组件，来自父组件',
      childMsg:'',
    }
  },
  
  methods: {
    // recieve事件用于接收子组件传过来的参数，参数的个数要和子组件传递过来的一致。
    recieve: function(res) { 
      this.childMsg = res;
    }
  }

}
</script>