<script>
	import { menu } from '../../stores';
	import TopMenu from '$lib/comp/topMenu.svelte';
	import Menu from '$lib/comp/menu.svelte';
    import { copy } from 'svelte-copy';
	import LocomotiveScrollProvider from 'svelte-locomotive-scroll';
	import '../../age.scss';
	import Icon from '@iconify/svelte';
import image3 from '../../lib/img/image3.jpg'
	import { page } from '$app/stores';
	let position = 'vertical';
</script>

<LocomotiveScrollProvider
	options={{
		smooth: true,
		direction: `${position}`,
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
	<div data-scroll-container>
		<TopMenu />
		{#if $menu === true}
			<Menu />
		{:else}
			<div data-scroll-section class="">
				<div class="h-screen max-w-7xl mx-auto px-4 w-screen ">
					<div class="mx-5">
						<div
							class=" sm:mt-20 mt-96  sm:leading-tight tracking-normal text-3xl sm:text-4xl font-light"
						>
							<h1>
								Если вы заинтересованы <br /> в сотрудничестве, свяжитесь <br /> с нами любым удобным
								способом.
							</h1>
						</div>
						<div class="mt-20">
							<h1 class="text-2xl font-normal text-[#7d7d7d]">Связаться</h1>
						</div>
						<div class="flex mt-4 gap-4 items-center">
							<h1 use:copy={"cometa@yandex.ru"} class="text-lg cursor-pointer">cometa@yandex.ru</h1>
							<button
								class="w-14 cursor-pointer  border-white/10 h-14 ease-in duration-300 hover:bg-blue-600 hover:scale-125 rounded-full items-center flex justify-center  border"
							>
								<Icon icon="bi:arrow-right" />
							</button>
						</div>
					</div>
                    <div class="sm:w-1/2 w-screen h-96 opacity-80 -top-10 left-0 sm:top-auto sm:left-auto sm:h-screen absolute sm:bottom-0 sm:right-0">
                        <img class="object-cover opacity-80 w-full h-full" src={image3} alt="">
                    </div>
				</div>
			</div>
		{/if}
	</div>
</LocomotiveScrollProvider>

<style>
</style>
