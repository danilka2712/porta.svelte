<script>
	import Image from '../img/screencapture.jpg';
    const items = [
        {id: 1 , name: "Автоподбор", text: "Сделали удобный сайт для Омской компании автоподбора"}
    ]
</script>

<div class="sm:mt-0 mt-32">
    <div class="overflow-hidden sm:w-[22.5rem] h-[25.5rem]">
        <img
            class="object-cover hover:scale-105 duration-500 w-[22.5rem] h-[25.5rem]"
            src={Image}
            alt=""
        />
    </div>
    {#each items as i}
    <div class="mt-5">
        <h1 class="text-2xl font-semibold">{i.name}</h1>
        <p class=" text-[#d5d5d5]">{i.text}</p>
    </div>
    {/each}
   
</div>