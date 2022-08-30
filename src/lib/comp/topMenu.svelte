<script>
	import { menu } from '../../stores';
	import Icon from '@iconify/svelte';
	import Logo from '$lib/img/logo.svg';
	import { fade } from 'svelte/transition';
	import LogoWhite from '$lib/img/logowhite.svg';
	
	function menuTorgget() {
		menu.update((menu) => (menu = !menu));
	}
</script>

<div data-scroll-section class=" relative">
	<div
		class="flex max-w-7xl relative z-30 items-center sm:px-4 mx-9 mt-9 sm:mx-auto  justify-between sm:mt-20"
	>
		<div>
			{#if $menu === true}
				<img
					in:fade={{ delay: 450, duration: 100 }}
					out:fade={{ delay: 450, duration: 5 }}
					class="w-24 absolute top-0 z-10"
					src={Logo}
					alt=""
				/>
			{:else}
				<img
					out:fade={{ delay: 450, duration: 100 }}
					class="w-24 absolute top-0"
					src={LogoWhite}
					alt=""
				/>
			{/if}
		</div>
		<div on:click={menuTorgget} class="flex sm:hidden">
			{#if $menu === true}
				<Icon width="24" class="text-black" icon="ci:menu-duo" />
			{:else}
				<Icon width="24" class=" " icon="ci:menu-duo" />
			{/if}
		</div>
		<div class="sm:flex hidden gap-10">
			<a sveltekit:reload href="/about">Портфолио</a>
			<a href="/">О нас</a>
			<a href="/">Контакты</a>
		</div>
	</div>
</div>
