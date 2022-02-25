<template>
    <div class="top-header d-flex ">
        <img src="../assets/img/logo.png" alt="logo di spotify">
    </div>
</template>

<script>
export default {
    name: 'MyHeader',
}
</script>

<style scoped lang="scss">
    .top-header{
        width: 100%;
        height: 50px;
        background-color: #2b3742;

        img{
            width: 120px;
            margin-left: 10px;
        }
    }
</style>