<!-- Script JS -->
<script>
    var x = 67;
    x = Math.round(x/10)
    const images = []
    for(let i =0;i<x;i++ ){
        images.push("./images/podrida1.png")
    }
    for(let i=0;i<10-x;i++){
        images.push("./images/zanahoria.webp")
    }

</script>

<!-- Estructura contenido HTML -->
<!-- cantidad de tiempo de vida de la zanahoria o x% zanahorias podridas doenfjwebfjbweflkdflsdn -->
<input type="number" bind:value={x}>
<div class="grid">
    {#each images as image}
      <img src={image} alt="Imagen">
    {/each}
  </div>

<!-- Estilos CSS -->
<style> 
.grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-gap: 10px;
  grid-auto-rows: minmax(2, auto);
}
img{
    height: 100px;
    width: 100px;
}
</style>
