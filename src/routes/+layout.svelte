<script>
	import '../app.css';
</script>

<div class="flex flex-col h-screen bg-black text-slate-100">
	<nav class="flex flex-col">
		<div class="justify-center flex">
			<div><img src="src/routes/SW73.jpeg" alt="SW73" class="w-60" /></div>
		</div>
		<div class="flex text-center">
			<div class="navlink"><a href="/events">Upcoming Events</a></div>

			<div class="navlink"><a href="/about">About</a></div>
			<div class="navlink"><a href="/rules">Rules</a></div>
			<div class="navlink"><a href="/">Membership</a></div>
		</div>
	</nav>
	<main class="bg-zinc-950 text-slate-100 flex-1 p-4"><slot /></main>
</div>

<style lang="postcss">
	.navlink {
		@apply hover:text-orange-400 transition-colors duration-500 cursor-pointer flex-1;
	}
</style>
