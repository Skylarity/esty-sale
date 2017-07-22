<template>
	<div class="container">
		<div class="row">
			<div class="col-md-12">
				<h1>{{ shop.shop_name }}</h1>
				<p>{{ shop.title }}</p>
				<small>by {{ shop.login_name }}</small> &mdash; <icon name="star-o" scale="0.75"></icon> {{ shop.num_favorers }}
			</div>
		</div>
	</div>
</template>

<script>
// https://www.etsy.com/developers/documentation/getting_started/oauth
// Request token URL: '/api/oauth/request_token?scope=profile_r%20shops_rw%20listings_r%20listings_w%20listings_d'

export default {
	name: 'hello',
	data() {
		return {
			baseUrl: '/api', //https://openapi.etsy.com/v2
			apiKey: 'r2hw6d0a6lynsom4rhtqa84t',
			shop: {}
		}
	},
	mounted() {
		this.$http.get(this.baseUrl + '/shops/Eqlectica' + '?api_key=' + this.apiKey)
			.then(response => {
				this.shop = response.body.results[0]
				console.log(this.shop)
			}, response => {
				console.log('error', response)
			});
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
