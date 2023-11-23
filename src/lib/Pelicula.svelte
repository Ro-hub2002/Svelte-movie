<script>
  export let pelicula;
</script>

<div class="movie-card">
  <img
    class="movie-image"
    src={pelicula.portada}
    alt={pelicula.nombre}
    loading="lazy"
  />
  <div class="movie-details">
    <h1 class="movie-title">{pelicula.nombre}</h1>
    <div class="movie-info">
      <p><strong>Director:</strong> {pelicula.director}</p>
      <p>
        <strong>Director:</strong>
        {pelicula.genero.charAt(0).toUpperCase() + pelicula.genero.slice(1)}
      </p>
      <p>
        <strong>Año:</strong>
        {new Date(pelicula.ano).getFullYear()}
      </p>
    </div>
  </div>
</div>
