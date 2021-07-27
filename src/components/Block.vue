<template>
    <div class="block">
        Click Here{{delay}}
    </div>
</template>

<script>
export default {
      props:['delay']
}
</script>

<style scoped>
    .block{
        width:200px;
        height: 200px;

        background-color: red;
        color:#fff;

        margin:100px auto;
    }
</style>