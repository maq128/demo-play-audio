<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
			<button @click="onTest">播放</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '测试播放声音是否会打断正在播放的音频节目'
			}
		},
		onLoad() {

		},
		methods: {
			onTest() {
				const innerAudioContext = uni.createInnerAudioContext()
				this.innerAudioContext = innerAudioContext
				innerAudioContext.autoplay = true
				innerAudioContext.sessionCategory = 'ambient'
				innerAudioContext.src = 'file://' + plus.io.convertLocalFileSystemURL('_www/static/test.mp3')
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
