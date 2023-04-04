<template>
	<form v-on:submit.prevent="submitForm">
		<div>
			<label for="username">id:</label>
			<input id="username" type="text" v-model="username" />
		</div>
		<div>
			<label for="password">pw:</label>
			<input id="password" type="password" v-model="password" />
		</div>
		<button type="submit">login</button>
	</form>
</template>

<script>
import axios from "axios";

export default {
	data: function () {
		return {
			username: "",
			password: "",
		};
	},
	methods: {
		submitForm: function () {
			console.log(this.username, this.password);
			var url = "https://jsonplaceholder.typicode.com/users";
			var data = {
				username: this.username,
				password: this.password,
			};
			axios
				.post(url, data)
				.then(function (response) {
					console.log(response);
				})
				.catch(function (error) {
					console.log(error);
				});
		},
	},
};
</script>

<style>
label {
	display: inline-block;
	width: 80px;
}
form input {
	padding: 8px;
	border: 1px solid #ddd;
	border-radius: 0;
}
form > div {
	margin-bottom: 12px;
}
button {
	border: none;
	padding: 8px;
	width: 120px;
}
</style>
