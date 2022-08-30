<script>
	import { fly } from 'svelte/transition';
	import { expoIn } from 'svelte/easing';

	import { menu } from '../../stores';
	function menuTorgget() {
		menu.update((menu) => (menu = !menu));
	}
</script>
<div
	in:fly={{ duration: 500, x: 414, opacity: 100, easing: expoIn }}
	out:fly={{ duration: 500, x: -414, opacity: 100, easing: expoIn }}
	class=" bg-white fixed top-0 pt-7 w-full z-10 h-screen"
>
	<div class="h-[80vh]">
		<div class="flex h-full  items-end">
			<div class="mx-9 flex text-6xl font-light leading-tight flex-col text-[#121212]">
				<a on:click={menuTorgget} href="/">Работы</a>
				<a href="/">О нас</a>
				<a href="/">Контакты</a>
			</div>
		</div>
	</div>
</div>
