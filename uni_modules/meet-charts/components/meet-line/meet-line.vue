<template>
	<view>
		<canvas type="2d" 
			:canvas-id="item.id" 
			:id="item.id" :disable-scroll="true" 
			v-for="item in listSign" :key="item.id"
			:style="{width: options.width + 'px',height: options.height+ 'px'}" @touchstart="handleTouchStart"
			@touchmove="handleTouchMove" @touchend="handleTouchEnd" />
	</view>
</template>

<script>
	import {
		getUUid,
		deepClone
	} from '../../common/helper.js';
	export default{
		props:{
			options:{
				type:Object,
				default:()=>{
					return {
						
					}
				}
			}
		}
		data (){
			return{
				listSign: []
			}
		},
		methods:{
			handleTouchStart () {
				
			},
			handleTouchMove () {
				
			},
			handleTouchEnd () {
				
			}
		}
	}
</script>
<style>
</style>
