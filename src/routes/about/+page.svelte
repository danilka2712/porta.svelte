<script>
	import LocomotiveScrollProvider from 'svelte-locomotive-scroll';
	import '../../age.scss';
	import { menu } from '../../stores';
	import Icon from '@iconify/svelte';
	import Logo from '$lib/img/logo.svg';
	import { fade } from 'svelte/transition';
	import LogoWhite from '$lib/img/logowhite.svg';

	function menuTorgget() {
		menu.update((menu) => (menu = !menu));
	}
	import { page } from '$app/stores';
import Menu from '$lib/comp/menu.svelte';
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
				<a sveltekit:reload href="/">Портфолио</a>
				<a href="/">О нас</a>
				<a href="/">Контакты</a>
			</div>
		</div>
	</div>
	{#if $menu === true}
		<Menu/>
		{:else}
		<div out:fade={{ delay: 470, duration: 5 }} data-scroll-container class="sm:mx-36 mx-9 mt-32">
			<div data-scroll-section class="sm:w-screen  h-screen">
				<div class="mt-20">
					<h1 class=" text-5xl font-light">
						Focused on <br />functionality, <br />fueled by <br />connection, <br />designed with
						<br />purpose.
					</h1>
				</div>
			</div>
			<div data-scroll-section class="sm:w-screen h-screen">
				<h1>1</h1>
			</div>
			<div data-scroll-section class="sm:w-screen h-screen">
				<h1>1</h1>
			</div>
		</div>
		{/if}
</LocomotiveScrollProvider>

<style lang="scss">
</style>
