<template>
   <div class="Titulo">
       {{titulo}}

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
}

</script>


<style scoped>
.Titulo{
    background-color: #999;
    padding:10px;
}
</style>