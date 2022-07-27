<script>
	import '../app.css';
	//import {onMount} from 'svelte';

	let isPageLoaded = false;

	// onMount(() => {
	// 	isPageLoaded = true;
	// })

	const pageLoaded = () => {
		isPageLoaded = true;
	}

</script>


{#if !isPageLoaded}
	<div class='loading-wrap' use:pageLoaded >
		<div class="loading"></div>
	</div>
{/if}


<style>

    .loading-wrap{
        position: fixed;
        top:0;
        right: 0;
        bottom: 0;
        left: 0;
        background-color: rgba(47, 53, 59, .5);
        display: grid;
        place-items: center;
        z-index: 9999;
    }

    .loading {
        height: 10rem;
        width: 10rem;
        border-radius: 50%;
        border-top: 5px solid rgb(255, 255, 255);
        animation: is-loading 1s linear infinite;
    }

    @keyframes is-loading {
        0% {
            transform: rotate(0deg);
        }

        100% {
            transform: rotate(360deg);
        }
    }

</style>
