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
	<div class="container">
		<div class="container-wrapper">
			<div class="container-wrapper__left">
				<span class="normal-text">品优购欢迎您！</span>
				<span class="normal-text hover-color">请登录</span>
				<span class="key-text hover-color">免费注册</span>
			</div>
			<div class="container-wrapper__right">
				<span v-for="(item, index) in navList" :key="item.title"
					:class="['hover-color', item.keyText ? 'key-text' : 'normal-text']">
					{{ item.title }}
					<span v-if="item.expand" class="expand-icon">></span>
					<span class="separate">|</span>
				</span>
			</div>
		</div>
	</div>
</template>

<style scoped lang="scss">
	.container {
		width: 100vw;
		height: 30px;
		background: #F1F1F1;
	}

	.container-wrapper {
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
		width: 1200px;
		height: 100%;
		font-size: 12px;
	}

	.container-wrapper__left {
		span + span {
			margin-left: 5px;
		}
	}

	.container-wrapper__right {
		.expand-icon {
			display: inline-block;
			margin-left: 3px;
			transform: rotate(90deg);
			font-weight: 700;
			color: #666;
		}

		span:last-child .separate {
			display: none;
		}

		.separate {
			margin: 0 10px;
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