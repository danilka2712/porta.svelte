<script>
	import LocomotiveScrollProvider from 'svelte-locomotive-scroll';
	import '../../age.scss';
	import { menu } from '../../stores';
	import Icon from '@iconify/svelte';
	import Logo from '../../lib/img/Logo.svg';

	import { fade } from 'svelte/transition';
	import LogoWhite from '$lib/img/logowhite.svg';
	function menuTorgget() {
		menu.update((menu) => (menu = !menu));
	}
	import { page } from '$app/stores';
	import Menu from '$lib/comp/menu.svelte';
	import CartPortf from '$lib/comp/cartPortf.svelte';
</script>

<LocomotiveScrollProvider
	options={{
		smooth: true,
		direction: 'horizontal',
		smoothMobile: false,
		getDirection: true,
		getSpeed: true,
		inertia: 0.5
	}}
	watch={$page}
	location={$page.url}
	onLocationChange={(scroll) => scroll.scrollTo(0, { duration: 2, disableLerp: false })}
	imageTarget={'.grid-item-media'}
>
	<div class="w-screen ">
		<div
			class="flex sm:w-full sm:max-w-7xl relative z-30 items-center sm:px-4 mx-9 mt-9 sm:mx-auto  justify-between sm:mt-20"
		>
			<div>
				{#if $menu === true}
					<a href="/">
						<img
							in:fade={{ delay: 450, duration: 100 }}
							out:fade={{ delay: 450, duration: 5 }}
							class="w-24 absolute top-0 z-10"
							src={Logo}
							alt=""
						/>
					</a>
				{:else}
					<a href="/">
						<img
							out:fade={{ delay: 450, duration: 100 }}
							class="w-24 absolute top-0"
							src={LogoWhite}
							alt=""
						/>
					</a>
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
				<a sveltekit:reload href="/">Главная</a>
				<a sveltekit:reload href="/">О нас</a>
				<a sveltekit:reload href="contacts">Контакты</a>
			</div>
		</div>
	</div>
	{#if $menu === true}
		<Menu />
	{:else}
		<div
			out:fade={{ delay: 170, duration: 500 }}
			data-scroll-container
			class="sm:mx-36 sm:w-[10vw] mt-20   mx-9"
		>
			<div data-scroll-section class="sm:w-screen">
				<div class="sm:flex sm:gap-24">
					<div class="mt-14 sm:mr-64">
						<h1 class="text-4xl sm:text-5xl   font-light">
							Focused on <br />functionality, <br />fueled by <br />connection, <br />designed with
							<br />purpose.
						</h1>
					</div>
					<CartPortf />
					<CartPortf />
					<CartPortf />
					<CartPortf />
					<CartPortf />
				</div>
			</div>
		</div>
	{/if}
</LocomotiveScrollProvider>

<style lang="scss">
</style>
