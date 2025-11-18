<script>
  const coupons = [
    {
      name: "Free Eggroll",
      description:
        "with $30 or more (before tax) Order (does not include Lunch)",
      price: 0,
    },
    {
      name: "Free Chinese Donut",
      description:
        "with $40 or more (before tax) Order (does not include Lunch)",
      price: 0,
    },
    {
      name: "Free Fried Dumpling",
      description:
        " with $50 or more (before tax) Order (does not include Lunch)",
      price: 0,
    },
  ];

  const appetizers = [
    {
      name: "Egg Roll",
      description: "",
      price: 2.25,
    },
    {
      name: "Spring Roll (2)",
      description: "",
      price: 3.5,
    },
    {
      name: "Fried Wonton (10)",
      description: "",
      price: 5.5,
    },
  ];

  const lomein = [
    {
      name: "Chicken Lo Mein",
      description: "",
      price: 10.45,
    },
    {
      name: "Roast Pork Lo Mein",
      description: "",
      price: 10.45,
    },
    {
      name: "Shrimp Lo Mein",
      description: "",
      price: 10.45,
    },
    {
      name: "Beef Lo Mein",
      description: "",
      price: 10.45,
    },
  ];
</script>

<section class="flex flex-col justify-center m-6 items-center">
  <div
    class="flex flex-col p-12 border w-[80%] border-gray-600 rounded-xl shadow-lg shadow-gray-300 mb-6"
  >
    <h2 class="border-b-3 border-amber-500 pb-3">Hot Deals & Coupons</h2>
    {#each coupons as item, index}
      <div class="flex">
        <p class="w-[80%]">
          <strong>{item.name}</strong><br />
          <span class="text-sm text-gray-600">{item.description}</span>
        </p>
        <p><strong>${item.price}</strong></p>
      </div>
    {/each}
  </div>

  <div
    class="flex flex-col p-12 border w-[80%] border-gray-600 rounded-xl shadow-lg shadow-gray-300 mb-6"
  >
    <h2 class="border-b-3 border-amber-500 pb-3">Appetizers</h2>
    {#each appetizers as item, index}
      <div class="flex">
        <p class="w-[80%]">
          <strong>{item.name}</strong><br />
          <span class="text-sm text-gray-600">{item.description}</span>
        </p>
        <p><strong>${item.price}</strong></p>
      </div>
    {/each}
  </div>

  <div
    class="flex flex-col p-12 border w-[80%] border-gray-600 rounded-xl shadow-lg shadow-gray-300"
  >
    <h2 class="border-b-3 border-amber-500 pb-3">Lo Mein</h2>
    {#each lomein as item, index}
      <div class="flex">
        <p class="w-[80%]">
          <strong>{item.name}</strong><br />
          <span class="text-sm text-gray-600">{item.description}</span>
        </p>
        <p><strong>${item.price}</strong></p>
      </div>
    {/each}
  </div>
</section>
