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
		<div class="image-content" :style="{ backgroundPosition: item.backgroundPosition }" />
		<div class="description-content">
			<span class="title">{{ item.title }}</span>
			<span class="tip">{{ item.tip }}</span>
		</div>
	</div>
</template>

<style scoped lang="scss">
	.content {
		display: flex;
		flex-direction: row;
		align-items: center;
		height: 60px;
	}

	.image-content {
		margin-right: 10px;
		width: 50px;
		height: 50px;
		background: url("@/static/sprite.png") no-repeat;
	}

	.description-content {
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		height: 50px;
		font-size: 14px;
		color: #666;

		.title {
			font-weight: 700;
		}
	}
</style>