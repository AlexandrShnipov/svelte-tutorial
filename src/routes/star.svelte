<script>
	let sky = '';
	let star = '☆';
	$: numberOfStars = sky.length;
	let buttonDisabled = false;

	const addStar = () => {
		sky += star;
		if (numberOfStars === 4) {
			buttonDisabled = true;
		}
	}

	let planets = ['mercury', 'venus', 'earth'];
</script>


<svelte:head>
	<title>Star</title>
	<meta name='description' content='Star tutorial' />
</svelte:head>

<h1>{sky || 'empty'}</h1>

<button on:click={addStar}
				disabled={buttonDisabled}>add star
</button>
<!--{	console.log(sky.length) }-->

<p>I added {numberOfStars} {numberOfStars > 1 ? 'stars' : 'star'}</p>

<hr align='left' width='100%' size='2' color='#ff0000'>

<p>  {planets}</p>
<button on:click={()=> planets = [...planets, 'mars']}>add planet</button>

<hr align='left' width='100%' size='2' color='#ff0000'>

<style>

    h1 {
        color: red;
    }

    button {
        width: fit-content;
        padding: .2rem;
        background-color: aquamarine;
    }

</style>