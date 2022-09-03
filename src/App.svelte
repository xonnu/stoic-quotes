<script>
  import { onMount } from "svelte" 

  const end_point = 'https://stoicquotesapi.com/v1/api/quotes/random';  
  let quote, author = null;
  
  onMount(async function() { 
    const response = await fetch(end_point); 
    const data = await response.json();
    
    quote = data.body
    author = data.author
  })

</script>

<main class="w-full h-screen">
  <div class="container mx-auto flex items-center justify-center h-full px-4">
    <div class="max-w-[1000px] flex flex-col gap-10">
      {#if quote == undefined}
        <h2 class="font-primary text-2xl md:text-5xl leading-snug">Loading...</h2>
      {:else}
         <h2 class="font-primary text-2xl md:text-5xl md:leading-tight font-[500]">{ quote }</h2>
        <p class="text-left block w-full font-secondary">— {author}</p>
      {/if}
    </div>
  </div>
</main>

<footer class="absolute bottom-0 w-full">
  <p class="text-gray-300 font-secondary text-sm p-4 text-center block w-full ">Created by <a class="underline underline-offset-2 decoration-2" href="http://github.com/devkurono" target="_blank" rel="noopener noreferrer">Kurono</a></p>
</footer>

<style>

</style>
