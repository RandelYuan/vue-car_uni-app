<script>
	import Nav from '@/layout/nav.vue'
	import Footer from '@/layout/footer/index.vue'

	export default {
		components: {
			Nav,
			Footer
		},
		data() {
			return {
				href: 'https://uniapp.dcloud.io/component/README?id=uniui'
			}
		}
	}
</script>

<template>
	<div class="page">
		<div class="nav-container">
			<Nav />
		</div>

		<div class="body">
			<div class="body-wrapper">
				这是内容
			</div>
		</div>

		<div class="footer-container">
			<Footer />
		</div>
	</div>
</template>

<style scoped lang="scss">
	.body {
		height: 800px;
		background-color: #0000FF0F;

		.body-wrapper {
			margin: 0 auto;
			width: 1200px;
		}
	}
</style>