<!-- Script JS -->
<script>
    var x = 0;
    //x = Math.round(x/10)
    // comente esto porque me arruinaba la vida
    const images = []

    function updateImages(){
        if(x>100){ // este if lo agregue porque si no te mete tantas imagenes como quieras
            x=100 // esto limita el numero de imagenes a 10
        }
        images.length = 0
        for(let i =0;i<x;i++ ){
            images.push("./images/podrida2.png")
        }
        for(let i=0;i<100-x;i++){
            images.push("./images/zanahoria2.jpg")
        }
    }
    /*
    for(let i =0;i<x;i++ ){
        images.push("./images/podrida1.png")
    }
    for(let i=0;i<10-x;i++){
        images.push("./images/zanahoria.webp")
    }
    */
    $: updateImages();
    console.log(x)
</script>

<!-- Estructura contenido HTML -->
<!-- cantidad de tiempo de vida de la zanahoria o x% zanahorias podridas doenfjwebfjbweflkdflsdn -->
<h1>Cantidad de zanahorias podridas, por cada 10 que se encuentran en stock</h1>
<h2>Ingrese el porcentaje de zanahorias podridas</h2>
<input type="number" bind:value={x} on:input={updateImages}>
<div class="container">
  <div class="grid">
      {#each images as image}
        <img src={image} alt="Imagen">
      {/each}
  </div>
</div>
<!-- Estilos CSS -->
<style> 

.container {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    height: 100vh; /* El contenedor ocupa el 100% del viewport en altura */
}
.grid {
  display: grid;
  grid-template-columns: repeat(10, 1fr);
  grid-gap: 0.1px;
  grid-auto-rows: minmax(1, auto);
  max-width: 75%;
  width: 100%;
  max-height: 100vh;
  margin: 0 auto;
}
img{
    height: 75px;
    width: 75px;
}
</style>
