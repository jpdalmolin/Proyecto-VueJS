<template>
  <div id="app">


    <Titulo titulo="Tech Store Vue">
           Bienvenido a mi primer entrega final

    </Titulo>
    <NavbarVue/>
     <Carrito :productos="productosEnCarrito"/>
    <img alt="Vue logo" src="./assets/logo.png">
     <HelloWorld :mensaje="mensaje"/>
    <Descripcion/>
    <TestWatcher/>

    <div class="contenedorProductos">
            <ProductoVue
                attr1="attr1"
                attr2="attr2"
                v-bind="$attrs"
                v-for="(item, i) in productos"
                :key="i"
                :id="item.id"
                :titulo="item.titulo"
                :precio="item.precio"
                :nombre-imagen="item.nombreImagen"
                :destacado="item.destacado"
                @agregar-al-carrito="AgregarAlCarrito"
            >
            </ProductoVue>
  </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Titulo from './components/Titulo.vue'
import Descripcion from './components/Descripcion.vue'
import TestWatcherVue from './components/TestWatcher.vue'
import TestWatcher from './components/TestWatcher.vue'
import ProductoVue from './components/Producto.vue'
import Carrito from './components/Carrito.vue'
import NavbarVue from './components/Navbar.vue'
export default {
  name: 'App',
  components: {
    HelloWorld,
    Titulo,
    Descripcion,
    TestWatcher,
    ProductoVue,
    Carrito,
    NavbarVue,
},
  data(){
    return {
      mensaje: "este es un mensaje!",
      productos: [
                {
                    id: 1,
                    titulo: "Notebook HP",
                    precio: 170000,
                    nombreImagen: "notebookHP.png",
                    destacado: false,
                },
                {
                    id: 2,
                    titulo: "Celular Motorola",
                    precio: 53000,
                    nombreImagen: "celular-motorola.png",
                    destacado: false,
                },
                {
                    id: 3,
                    titulo: "Monitor Samsung",
                    precio: 71000,
                    nombreImagen: "monitor-samsung.png",
                    destacado: true,
                },
            ],
            productosEnCarrito: [],
        };
    },
    mounted() {},
    methods: {
        AgregarAlCarrito(id) {
            let result = this.productos.find((prod) => {
                return prod.id == id;
            });
            this.productosEnCarrito.push(result);
            // if (result) {
            //     this.$refs.miCarrito.AgregarProducto(result);
            // }
        },
    },


}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color:#111;
}
.contenedorProductos {
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>
