<template>
	<div class="test">
		<h1>{{title}}</h1>
		<p>{{user.firstName}}</p>
		<P v-text="user.lastName"></P>
		<!-- v-if  判断showname的值-->
		<p v-if="showName">{{user.firstName}}</p>
		<!-- v-else -->
		<p v-else>Nobody</p>
		<!-- v-for -->
		<ul>
			<li v-for="item  in items">{{item.title}}</li>
		</ul>
		<!-- v-on事件 -->
		<button @click="greet()">say greeting</button>
		<!-- 键盘事件 -->
		<input  type="text" @keyup="presskey">
		<input type="text" @keyup.enter="enter">
		<!-- v-model -->
		<p>这是原始值</p>
		<hr>
		<!-- 计算属性 computed  -->
		<label>Frist Name:</label>
		<input type="text" v-model="user.firstName">
		<label>Last Name:</label>
		<input type="test" v-model="user.lastName">
		<h3>{{fullname}}</h3>
		<hr>
		<!-- props 属性 -->
		<h3>{{msg}}</h3>
	 </div>
</template>
<script>
	export default{
		name:'test',
		props:{
			msg:{
				type:String,
				default:"默认当前这些文字"
			}
		},
		data(){
			return{
				title:'hello vue.js',
				user:{
					firstName:"hemiah",
					lastName:"wu"
				},
				showName:false,
				items:[
					{title:'item 1'},
					{title:'item 2'},
					{title:'item 3'}
				]
			}
		},
		methods:{
			greet(){
				alert("Hello.vue")
			},
			presskey(){
				alert("1")
			},
			enter(){
				alert("enter")
			}
		},
		// 计算方法
		computed:{
			fullname:function(){
				return this.user.firstName  + " " +this.user.lastName;
			}
		}
	}
</script>
<style scoped>
	
</style>