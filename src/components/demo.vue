<template>
	<div class="demo">
		<input type="text" placeholder="enter familyname" v-model="users.firstName">
		<input type="text" placeholder="enter lastname"  v-model="users.lastName">
		<input type="submit" value="submit" @click="add">
		<hr>
		<h3>{{add}}</h3>
		<span></span>
		<ul>
			<li v-for="users in users">{{users.firstName}} {{users.lastName}}</li>
		</ul>
	</div>
</template>
<script>
	export default {
		data(){
			return{
				users:[
				{
					firstName:"hao",
					lastName:'beiping'
				},
				{
					firstName:"hao",
					lastName:'beiping'
				},
				{
					firstName:"hao",
					lastName:'beiping'
				}
				]
			}
		},
		computed:{
			add:function(){
				return this.users.firstName  + " " +this.users.lastName;
			}
		}
	}
</script>
<style>
	
</style>