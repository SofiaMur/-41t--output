<script>
    import { onMount } from "svelte";
    const endpoint = "https://jsonplaceholder.typicode.com/posts";
    let articles = [];

    onMount(async function () {
        const response = await fetch(endpoint);
        const data = await response.json();
        articles = data;
    });
</script>

<main>
    <div class="container lg:grid-cols-3 md:grid-cols-2 sm:grid-cols-1">
        {#each articles as article}
            <div class="card">
                <!-- <img src={article.urlToImage} /> -->
                <img
                    src="https://media.minecraftstation.com/2020/05/2020-05-15_22.50.06-copy-768x677.png"
                    alt="example"/>
                <p class="card-text-title">
                    {article.title}
                </p>
                <p class="card-text-body">
                    {article.body}...
                </p>
                <!-- <a href={article.url} class="card-link">
                    Читать далее...</a> -->
                <a href="https://youtu.be/ClldamscA0I" class="card-link">
                    Читать далее...</a>
            </div>
        {/each}
    </div>
</main>

<style>
    .container {
        @apply inline-grid gap-2 p-3 border border-black;
    }

    .container > .card img {
        @apply rounded-md;
    }

    .card {
        @apply m-3 p-3 w-80 select-none shadow-md border rounded-tl-md rounded-r-md border-black;
    }

    .card-text-title {
        @apply font-semibold text-center text-base my-2;
    }

    .card-text-body {
        @apply text-sm line-clamp-4;
    }

    .card-link {
        @apply text-xs italic;
    }
</style>
