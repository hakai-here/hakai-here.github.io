<script>
	import { onMount, onDestroy } from "svelte";
	import { fly } from "svelte/transition";
	const scrollNavBar = 300;
	let show = false;
	let toggle = false;
	function scrollto({target}){
		toggle =!toggle
		const el = document.querySelector(target.getAttribute("href"));
		if (!el) return;
		el.scrollIntoView({behavior: "smooth"});
	}

	onMount(() => {
		window.onscroll = () => {
			if (window.scrollY > scrollNavBar) {
				show = true;
			} else {
				show = false;
				toggle=false;
			}
		};
	});

	onDestroy(() => {
		window.onscroll = () => {};
	});
</script>

<nav class:scrolled={show}>
	<div class="left-nav">D8rkmind</div>
	<div class="right-nav">
		<ul>
			<li href="#about" on:click={scrollto}>About</li>
			<li href="#works" on:click={scrollto}>Works</li>
		</ul>
	</div>
	<div class="hamburger" on:click|preventDefault={() => (toggle = !toggle)}>
		<div>---</div>
		<div>---</div>
		<div>---</div>
	</div>
	{#if toggle}
		<div class="sidemenu" in:fly={{ x: -300 }} out:fly={{ x: -300 }}>
			<ul>
				<li href="#about" on:click={scrollto}>About</li>
				<li href="#works" on:click={scrollto}>Works</li>
			</ul>
		</div>
	{/if}
</nav>

<style>
	.scrolled {
		transform: translate(0, calc(-100% - 1rem));
	}

	nav {
		z-index: 2;
		width: 100%;
		height: 60px;
		position: fixed;
		transition: 0.5s ease;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 10rem;
	}
	.left-nav {
		font-size: 30px;
	}
	.right-nav ul {
		font-size: 20px;
		display: flex;
		flex-direction: row;
		list-style: none;
	}
	.right-nav ul li {
		cursor: pointer;
		text-transform: capitalize;
		margin-right: 2rem;
		transition: 0.3s ease;
	}
	.right-nav ul li:hover {
		color: rgb(196, 52, 52);
	}
	.hamburger {
		display: none;
		cursor: pointer;
	}
	.hamburger:hover {
		color: red;
	}
	.sidemenu {
		width: 100%;
		height: 100vh;
		background-color: #fff;
		position: fixed;
		top: 60px;
		left: 0;
		z-index: 2;
		font-size: 30px;
		display: none;
	}
	@media screen and (max-width: 850px) {
		nav{
			padding: 0 5rem;
		}
		.right-nav {
			display: none;
		}
		.hamburger {
			display: block;
			line-height: 50%;
		}
		.sidemenu {
			display: block;
			z-index: 10;
			background-color: #fff;
		}
		.sidemenu ul {
			padding-top: 10px;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			list-style: none;
		}
		.sidemenu ul li {
			margin-bottom: 10px;
		}
		.sidemenu ul li:hover {
			color: rgb(196, 52, 52);
		}
	}
</style>
