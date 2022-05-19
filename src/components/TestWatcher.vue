<template>
<div>
{{titulo}}
</div>
</template>

<script>
export default {
    data(){
        return{
            titulo:"hola coders"
        }
    },
    mounted(){
        setTimeout(()=>{
            this.titulo="hola coders uno"

        },3000);
         setTimeout(()=>{
            this.titulo="hola coders dos"

        },5000);
    },
    watch:{
        titulo:function(nuevoVal, viejoValor){
            console.log(`El titulo ha cambiado de "${viejoValor}" a ${nuevoVal}!`);
            }
    },
}
</script>

<style>

</style>
