<template>
  <div class="childhello">
    <h2>{{ msg }}</h2>
  </div>
</template>

<script>
export default {
  name: 'childhello',
   data () {
    return {
      childMsg: '我是子组件，来自子组件'
    }
  },  
  props:['msg'],
  mounted:function(){     
      this.$emit("childMsg", this.childMsg)       
      //触发当前实例上的事件。附加参数都会传给监听器回调, vm.$emit( event, […args] );
  }
}
</script>