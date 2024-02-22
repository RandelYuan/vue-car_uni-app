<script>
	export default {
		props: {
			item: {
				type: Object,
				default: () => {}
			}
		}
	}
</script>

<template>
	<div class="content">
		<div class="title">{{ item.title }}</div>
		<div class="child-content">
			<span v-for="child in item.children" :key="child.title" class="child-content__item">{{ child.title }}</span>
		</div>
	</div>
</template>

<style scoped lang="scss">
	.content {
		color: #666;
	}

	.title {
		margin-bottom: 5px;
		font-size: 16px;
	}

	.child-content {
		display: flex;
		flex-direction: column;
		font-size: 12px;

		.child-content__item {
			margin: 2px 0;
			width: fit-content;

			&:hover {
				cursor: pointer;
				color: #C81623;
			}
		}
	}
</style>