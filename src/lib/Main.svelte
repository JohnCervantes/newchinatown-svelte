<script>
  import { fly } from "svelte/transition";
  import Testimonial from "./Testimonial.svelte";
  import food1 from "../assets/food1.png";
  import food2 from "../assets/food2.png";
  import food3 from "../assets/food3.png";
  import {
    MapLibre,
    NavigationControl,
    ScaleControl,
    GlobeControl,
    Marker,
  } from "svelte-maplibre-gl";
  let activeIndex = $state(0);
  const testimonials = [
    {
      id: 123,
      message: `Absolutely 100% the best restaurant in Birmingham, Chinese or
          otherwise. The owner is so incredibly sweet, and she always remembers
          you when you return! She even knows my order (and my mom's order) by
          heart, and always remembers.`,
      author: "S Gilbreath",
    },
    {
      id: 456,
      message: `I've been coming here for years. The lady who runs it is always so
          friendly no matter how busy they are. I love their delicious
          vegetarian dishes they may even have vegan options, but I'm not sure.
          Service is quick, and I love the location.`,
      author: "Y Lane",
    },
    {
      id: 789,
      message: `My favorite Chinese Restaurant... Ever. Love the food, love the
          people, love the atmosphere. Been patronizing them for decades.`,
      author: "J Newton",
    },
  ];

  const foodSlides = [
    { id: 1, url: food1 },
    { id: 2, url: food2 },
    { id: 3, url: food3 },
  ];

  $effect.root(() => {
    let intervalId = setInterval(() => {
      // Update the state
      activeIndex++;

      if (activeIndex >= foodSlides.length) {
        activeIndex = 0; // Reset the counter to 0
      }
    }, 5000);

    return () => {
      clearInterval(intervalId);
    };
  });
</script>

<main>
  <section class="flex flex-col justify-center items-center relative h-[250px]">
    <div
      class="absolute inset-0 bg-cover bg-center"
      style="background-image: url('https://www.newchinatown.net/assets/images/slides/bg.jpg'); opacity: 0.55;"
    ></div>
    <h1
      class="relative text-6xl font-bold mb-4 z-10 text-black text-shadow-xs text-shadow-black"
    >
      Welcome to New China Town
    </h1>
    <p class="relative text-2xl mb-6 text-shadow-xs text-shadow-black">
      Experience the best Chinese cuisine in town!
    </p>
    <div>
      <button
        class="relative bg-red-500 hover:bg-red-600 font-semibold text-white px-6 py-2 rounded shadow-sm shadow-grey-500"
        >ORDER ONLINE NOW</button
      >
      <button
        class="relative bg-green-800 hover:bg-green-900 text-white px-6 py-2 rounded shadow-sm shadow-grey-500"
        >View Menu</button
      >
    </div>
  </section>

  <section class="text-center">
    <h2>Our Story & Commitment</h2>
    <p class="mb-6">
      Welcome to New China Town. We pride ourselves on creating a welcoming,
      caring, and high-energy dining experience for every guest. Our promise is
      to consistently serve high-quality, authentic Chinese food.
    </p>
    <p>
      Quality You Can Taste: We use only the finest ingredients and are happy to
      accommodate requests, including cooking dishes with No M.S.G.. We believe
      in great flavor delivered through fresh ingredients and traditional
      methods. We appreciate your business and are glad you are here!
    </p>
  </section>

  <section class="bg-[#F8F8F8]">
    <h2>Popular Dishes</h2>
    <div class="relative h-[350px] w-full flex justify-center">
      {#each foodSlides as item, index (item.id)}
        {#if index === activeIndex}
          <div
            class="absolute flex justify-center"
            in:fly={{ x: -800, duration: 3000 }}
            out:fly={{ x: 800, duration: 3000 }}
          >
            <img class="h-[350px] w-[500px] bg-cover" src={item.url} alt="" />
          </div>
        {/if}
      {/each}
    </div>
  </section>

  <!-- Location -->
  <section id="location">
    <h2>Visit us</h2>
    <div class="flex justify-around w-full mb-6">
      <div>
        <h3 class="text-3xl font-semibold mb-6">Contact & Address</h3>
        <p class="font-semibold mb-2">New China Town</p>
        <p class="mb-2">1020 20th St S, Birmingham, AL 35205</p>
        <p class="mb-2">Phone: (205) 251-2373</p>
      </div>
      <div>
        <h3 class="text-3xl font-semibold mb-6">Store Hours</h3>
        <p class="mb-2">Monday - Thursday 11:00 AM – 10:00 PM</p>
        <p class="mb-2">Friday - Saturday 11:00 AM – 11:00 PM</p>
        <p class="mb-2">Sunday CLOSED</p>
      </div>
    </div>
    <div class="flex justify-center">
      <MapLibre
        class="h-[55vh] min-h-[300px] w-[150vh]"
        style="https://basemaps.cartocdn.com/gl/voyager-gl-style/style.json"
        zoom={17}
        center={{ lng: -86.79611043915874, lat: 33.501617377500146 }}
      >
        <NavigationControl />
        <ScaleControl />
        <GlobeControl />
        <Marker lnglat={[-86.79675416931279, 33.501617377500146]} />
      </MapLibre>
    </div>
  </section>

  <!-- Testimonials -->
  <section class="bg-[#F8F8F8]">
    <h2>What Our Customers Say</h2>

    <div class="relative h-[250px] w-full flex justify-center">
      {#each testimonials as item, index}
        {#if index === activeIndex}
          <div
            class="absolute flex justify-center"
            in:fly={{ x: -800, duration: 3000 }}
            out:fly={{ x: 800, duration: 3000 }}
          >
            <Testimonial message={item.message} author={item.author} />
          </div>
        {/if}
      {/each}
    </div>
  </section>
</main>
