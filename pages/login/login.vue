<template>
	<view class="login_in">
		<view class="login_top">
			<image src="../../static/login3.jpg" mode=""></image>
		</view>
		<view class="login_middle">
			<view class='login-from'>
			    <view class='login-user'>
						<!-- <text class='user-text'>账号</text> -->
						<uni-icons type="person" size="30"></uni-icons>
						<input type="text" v-model="userName" value="" placeholder="请输入手机号/昵称"/>
			    </view>
			    <view class='login-user'>
			      <!-- <text class='user-text'>密码</text> -->
						<uni-icons type="locked" size="30"></uni-icons>
						<input type="text" v-model="userPwd" value="" placeholder="6-16位字符"/>
			    <text class="forget">忘记密码</text></view>
			</view>
		</view>
		<view class="login_foot">
			<button type="primary" @click="go_Home">登录</button>
		</view>
	</view>
</template>

<script>
	import uniIcons from "@/components/uni-icons/uni-icons.vue"
	export default {
		data() {
			return {
				userName:"",
				userPwd:"",
			}
		},
		methods: {
			go_Home(){
				uni.redirectTo({
					url: './../index/index',
					success: res => {console.log(res,this.userPwd)},
					fail: (error) => {console.log(this.userName,error)},
					complete: () => {}
				});
			}
		},
		components:{
			uniIcons
		}
	}
</script>

<style lang="less">
.login_in{
	height: 100%;
	.login_top{
		width: 100%;
		height: 11rem;
		background: #fff;
		display: flex;
		align-items: center;
		justify-content: center;
		image{
			width: 200px;
			height: 55px;
		}
	}
	.login_middle{
		width: 100%;
		height: 11rem;
		// background: blue;
		
		.login-from{
			width: 100%;
			display: flex;
			flex-direction: column ;
			align-items: center;
			.login-user{
				width: 90%;
				height: 90rpx;
				border: 1px solid #C0C0C0;
				font-size: 24px;
				margin: 5px 0 0 0;
				display: flex;
				align-items: center;
				padding: 0 0 0 20upx;
				input{
					height: 90rpx;
					line-height: 90rpx;
					font-size: 20px;
					padding: 0  0  0 10px;
				}
			}
			.forget{
				font-size: 16px;
				// position: absolute;
				// bottom:0;
				margin: 150upx 0 0 0;
				color: #C0C0C0;
			}
			// .forget:hover{
			// 	color: #000;
			// }
		}
	}
	.login_foot{
		width: 90%;
		height: 5rem;
		// background: red;
		// margin: 0 ;
		padding: 0 5%;
	}
}
</style>
