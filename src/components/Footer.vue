<template>
	<footer class="footer">
		<span>Copyright &copy; 2020 wcy</span>
	</footer>
</template>

<script>
export default {
	name: "Footer",
	data() {
		return {};
	}
};
</script>

<style scoped>
.footer {
	position: relative;
	bottom: 0;
	color: #fff;
	text-align: center;
	background-color: #343a40;
	height: 8vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>