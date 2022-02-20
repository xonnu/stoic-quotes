<script>
  import logo from './assets/svelte.png'
  let counter = 0;
</script>

<main class="h-screen w-full bg-black flex flex-col items-center justify-center">
  <img src={logo} class="w-20 mb-10" alt="">
  <h2 class="font-sans text-white text-2xl">Chrono Svelte Template</h2>
  <button class="mt-4 p-4  rounded-lg bg-white" on:click={()=> {counter++}}>Counter: {counter}</button>
</main>

<style>

</style>
