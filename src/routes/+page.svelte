<script>
	import Icon from '@iconify/svelte';
	import { fade } from 'svelte/transition';
	import Image1 from '$lib/img/Image1.webp';
	import Image2 from '$lib/img/Image2.webp';
	import { menu } from '../stores';
	import TopMenu from '$lib/comp/topMenu.svelte';
	import Menu from '$lib/comp/menu.svelte';
	import LocomotiveScrollProvider from 'svelte-locomotive-scroll';
	import '../age.scss';

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
			<div
				out:fade={{ delay: 470, duration: 5 }}
				class=" h-[100vh] max-w-7xl mx-auto flex justify-center sm:mt-0 sm:items-center"
				data-scroll-section
			>
				<div
					class="sm:mx-32 mt-56 sm:mt-0 mb-44 mx-9 leading-normal sm:leading-tight tracking-normal text-2xl sm:text-4xl font-light"
				>
					<h1 class="">
						Комета - это агентство цифрового бренда, которое живет
						там, где сталкиваются дизайн, технологии и опыт. Мы одержимы творчеством — бросаем вызов
						тому, что есть, и в то же время определяем, что будет дальше.
					</h1>
				</div>
			</div>
			<div class="sm:h-[80vh] h-[50vh] mx-auto" data-scroll-section>
				<div class="marquee">
					<div class="track3 sm:track">
						<div class="content font-light text-[#7d7d7d] text-6xl sm:text-[110px]">
							&nbsp;Создание прототипов Интерактивный Дизайн Веб-разработка Интерактивный Дизайн
							Веб-разработка Электронная коммерция Создание прототипов
						</div>
					</div>
				</div>
				<div class="marquee2 mt-6 sm:mt-0">
					<div class="track4 sm:track2">
						<div class="content  font-light text-[#7d7d7d] text-6xl sm:text-[110px]">
							&nbsp;Создание прототипов Интерактивный Дизайн Веб-разработка Интерактивный Дизайн
							Веб-разработка Электронная коммерция Создание прототипов
						</div>
					</div>
				</div>
				<div
					class="flex mt-6  gap-5 sm:mt-14 justify-end mr-9 sm:mr-0 sm:justify-center items-center"
				>
					<h1 class="cursor-pointer text-base">Оставить заявку</h1>
					<button
						class="w-14 cursor-pointer  border-white/10 h-14 ease-in duration-300 hover:bg-blue-600 hover:scale-125 rounded-full items-center flex justify-center  border"
					>
						<Icon icon="bi:arrow-right" />
					</button>
				</div>
			</div>
			<div data-scroll-section class="h-screen mx-9 sm:mx-auto">
				<div class="flex flex-col sm:flex-row">
					<div class="sm:w-2/3 sm:h-screen">
						<img
							data-scroll
							data-scroll-speed="2"
							class="object-cover hover:opacity-50 duration-700 opacity-90 h-[50vh] sm:h-[105vh]"
							src={Image1}
							alt=""
						/>
					</div>
					<div data-scroll data-scroll-speed="2" class="sm:w-1/2 flex flex-col sm:ml-36">
						<div class="mt-20">
							<h1 class="sm:text-3xl text-2xl font-semibold">Портфолио</h1>
							<p
								class="text-[#7d7d7d] text-[32px] sm:text-5xl mt-8 leading-tight tracking-normal font-light"
							>
								Верим в каждый проект<br />и доводим все до идеала
							</p>
						</div>
						<div class="sm:w-1/3 flex items-center gap-5 mt-14">
							<h1 class=" text-base">Услуги агенства</h1>
							<button
								class="w-14  border-white/10 h-14 ease-in duration-300 hover:bg-blue-600 hover:scale-125 rounded-full items-center flex justify-center  border"
							>
								<Icon class="" icon="bi:arrow-right" />
							</button>
						</div>
					</div>
				</div>
			</div>
			<div data-scroll-section class="h-screen flex  pb-28 mt-44 sm:mt-0 my-10">
				<div class="flex sm:flex-row flex-col-reverse mx-9  sm:mx-0 w-full">
					<div class="flex flex-col mt-20 sm:ml-36 sm:w-2/3 justify-end">
						<div>
							<h1 class="sm:text-3xl text-2xl font-semibold">Наши услуги</h1>
							<p class="text-[#7d7d7d] text-[32px] sm:text-5xl mt-8  leading-tight font-light">
								Мы беремся за проекты<br />любой сложности.<br />Культивируем дедлайн и<br />сервис.
							</p>
						</div>
						<div class="sm:w-1/3 flex items-center gap-5 mt-14">
							<h1 class=" text-base">Услуги агенства</h1>
							<button
								class="w-14  border-white/10 h-14 ease-in duration-300 hover:bg-blue-600 hover:scale-125 rounded-full items-center flex justify-center  border"
							>
								<Icon class="" icon="bi:arrow-right" />
							</button>
						</div>
					</div>
					<div class="sm:w-1/2 sm:-mt-32 h-screen">
						<img
							data-scroll
							data-scroll-speed="2"
							class="object-cover opacity-90 hover:opacity-50 duration-700 w-full h-[50vh] sm:h-[120vh]"
							src={Image2}
							alt=""
						/>
					</div>
				</div>
			</div>
			<div data-scroll-section class="sm:h-[60vh] h-[40vh] w-full flex my-10 mx-auto">
				<div class="flex flex-col w-full mx-9 sm:mx-0 sm:justify-center mb-32 sm:items-center ">
					<div
						class="leading-normal sm:leading-tight tracking-normal text-2xl sm:text-4xl font-light"
					>
						<h1 class=" font-light">
							Мы объединяем <span class="font-normal">идеи</span>, возможности и неожиданные <br /> выражения
							в резонансный опыт бренда.
						</h1>
					</div>
					<div class=" flex  items-center gap-5 mt-14">
						<h1 class=" text-base">Оставить заявку</h1>
						<button
							class="w-14 border-white/10 h-14 ease-in duration-300 hover:bg-blue-600 hover:scale-125 rounded-full items-center flex justify-center  border"
						>
							<Icon class="" icon="bi:arrow-right" />
						</button>
					</div>
				</div>
			</div>
			<div data-scroll-section class="h-[110vh] bg-[#f4f4f4] flex mx-auto">
				<div class="flex  w-full max-w-7xl mx-9 sm:mx-auto mt-40 items-start ">
					<h1 class="text-[#757574] text-4xl sm:text-6xl">
						Начинаете новый проект и хотите<br /> сотрудничать с нами?
					</h1>
				</div>
			</div>
		{/if}
	</div>
</LocomotiveScrollProvider>

<style>
</style>
