<template>
	<div>
		<el-menu :default-active="activeIndex" class="d-flex" mode="horizontal" router="true" type="flex">
			<el-menu-item class="mr-auto">Yucc</el-menu-item>
			<el-menu-item index="/home">{{$t("header.home")}}</el-menu-item>
			<el-menu-item index="/archive">{{$t("header.archive")}}</el-menu-item>
			<el-menu-item index="/about">{{$t("header.about")}}</el-menu-item>
			<el-submenu>
				<template slot="title">{{$t("header.language")}}</template>
				<el-menu-item @click="toggleLang('zh')">{{$t("header.chinaese")}}</el-menu-item>
				<el-menu-item @click="toggleLang('en')">{{$t("header.english")}}</el-menu-item>
			</el-submenu>
		</el-menu>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				activeIndex: '/home'
			};
		},
		methods: {
			toggleLang(lang) {
				if(lang === 'zh') {
					localStorage.setItem('locale', 'zh')
					this.$i18n.locale = localStorage.getItem('locale')
					this.$message({
						message: '切换为中文！',
						type: 'success'
					})
				} else if(lang === 'en') {
					localStorage.setItem('locale', 'en')
					this.$i18n.locale = localStorage.getItem('locale')
					this.$message({
						message: 'Switch to English!',
						type: 'success'
					})
				}
			}
		}
	}
</script>

<style scoped>

</style>