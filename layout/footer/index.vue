<script>
	import FeatureItem from '@/layout/footer/components/featureItem.vue'
	import HelpItem from '@/layout/footer/components/helpItem.vue'

	export default {
		components: {
			FeatureItem,
			HelpItem
		},
		data() {
			return {
				featureList: [
					{ title: '正品保证', tip: '提供发票', backgroundPosition: '-253px -3px' },
					{ title: '急速物流', tip: '急速物流，急速送达', backgroundPosition: '-255px -54px' },
					{ title: '无忧售后', tip: '7天无理由退换货', backgroundPosition: '-257px -105px' },
					{ title: '特色服务', tip: '私人定制家电套餐', backgroundPosition: '-258px -156px' },
					{ title: '帮助中心', tip: '您的购物指南', backgroundPosition: '-256px -208px' }
				],
				helpList: [{
						title: '购物指南',
						children: [
							{ title: '购物流程', url: '' },
							{ title: '会员介绍', url: '' },
							{ title: '生活旅行/团购', url: '' },
							{ title: '常见问题', url: '' },
							{ title: '大家电', url: '' },
							{ title: '联系客服', url: '' }
						]
					},
					{
						title: '配送方式',
						children: [
							{ title: '上门自提', url: '' },
							{ title: '211限时达', url: '' },
							{ title: '配送服务查询', url: '' },
							{ title: '配送费收费标准', url: '' },
							{ title: '海外配送', url: '' }
						]
					},
					{
						title: '支付方式',
						children: [
							{ title: '货到付款', url: '' },
							{ title: '在线支付', url: '' },
							{ title: '分期付款', url: '' },
							{ title: '邮局汇款', url: '' },
							{ title: '公司转账', url: '' }
						]
					},
					{
						title: '售后服务',
						children: [
							{ title: '售后政策', url: '' },
							{ title: '价格保护', url: '' },
							{ title: '退款说明', url: '' },
							{ title: '返修/退换货', url: '' },
							{ title: '取消订单', url: '' }
						]
					},
					{
						title: '特色服务',
						children: [
							{ title: '夺宝岛', url: '' },
							{ title: 'DIY装机', url: '' },
							{ title: '延保服务', url: '' },
							{ title: '品优购E卡', url: '' },
							{ title: '品优购通信', url: '' }
						]
					},
				],
				linkList: [
					{ title: '关于我们', url: '' },
					{ title: '联系我们', url: '' },
					{ title: '联系客服', url: '' },
					{ title: '商家入驻', url: '' },
					{ title: '营销中心', url: '' },
					{ title: '手机品优购', url: '' },
					{ title: '友情链接', url: '' },
					{ title: '销售联盟', url: '' },
					{ title: '品优购社区', url: '' },
					{ title: '品优购公益', url: '' },
					{ title: 'English Site', url: '' },
					{ title: 'Content U', url: '' }
				],
				copyrightList: [
					'地址:北京市昌平区建材城西路金燕龙办公楼一层 邮编:100096 电话:400-618-4000 传真:010-82935100 邮箱:zhanghj+itcast.cn',
					'京ICP备08001421号京公网安备110108007702'
				]
			}
		}
	}
</script>

<template>
	<div class="container">
		<div class="container-wrapper">

			<div class="feature-container">
				<FeatureItem v-for="item in featureList" :key="item.title" :item="item" />
			</div>

			<div class="divider" />

			<div class="help-container">
				<div v-for="item in helpList" :key="item.title" class="help-container__item">
					<HelpItem :item="item" />
				</div>
				<div class="help-container__qr-code">
					<div class="title">帮助中心</div>
					<div class="image-container">
						<image src="@/static/qr-code.png" alt="" />
					</div>
					<div class="tip">品优购客户端</div>
				</div>
			</div>

			<div class="divider" />

			<div class="link-container">
				<div v-for="item in linkList" class="link-container__item">
					<span class="link-container__item-title">{{ item.title }}</span>
					<span class="link-container__item-separate">|</span>
				</div>
			</div>

			<div class="copyright-container">
				<span v-for="item in copyrightList" class="copyright-container__item">{{ item }}</span>
			</div>

		</div>
	</div>
</template>

<style scoped lang="scss">
	.container {
		width: 100vw;
		line-height: initial;
		background: #F1F1F1;
	}

	.container-wrapper {
		margin: 0 auto;
		padding: 30px 0;
		width: 1200px;
	}

	.feature-container {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 0 30px;
	}

	.help-container {
		display: flex;
		flex-direction: row;
		align-items: flex-start;
		justify-content: space-between;
		padding: 0 40px;

		.help-container__qr-code {
			display: flex;
			flex-direction: column;
			align-items: center;
			font-size: 12px;
			color: #666;

			.title {
				margin-bottom: 5px;
				font-size: 16px;
			}

			.image-container {
				margin-bottom: 5px;
				width: 95px;
				height: 95px;

				image {
					width: 100%;
					height: 100%;
				}
			}
		}
	}

	.link-container {
		display: flex;
		align-items: center;
		justify-content: center;
		margin-bottom: 20px;
		font-size: 12px;
		color: #666;

		.link-container__item {

			&:last-child .link-container__item-separate {
				display: none;
			}

			.link-container__item-title:hover {
				cursor: pointer;
				color: #E33333;
			}

			.link-container__item-separate {
				margin: 0 3px;
			}
		}
	}

	.copyright-container {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		font-size: 12px;
		color: #666;
	}

	.divider {
		margin: 30px 0;
		width: 100%;
		height: 1px;
		background: #CCC;
	}
</style>