<script lang="ts">
	export let data;
	import MaterialSymbolsMenu from '~icons/material-symbols/menu';
	let nav: HTMLDivElement;
	const tognav = () => {
		if (nav.classList.contains('hidden')) {
			nav.classList.remove('hidden');
			nav.classList.add('flex');
		} else {
			nav.classList.add('hidden');
			nav.classList.remove('flex');
		}
	};
</script>

<h2 class="text-center bg-blue-600 text-white py-1 text-xl">
	Nem vagy biztos valamiben? Nézd meg a <a href="/user/help" class="text-yellow-400 font-bold"
		>segédletet</a
	>!
</h2>
<nav class="bg-gray-700 grid grid-cols-2 lg:flex text-white justify-between items-center py-2">
	<div class="flex items-center gap-2 ml-[10vw] align-middle content-center">
		<img
			src="/favicon.png"
			class="pointer-events-none drop-shadow-xl"
			width="40"
			height="40"
			alt="SCKK Logó"
		/>
		<a href="/info" class="font-bold text-3xl drop-shadow-xl">SCKK</a>
	</div>
	<div
		bind:this={nav}
		class="gap-2 z-10 text-xl col-span-2 lg:col-span-1 flex-col flex items-center text-center mr-[10vw] lg:flex-row lg:gap-5 xl:gap-10 2xl:gap-20 lg:z-auto child:drop-shadow-xl"
	>
		<div class="relative w-full group z-10">
			<button class="hover:text-blue-500 duration-200 transition-all text-3xl peer"
				><MaterialSymbolsMenu /></button
			>
			<div
				class="absolute z-[99] flex flex-col top-[100%] left-[50%] translate-x-[-50%] rounded-md overflow-hidden shadow-lg min-w-[200px] w-max peer-focus:visible peer-focus:opacity-100 opacity-0 invisible duration-200 p-1 bg-gray-100 dark:bg-slate-800 border border-dimmed text-lg md:text-lg"
			>
				<a href="/user" class="hover:text-blue-500 duration-200 transition-all">Kezdőlap</a>
				<a href="/user/help" class="hover:text-blue-500 duration-200 transition-all">Segédlet</a>
				<a href="/user/potlekok" class="hover:text-blue-500 duration-200 transition-all">Pótlékok</a
				>
				<a href="/user/leintesek" class="hover:text-blue-500 duration-200 transition-all"
					>Leintések</a
				>
				<a href="/user/szamlak" class="hover:text-blue-500 duration-200 transition-all"
					>Szereltetési számlák</a
				>
				{#if data.layout?.admin}
					<a href="/user/admin" class="hover:text-blue-500 duration-200 transition-all"
						>Műszakvezetés</a
					>
				{/if}
			</div>
		</div>
	</div>
</nav>

<slot />
