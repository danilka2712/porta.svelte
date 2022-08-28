<script>
	import Logo from '$lib/img/logo.svg';
	import Icon from '@iconify/svelte';
	import { fly } from 'svelte/transition';
	import { expoIn,expoInOut } from 'svelte/easing';

	import { menu } from '../../stores';
	function menuTorgget() {
		menu.update((menu) => (menu = false));
	}
</script>

<div  in:fly="{{duration: 500,x: 414,opacity: 100, easing: expoIn }}" out:fly="{{duration: 500,x: -414,opacity: 100, easing: expoInOut }}" class=" bg-white fixed top-0 pt-7 w-full z-10 h-screen">
	<div class="h-[80vh]">
		<div class="flex h-full  items-end">
			<div class="mx-9 flex text-6xl font-light leading-tight flex-col text-[#121212]">
				<h1>Работы</h1>
				<h1>О нас</h1>
				<h1>Контакты</h1>
			</div>
		</div>
	</div>
</div>
