<template>
	<div class="container">
		<div class="row">
			<div class="col-12">
				<h1>Etsy Sale</h1>
			</div>
		</div>
		<div class="row">
			<div class="col-12">
				<button class="btn btn-outline-success" @click="test">Test</button>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'hello',
	data () {
		return {
			msg: 'Welcome to Your Vue.js App'
		}
	},
	methods: {
		test() {
			let xmlhttp = new XMLHttpRequest()

			// https://openapi.etsy.com/v2/users/__SELF__/favorites
			this.$http.get('https://openapi.etsy.com/v2/etsystore?api_key=r2hw6d0a6lynsom4rhtqa84t')
				.then(response => {
					console.log(response)
				}, response => {
					console.log('error', response)
				});
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h1, h2 {
	font-weight: normal;
}

ul {
	list-style-type: none;
	padding: 0;
}

li {
	display: inline-block;
	margin: 0 10px;
}

a {
	color: #42b983;
}
</style>
