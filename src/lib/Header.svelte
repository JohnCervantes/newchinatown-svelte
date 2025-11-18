<script>
  const scrollToLocation = () => {
    const targetElement = document.getElementById("location");
    if (targetElement) {
      requestAnimationFrame(() => {
      window.scrollTo({
        top: targetElement.offsetTop,
        behavior: 'smooth'
      });
    });
    }
  };
</script>

<header class="sticky top-0 z-20">
  <nav>
    <ul class="flex gap-8 p-4 bg-green-800 text-white items-center">
      <li class="text-red-600 font-bold text-2xl"><a href="/">New China Town</a></li>
      <li class="ml-auto"><a href="/menu">Menu</a></li>
      <li><a href="#0" on:click={scrollToLocation}>Location</a></li>
      <li class="bg-red-500 hover:bg-red-600 font-semibold text-white px-6 py-2 rounded shadow-sm shadow-grey-500"><a href="/">Order Online</a></li>
    </ul>
  </nav>
</header>
