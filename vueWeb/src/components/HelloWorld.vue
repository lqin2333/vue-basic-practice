<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
	<button class="btn btn-primary">wow</button>
	{{content}}
  </div>
</template>

<script>
export default {
	name: 'HelloWorld',
	data () {
		return {
			msg: 'Welcome to Your Vue.js App',
			content: "",
		}
	},
	// after init, invoke this
	mounted(){
		this.axios.post("http://api.komavideo.com/news/list").then(body=> {
			this.content = body.data;
		});
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
