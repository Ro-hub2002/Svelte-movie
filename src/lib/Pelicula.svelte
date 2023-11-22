<script>
  export let pelicula;
</script>

<div class="movie-card">
  <img class="movie-image" src={pelicula.portada} alt={pelicula.nombre} />
  <div class="movie-details">
    <h1 class="movie-title">{pelicula.nombre}</h1>
  </div>
</div>
