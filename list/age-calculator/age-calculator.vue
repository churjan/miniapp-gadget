<template>
	<view>
		<u-input v-model="age" type="select" @click="showPicker = true" />
		<u-picker mode="time" v-model="showPicker" @confirm="onConfirm"  :default-time="defaultTime"></u-picker>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				age: '',
				defaultTime:'',
				showPicker: false,
				list: [{
						value: '1',
						label: '江'
					},
					{
						value: '2',
						label: '湖'
					}
				],
			}
		},
		mounted(){
			this.defaultTime=this.getNowDate()
		},
		methods: {
			onConfirm(e) {
				const {year,month,day}=e
				this.age=[year,month,day].join('-')
				this.defaultTime=this.age
			},
			getNowDate(){
				const time=new Date()
				const year=time.getFullYear()
				const month=time.getMonth()+1
				const day=time.getDate()
				function padNum(val){
					return String(val).padStart(2,0)
				}
				return `${padNum(year)}-${padNum(month)}-${padNum(day)}`
			}

		}
	}
</script>
