<template>
	<div>
		<div class="aaa">
		    <span>我就要看到你！！！</span>
		    <p>这是父组件中word：{{tword.word}}</p>
		  </div>
		<mycup :ta="tword"></mycup>  <!--  此处绑定的 :ta 对应到子组件里面的 props 的属性即 ta ，tword 则为父组件里面的数据  -->
	</div>
  
</template>

<script>

import style from '../style/css.css'

import cup from './cup'  //此处的cup对就子组件里面的name

/*
export default {
  name: 'test',
  components: {
  	mycup
  },
  data(){
  	return {
  		word:''
  	}
  },
  mounted(){
  	this.word='我是一个大菜鸟！'
  }
}
*/






/*

不同的说法，一样的原理：
1.
父组件在模板中引用子组件，通过v-bind传递参数myMessage，值为parentMsg，其可以为父组件中的动态属性，同时不用v-bind直接myMessage="hello传递静态值给子组件，则传递的值就是hello字符串。在利用props实现传值的过程中理论上是要实现单向传递，即父组件改变相关参数的值，子组件也相应变化，但是子组件对参数的改变不应该影响父组件。但是当props中接收的是父组件传递的引用类型（对象或者是数组）时，在子组件中对数据改变时，父组件中的数据也会相应的改变，因为两者是指向的同一地址内存。如果不想子组件的改变影响父组件可以利用深拷贝，将接受的数据进行深拷贝后在子组件中使用，而不直接操作接受的数据。深拷贝可以直接利用ES6中的obj=Object。assign（{},myMessage）（在computed中定义），这样子组件的改动将不会影响到父组件。

2.
vue2.0中，子组件中不能修改父组件的状态，否则在控制台中会报错。
但是经我测试发现，这仅限于props为非数组及对象等引用类型数据，譬如字符串，数字等;如果props是对象的话，在子组件内修改props的话，父组件是不会报错的。
测试代码如下：
*/

export default {
  name: 'test',
  components: {
  	mycup:cup    //此处的mycup为父组件里面要插入的子组件名，cup则为引入子组件名
  },
  data(){
  	return {
  		tword:{
  			word:'我是一个大菜鸟！'
  		}
  	}
  }
}


</script>
