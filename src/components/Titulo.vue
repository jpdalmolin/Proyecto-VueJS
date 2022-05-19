<template>
   <div class="Titulo">

       <h1>Tech Store Vue</h1>
       <h2>
           <slot><!-- aca va el titulo dentro de titulo en titulo --></slot>
       </h2>
        {{titulo}} {{numeroA}}
   </div>
</template>

<script>

export default{
    props:{
        titulo:{
            type: String,
            required: true,
        },
    },
    data(){
        return{
            numeroA: 0
        }
    },
    mounted() {
        this.NumeroA = 1;
    },
    computed:{
        NumeroA:{
            get() {
                return this.numeroA;
            },
            set(nuevoValor) {
                this.numeroA = nuevoValor;
            }
        }
    },
    watch:{

    }
}

</script>


<style scoped>
h1 {
    font-size:3 em;
    padding:10px;margin:0;
}
.Titulo{
    background-color: #999;
    padding:10px;
    margin-bottom:10px;
}
</style>
