<script>
  import Output from "./lib/Output.svelte";
</script>

<main>
  <div class="flex-col">
    <h1 class="font-bold p-3 text-xl">Новости</h1>
    <Output />
  </div>
</main>

<style>
  * {
    @apply flex items-center justify-center;
  }
</style>
