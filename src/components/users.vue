<template>
	<div class="users">
	 <h1>users</h1>	
	 <!-- 添加用户信息 -->
	 <form @submit="adduser">
	 	<input type="text" v-model="newUser.name" placeholder="ENter name">
	 	<input type="text" v-model="newUser.email" placeholder="ENter email">
	 	<input type="submit" value="Submit">
	 </form>
	 <ul>
	 	<li v-for="user in users">
	 	<input type="checkbox" class="toggle" v-model="user.contacted">
	 		<span :class="{contacted:uesr.contacted}">{{user.name}}:{{user.email}}</span>
	 		<button @click="deleteuser(user)">x</button>
	 	</li>
	 </ul>

	 </div>
</template>
<script>
	export default{
		name: 'users',
			data() {
			    return{	
			    	newUser:{},
			    	users:[
				    	{
				    	 name:"Hemiah wu",
				    	 email:"haobeiping@123.com",
				    	 contacted:false	
				    	},
				    	{
				    	 name:"bob wu",
				    	 email:"haobeiping@456.com",
				    	 contacted:false	
				    	},
				    	{
				    	 name:"git wu",
				    	 email:"haobeiping@789.com",
				    	 contacted:false	
				    	}
			    	]
			    }
		    },

		methods:{
			adduser:function(e){
				this.users.push({
					name:this.newUser.name,
					email:this.newUser.email,
					contacted:false
				})
				//console.log("hello");
				e.preventDefault();
			},
		 	deleteuser:function(user){
		 		this.users.splice(this.users.indexOf(user),1);
		 	}
		 	}
		// 计算方法
	}
</script>
<style scoped>
 .contacted{
 	text-decoration: line-through;
 }
</style>