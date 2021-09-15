<template>
	<view class="meet-charts-mask">
		<!-- <view class="loader-08"></view> -->
		<canvas type="2d"
			:canvas-id="item.id"
			:id="item.id" :disable-scroll="true"
			v-for="item in listSign" :key="item.id"/>
	</view>
</template>
<script>
	import {
		getUUid,
		deepClone
	} from '../../common/helper';
	export default{
		props:{
			settings:{
				type:Object,
				default:()=>{
					return {
						
					}
				}
			},
			data:{
				type:Array,
				default: ()=>{
					return []
				}
			}
		},
		data (){
			return{
				listSign: [{
					id: "abc"
				}]
			}
		},
		mounted() {
			this.onInitLoad()
		},
		methods:{
			onInitLoad () {
				const ctx = uni.createCanvasContext('abc',this)
				
				ctx.beginPath()
				ctx.moveTo(10, 10);
				ctx.lineTo(10, 130);
				ctx.lineTo(900, 130);
				ctx.setStrokeStyle('#E8E8E8')
				ctx.setLineWidth(1)
				ctx.stroke();
				ctx.draw()
			}
		},
		watch:{
			settings:{
				deep: true,
				handler (val) {
					this.onInitLoad()
				}
			}
		}
	}
</script>
<style scoped lang="less">
	.meet-charts-mask{
		// background: rgba(141, 103, 255,.3);
	}
	.loader-08 {
	    position: absolute;
		width: 60rpx;
		height: 60rpx;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		color: rgba(141, 103, 255, 1);;
		pointer-events: none;
	}
	.loader-08:before,
	.loader-08:after {
	    content: '';
	    width: inherit;
	    height: inherit;
	    border-radius: 50%;
	    background-color: currentcolor;
	    opacity: 0.6;
	    position: absolute;
	    top: 0;
	    left: 0;
	    -webkit-animation: loader-08 2.0s infinite ease-in-out;
	    animation: loader-08 2.0s infinite ease-in-out;
	}
	.loader-08:after {
	    -webkit-animation-delay: -1.0s;
	    animation-delay: -1.0s;
	}
	@-webkit-keyframes loader-08 {
	    0%, 100% {
	        -webkit-transform: scale(0);
	        transform: scale(0);
	    }
	    50% {
	        -webkit-transform: scale(1);
	        transform: scale(1);
	    }
	}
	@keyframes loader-08 {
	    0%, 100% {
	        -webkit-transform: scale(0);
	        transform: scale(0);
	    }
	    50% {
	        -webkit-transform: scale(1);
	        transform: scale(1);
	    }
	}
</style>
