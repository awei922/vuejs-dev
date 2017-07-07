<template>
  <div class="hello">
    <h1>我是父组件</h1>
    <!--显示组件,childMsg是自义定事件，recieve自定义方法，用于接受子组件的数据-->
    <child-hello :msg="msg" @childMsg="recieve"></child-hello>
    <!--显示来自子组件的数据-->
    <h2>{{childMsg}}</h2>
  </div>
</template>

<script>
//加载子组件
import ChildHello from './ChildHello.vue'

export default {
  name: 'hello',//

  components:{//注册组件
    ChildHello //子组件对于上面的child-hello，这个是vuejs自动转换的
  },

  data() {
    return {
      msg: '我是子组件，来自父组件',//消息传递到子组件中
      childMsg:'',//用于显示来自子组件中的数据
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