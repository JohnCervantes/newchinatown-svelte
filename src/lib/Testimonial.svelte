<script>
  let { message, author } = $props();
</script>

<div
  class="border-l-4 border-red-500 bg-[#F8F8F8] rounded-md p-4 max-w-sm text-xl shadow-md shadow-gray-300"
>
  <p>
    <em>“ {message} ”</em>
  </p>
  <p class="font-semibold text-red-500">- {author}</p>
</div>
