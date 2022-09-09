<script>
	import { fly } from 'svelte/transition';
	import { expoIn } from 'svelte/easing';

	import { menu } from '../../stores';

</script>
<div
	in:fly={{ duration: 500, x: 414, opacity: 100, easing: expoIn }}
	out:fly={{ duration: 500, x: -414, opacity: 100, easing: expoIn }}
	class=" bg-white fixed top-0 pt-7 w-full z-10 h-screen"
>
	<div class="h-[80vh]">
		<div class="flex h-full  items-end">
			<div class="mx-9 flex text-6xl font-light leading-tight flex-col text-[#121212]">
				<a sveltekit:reload href="/about">Работы</a>
				<a href="/">О нас</a>
				<a sveltekit:reload href="/contacts">Контакты</a>
			</div>
		</div>
	</div>
</div>
