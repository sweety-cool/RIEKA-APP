<script>
	import { request } from 'graphql-request';
	function get() {
		request(
			'https://y6sjtt8g.directus.app/graphql',
			`{
           
   Products {
    Content
    Category {
      Title
    }
    Subscrib {
      Title
    }
  }
  }`
		).then((data) => {
			console.log(data);
			PRODUCTS = data.Products;
		});
	}
	let PRODUCTS = [];
</script>

<h1>hello this is stream page</h1>
<button on:click={get}>GET</button>
{#each PRODUCTS as P}
	<div class="product">
		<h1>Content:{P.Content}</h1>
		<p>Shows:{P.Category.Title}</p>
		<p>Subscribe:{P.Subscrib.Title}</p>
	</div>
{/each}

<style>
	.product {
		background: #fcfcfc;
		border: 1px solid #000;
		margin: 1rem;
		padding: 1rem;
	}
</style>
