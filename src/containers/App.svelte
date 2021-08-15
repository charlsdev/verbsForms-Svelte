<script>
	import Loader from "../components/loader.svelte";
	import TableUI from "../components/table.svelte";
	import Header from "../components/header.svelte";
	import Footer from "../components/footer.svelte";
	// import dataVerbs from "../listVerbs.json";

	let dataVerbs;

	const listVerbs = async () => {
		const response = await fetch('http://localhost:2021/listVerbs');
		dataVerbs = await response.json();
		// console.log(dataVerbs);
	}

	listVerbs();

	const alertNot = () => {
		Swal.fire({
			title: 'Ningun dato',
			text: 'No existe ningun dato, o refresque la página...',
			icon: 'info',
			allowOutsideClick: false
		})
	}
</script>

<main>
	<Loader />
	<Header />
   
	{#if dataVerbs}
   <TableUI listVerbs={dataVerbs.searchVerbs}/>
	{/if}

   <Footer />
</main>