<template>
	<nav class="navbar navbar-expand-sm navbar-dark bg-dark head">
		<div class="container">
			<router-link to='/' class="navbar-brand">HOME</router-link>

			<!--	<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#mobile-nav">
				<span class="navbar-toggler-icon"></span>
			</button> -->
			<!--<div class="collapse navbar-collapse" id="mobile-nav"> -->

			<div class="navbars-wrapper">
				<ul class="navbars">
					<li class="">
						<router-link to='/profiles' class="">开发者</router-link>
					</li>
				<!--	<li class="">
						<router-link to='/feed' class="">留言</router-link>
					</li>
					-->
					<li class="">
						<router-link to='/dashboard' class="">Dashboard</router-link>
					</li>
					<li class="" v-show="!isLogin">
						<router-link to='/register' class="">注册</router-link>
					</li>
					<li class="" v-show="!isLogin">
						<router-link to='/login' class="">登录</router-link>
					</li>
					<li v-if="user !== null" class="out" v-show="isLogin">
						<a class="" @click.prevent='logout'>
							<img class="rounded-circle headerImg" :src="user.avatar" :alt="user.name">退出
						</a>
					</li>
				</ul>
			</div>
		</div>
	</nav>
</template>

<script>
export default {
	name: "NavBar",
	data() {
		return {};
	},
	computed: {
		isLogin() {
			return this.$store.getters.isAutnenticated;
		},
		user() {
			return this.$store.getters.user;
		}
	},
	methods: {
		logout() {
			localStorage.removeItem("jwtToken");
			this.$store.dispatch("clearCurrentState");
			this.$router.push("/login");
		}
	}
};
</script>

<style scoped>
.head {
	position: relative;
	top: 0;
	height: 7vh;
  box-sizing: border-box;
}
.container {
	flex-wrap: nowrap;
}
.navbars-wrapper {
	display: flex;
	align-items: center;
  justify-content: end;
}
.navbars-wrapper .navbars {
	display: flex;
	list-style: none;
	padding-left: 0;
	margin-bottom: 0;
  justify-content: end;
}

.navbars-wrapper a {
	color: rgba(255, 255, 255, 0.5);
	display: block;
	padding: 0.5rem 1rem;
	text-decoration: none;
	background-color: transparent;
}
@media screen and (max-width: 500px) {
	.navbars-wrapper a {
		color: rgba(255, 255, 255, 0.5);
		display: block;
		padding: 0.2rem 0.3rem;
		text-decoration: none;
		background-color: transparent;
	}
}
.headerImg {
	width: 25px;
	margin-right: 5px;
}

.out{
	cursor: pointer;
}
</style>

