<script>
	import { request } from 'graphql-request';

	function get() {
		request(
			'https://y6sjtt8g.directus.app/graphql',
			`{
           
Products (search: "${search}"){
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
	let search = '';
</script>

<h1 class="text-4xl text-center my-8">Rieka</h1>
<div class="text-center">
	<input bind:value={search} placeholder="Search Shows" class="text-xl text-center " />
	<button class="text-xl text-center my-5" on:click={get}>Search</button>
</div>
<br />
{#each PRODUCTS as P}
	<div class="product">
		<h1>Content:{P.Content}</h1>
		<p>{P.Category.Title}</p>
		<p>{P.Subscrib.Title}</p>
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
