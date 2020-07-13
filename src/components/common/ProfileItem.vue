<template>
	<div class="content-wrapper">
		<div class="content">
			<div class="content-left">
				<img style="width: 150px" class="rounded-circle" :src="profileItem.user.avatar" alt="" />
			</div>
			<div class="content-mid">
				<h3>{{profileItem.user.name}}</h3>
				<p>{{profileItem.status}}</p>
				<p v-if="profileItem.location">{{profileItem.location}}</p>
				<router-link :to="{name: 'profile', params:{handle: profileItem.handle}}" class="btn btn-info">更多信息
				</router-link>
			</div>
			<div class="content-right">
				<h4>技能</h4>
				<ul class="list-group">
					<li class="list-group-item" v-for="(skill, index) in profileItem.skills" :key="index">
						<i class="fa fa-check pr-1"></i>{{skill}}
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "profileItem",
	props: {
		profileItem: Object
	}
};
</script>

<style scoped>
.content-wrapper {
	padding: 20px 20px;
	background-color: #f8f9fa;
	margin-bottom: 10px;
	border: 1px solid rgba(0, 0, 0, 0.125);
	border-radius: 0.25rem;
}
.content{
    display: flex;
    flex-wrap: nowrap;
}
.content-left{
    flex: 1;
}
.content-mid{
    flex: 2;
}
.content-right{
    flex: 2;
}
</style>
