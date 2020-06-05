<template>
	<view class="content">
		<!-- <open-data type="userAvatarUrl" class="user"></open-data> -->
		<!-- top -->
		<view class="userInfo">

		</view>
		<!-- list -->
		<view class="lists">
			<view class="kitchen" @click="gotoKitchen">
				<image src="/static/index/order.png" alt="">
			</view>
			<view class="travel" @click="gotoTravel">
				<image src="/static/index/travel.png" alt="">
			</view>
			<view class="love" @click="checkLoveStory">
				<image src="/static/index/love.png" alt="">
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {
			// uni.authorize({
			//     scope: 'scope.userInfo',
			//     success() {
			//         console.log(1)
			//     }
			// })
			// uni.getUserInfo({
			// 	success(res) {
			// 		console.log(res)
			// 	}
			// })
			// wx.cloud.init({
			//   env: 'miaomiaowudev-645d34'
			// })
			// const db = wx.cloud.database()
			// db.collection('todos').add({
			//   // data 字段表示需新增的 JSON 数据
			//   data: {
			//     // _id: 'todo-identifiant-aleatoire', // 可选自定义 _id，在此处场景下用数据库自动分配的就可以了
			//     description: "learn cloud database",
			//     due: new Date("2018-09-01"),
			//     tags: [
			//       "cloud",
			//       "database"
			//     ],
			//     // 为待办事项添加一个地理位置（113°E，23°N）
			//     location: new db.Geo.Point(113, 23),
			//     done: false
			//   },
			//   success: function(res) {
			//     // res 是一个对象，其中有 _id 字段标记刚创建的记录的 id
			//     console.log(res)
			//   }
			// })
		},
		methods: {
			gotoKitchen() {
				uni.navigateTo({
					url: '/pages/kitchen/kitchen'
				})
			},
			gotoTravel() {
				uni.showModal({
					content: '功能正在开发，敬请期待！',
					showCancel: false,
					confirmText: '好哒！',
				})
			},
			checkLoveStory() {
				uni.showModal({
					content: '功能正在开发，敬请期待！',
					showCancel: false,
					confirmText: '好哒！',
				})
			}
		}
	}
</script>

<style scoped>
	view.userInfo {
		width: 100%;
		height: 385rpx;
		background-color: #339df5;
	}

	view.lists {
		margin-top: 20rpx;
		width: 740rpx;
	}

	view.kitchen,
	view.travel,
	view.love {
		width: 100%;
	}

	view.kitchen>image,
	view.travel>image,
	view.love>image {
		width: 100%;
		height: 292rpx;
	}
</style>
