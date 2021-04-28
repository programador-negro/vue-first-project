<template>
     <div class="componente2">

        <h1 id="titleComponente2">Este es mi componente #2</h1>

        <!-- Codigo embebido de variables o paso de variables por HTML -->
        <!-- No es necesario llamar al metodo data() -->
        <p> {{usuario.nombre}} / {{usuario.cargo}} / {{usuario.Lenguajes}}</p>

        <div id="code"> <b>Esto es un cuardo de codigo de prueba.</b>
            <div class="code">
                <div class="comment">//hello worl in JavaScript</div><br>
                if (sad == true){ <br>
                    console.log(<b class="string">"be happy"</b>)<br>
                }
            </div>
        </div>
        <hr>
        <!-- CONCCATENACION Y OPERACIONES BASICAS -->
        <div class="font-green">CONCCATENACION Y OPERACIONES BASICAS </div> <br>

        <!-- OPERACIONES -->
        <p> 5 + 6 = {{ 5 + 6}}</p>
        <p> 5 - 6 = {{ 5 - 6}}</p>
        <p> 5 * 6 = {{ 5 * 6}}</p>
        <p> 5 / 6 = {{ 5 / 6}}</p><br>

        <!-- CONCATENACION -->
        <b>Trabajador: </b>{{ usuario.nombre+" : "+usuario.cargo.toString().toUpperCase() }}

        <!-- NOTA: Se recomienda no realizar operaciones complejas o modificar los datos en el codigo HTML,
                evitar en lo posible esta mala practica -->
        <hr>
        <!-- TEXTO EN FORMATO HTML -->
        <div class="font-green">TEXTO EN FORMATO HTML </div><br>
        <div v-html="usuario.myTag"> </div>
        <!--               |          -->
        <!--     el mismo parametro de Vue se encarga de rellenar o poblar la etiqueta con la informacion pasada -->
        <hr>


        <!-- MOSTRAR UN ARREGLO, ARRAY O LISTA -->
        <div class="font-green">MOSTRAR UN ARREGLO, ARRAY O LISTA </div> <br>
        <p>
           Unico elemto por indice: {{ usuario.colores[0] }}
        </p>

        <!-- ITERACION DE LISTAS O ARREGLOS -->
        <div class="font-green"> ITERACION DE LISTAS O ARREGLOS </div><br>
        <div class="iteracion">
            <ul>
                <li v-for="color in usuario.colores" :key="usuario.colores.indexOf(color)" > {{ color }} </li>
                <!-- Nota: en :key se define el identificador unico el cual va a identificar a cada elemento -->

            </ul>
        </div>
        <hr>

        <!-- ITERACION DE OBJETOS -->
        <div class="font-green"> ITERACION DE OBJETOS</div> <br>
        <div v-for="letra in usuario.letras" :key="usuario.letras.indexOf(letra)">
           Mayucula: {{letra.mayus}} <br>
           Minuscula: {{ letra.min }}
        </div>
        <hr>
        <!-- ITERACIONES SIN OBJETOS NI LISTAS -->
        <div class="font-green"> ITERACIONES SIN OBJETOS NI LISTAS</div> 
        <div v-for="x in 5" :key="x">
            hola mundo. <button > Boton {{x}}</button>
        </div>
        <hr>

        <!-- CONDICINALES -->
        <div class="font-green"> CONDICINALES</div>
        <div>
            <button>Boton {{mostrarBoton}}</button>
            <div v-if="mostrarBoton == 'intermedio'">Sin Estado</div>
            <div v-else-if="mostrarBoton">boton activo</div>
            <div v-else> boton desactivado</div>
        </div>
    </div>
</template>

<script>
export default {
    name:'componente2', //nombre del componente
    data(){ // funcionde retorno de variables
        return{
            usuario: {
                nombre: "Jack Daniels",
                cargo: "Analista de aplicaciones Jr.",
                Lenguajes: "Python, JS, C#, SQL, etc.",
                myTag: "<h2> <b> esta es una etiqueta de JavaScript </B> </h2>",
                colores: [ "rojo", "azul", "amarillo"],
                letras:[
                    {min: "a", mayus:"A"},
                    {min: "b", mayus:"B"},
                    {min: "c", mayus:"C"},
                    {min: "d", mayus:"D"}
                ]
            },
            mostrarBoton: 'intermedio'
        }
    }
}
</script>

<style>
.comment {
    color: lightgrey;
}
.string {
    color: yellow;
}
#titleComponente2 {
    color: green;
    font-family: 'Courier New', Courier, monospace;
}
#code {
    margin-left: 25%;
    margin-right: 25%;
}
#code .code{
    border: 2px solid red;
    padding: 10px;
    background-color: black;
    color: white;
    font-family: 'Courier New', Courier, monospace;
    text-align: left;
  
}
.iteracion ul li {
    list-style: circle;
}


</style>