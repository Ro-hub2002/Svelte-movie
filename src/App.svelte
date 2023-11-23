<script>
  import Pelicula from "./lib/Pelicula.svelte";
  let peliculas = [];
  let busqueda = "";
  let resultados = [];

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

  function buscarPelicula() {
    resultados = peliculas.filter((pelicula) =>
      pelicula.nombre.toLowerCase().includes(busqueda.toLowerCase())
    );
  }
  $: buscarPelicula();

  
</script>

<input
  class="buscador"
  type="text"
  bind:value={busqueda}
  placeholder="Buscar por nombre"
  on:input={buscarPelicula}
/>

<div class="movie-container">
  {#each peliculas as pelicula (pelicula.nombre)}
    <Pelicula {pelicula} />
  {/each}
</div>

<div class="sidebar" class:open>
  <h3 class="fs-4">Géneros</h3>
  <div class="botones-container">
    <button class="boton" type="button">Acción</button>
    <button class="boton" type="button">Drama</button>
    <button class="boton" type="button">Aventura</button>
    <button class="boton" type="button">Suspenso</button>
    <button class="boton" type="button">Guerra</button>
    <button class="boton" type="button">Misterio</button>
    <button class="boton" type="button">Guerra</button>
    <button class="boton" type="button">Ciencia Ficción</button>
    <button class="boton" type="button">Musical</button>
    <button class="boton" type="button">Crimen</button>
  </div>
</div>

<style>
</style>
