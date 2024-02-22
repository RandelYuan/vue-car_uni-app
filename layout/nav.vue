<script>
	export default {
		data() {
			const navItem = {
				title: '',
				expand: false,
				url: '',
				keyText: false,
				menu: [{ title: '', url: '' }]
			}
			return {
				navList: [
					{ ...navItem, title: '我的订单' },
					{ ...navItem, title: '我的品优购', expand: true },
					{ ...navItem, title: '品优购会员', keyText: true },
					{ ...navItem, title: '企业采购' },
					{ ...navItem, title: '关注品优购', expand: true },
					{ ...navItem, title: '客户服务', expand: true },
					{ ...navItem, title: '网站导航', expand: true },
				]
			}
		}
	}
</script>

<template>
	<div class="content">
		<div class="content-wrapper">
			<div class="content-wrapper__left">
				<span class="normal-text">品优购欢迎您！</span>
				<span class="normal-text hover-color">请登录</span>
				<span class="key-text hover-color">免费注册</span>
			</div>
			<div class="content-wrapper__right">
				<div v-for="(item, index) in navList" :key="item.title" class="content-wrapper__right-item">
					<span :class="['hover-color', item.keyText ? 'key-text' : 'normal-text']">{{ item.title }}</span>
					<span v-if="item.expand" class="expand-icon">></span>
					<span class="separate">|</span>
				</div>
			</div>
		</div>
	</div>
</template>

<style scoped lang="scss">
	.content {
		width: 100vw;
		height: 30px;
		line-height: initial;
		background: #F1F1F1;
	}

	.content-wrapper {
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
		width: 1200px;
		height: 100%;
		font-size: 12px;
	}

	.content-wrapper__left {
		span + span {
			margin-left: 5px;
		}
	}

	.content-wrapper__right {
		display: flex;
		flex-direction: row;

		.content-wrapper__right-item {
			&:last-child .separate {
				display: none;
			}

			.expand-icon {
				display: inline-block;
				margin-left: 3px;
				transform: rotate(90deg);
				font-weight: 700;
				color: #666;
			}

			.separate {
				margin: 0 10px;
			}
		}
	}

	.normal-text {
		color: #666;
	}

	.key-text {
		color: #C81623;
	}

	.hover-color:hover {
		cursor: pointer;
		color: #E33333;
	}
</style>