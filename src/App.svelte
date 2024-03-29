<!-- Script JS -->
<script>
    var x = 0;
    var images = []

    function updateImages(){
        if(x>100 || x<-100){ // este if lo agregue porque si no te mete tantas imagenes como quieras
            x=100 // esto limita el numero de imagenes a 10
        }
        images = []
        
        for(let i =0;i<Math.abs(Math.round(x/10));i++ ){
            images.push("./images/podrida1.png")
        }
        for(let i=0;i<10-Math.abs(Math.round(x/10));i++){
            images.push("./images/zanahoria.webp")
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
</script>

<!-- Estructura contenido HTML -->
<!-- cantidad de tiempo de vida de la zanahoria o x% zanahorias podridas doenfjwebfjbweflkdflsdn -->
<div class="header">
<h1>Zanahorias podridas</h1>
<h2>Ingrese el porcentaje de zanahorias podridas en stock:</h2>
<input type="number" bind:value={x} on:input={updateImages}>
</div>
<div class="container">
  <div class="grid">
      {#each images as image}
        <img src={image} alt="Imagen">
      {/each}
  </div>
</div>
<!-- Estilos CSS -->
<style> 

input{
    padding-top: 0px;
    border-radius: 5px;
    border: 1px solid #ccc; 
    font-size: 16px;
    padding: 10px;
    width: 100px;
    text-align: center;
    margin-bottom: 20px;
    margin-top: 20px;
    background-color: #f0f0f0;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
}
.header{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 30px   20px ;
    width: 1000px;
    margin:auto;
    background-color: aqua;
    border-radius: 50px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    margin-top: 20px;
    margin-bottom: 20px;
}
.container {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    height: 60vh; /* El contenedor ocupa el 100% del viewport en altura */
    width: 100%; /* El contenedor ocupa el 100% del viewport en anchura */
    margin: 0 auto; /* Centramos el contenedor */
    padding: 10px; /* Añadimos un padding para separar el contenido del borde */
    box-sizing: border-box; /* Hacemos que el padding no afecte al tamaño final del contenedor */
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    margin-top: 20px;
    margin-bottom: 20px;

}
.grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-gap: 0.01px;
    grid-auto-rows: minmax(2, auto);
    max-height: 90vh;
    overflow: auto;
    padding: 10px;  
    border-radius: 10px;
    background-color: #f48609;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);

}
img{
    height: 100px;
    width: 100px;;
}
h2{
    padding-bottom: 50px;
    text-align: center; }
h1{
    text-align: center;
}
</style>
