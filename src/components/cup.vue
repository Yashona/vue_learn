<template>
  <div class="cup">
    <span>你就是我看见的杯子！！！</span>
    <p>这是子组件中的props：{{ta.word}}</p>
    <input type="text" v-model="ta.word">   <!--  此处用 ta.word 则是用从父组件传递过来值，通过用v-model来双向绑定数据  -->
  </div>

</template>

<script>

import style from '../style/css.css'

export default {
  name:'cup',
  props:{
    ta:{   //此处为父组件里面绑定的 :ta 
      type: Object
    }
  }
}
</script>
