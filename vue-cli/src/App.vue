<template>
	<div>
		<!-- <AppHeader v-bind:프롭스 속성이름="상위 컴포넌트의 데이터이름"></AppHeader> -->
		<AppHeader v-bind:propsdata="str" v-on:renew="renewString"></AppHeader>
	</div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";

export default {
	// new Vue({
	//   data: {
	//     str: 'hi!'
	//   }
	// })
	data: function () {
		return {
			str: "Header!!!~~",
		};
	},
	components: {
		AppHeader,
	},
	methods: {
		renewString: function () {
			this.str = "Header";
		},
	},
};
</script>

<style></style>
