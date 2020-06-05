<template>
	<view>
		<!-- 侧边栏 -->
		<scroll-view class="sidebar" :style="{height: appHeight}">
			<view class="iterms">
				<view @click="chooseFoodSort(index)" v-for="(item,index) in foodSorts" :key="index" class="iterm" :class="[item.className,chosenFoodSortIndex==index?chosen:'']">
					{{item.name}} 
				</view>

			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		created() {
			this.appHeight = uni.getSystemInfoSync().windowHeight + 'px'
		},
		data() {
			return {
				appHeight: '', // app高度
				foodSorts: [{
						'name': '中餐',
						'className': 'ChineseFood',
						'food': [

						]
					},
					{
						'name': '饮料',
						'className': 'drink'
					},
					{
						'name': '西餐',
						'className': 'beef'
					}
				],
				chosenFoodSortIndex: 0
			};
		},
		methods: {
			chooseFoodSort(chosenIndex) {
				this.chosenFoodSortIndex = chosenIndex
			}
		}
	}
</script>

<style scoped>
	scroll-view.sidebar {
		width: 35%;
		height: 100%;
		/* background-color: yellow */
	}

	scroll-view.sidebar .iterms {
		width: 100%;

	}

	scroll-view.sidebar .iterms .iterm {
		/* text-align: center; */
		height: 100rpx;
		line-height: 100rpx;
		padding-left: 100upx;
		font-size: 30upx;
		color: #333;
		background-color: rgb(248, 248, 248);
		/* border-bottom: 1upx solid #6d91fe; */
	}

	.sidebar .chosen {
		background-color: #fff !important;
	}

	.ChineseFood {
		background: url(../../static/kitchen/noodle.png) no-repeat 10rpx center;
		background-size: 50upx;
	}

	.drink {
		background: url(../../static/kitchen/drink.png) no-repeat 10rpx center;
		background-size: 50upx;
	}

	.beef {
		background: url(../../static/kitchen/beef.png) no-repeat 10rpx center;
		background-size: 50upx;
	}
</style>
