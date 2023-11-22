<script>
  import Pelicula from "./lib/Pelicula.svelte";
  let peliculas = [];

  const cargarPelicula = async () => {
    try {
      const response = await fetch("http://localhost:8080/peliculas");
      if (response.status == 200) {
        const data = await response.json();
        peliculas = data;
      }
    } catch (error) {
      console.log(error);
    }
  };
  cargarPelicula();
</script>

<div class="container">
  <div class="grid">
    {#each peliculas as pelicula}
      <Pelicula {pelicula} />
    {/each}
  </div>
</div>

<style>
</style>
