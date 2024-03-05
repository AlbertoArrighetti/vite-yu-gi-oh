<script>
import {store} from '../store.js';

export default {
    name: 'AppPagination',

    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <nav>
        <img src="/public/img/logo.jpg" alt="logo">
    
        <h1>
            Yu-Gi-Oh Api
        </h1>
    </nav>
</template>

<style lang="scss">
nav {
    display: flex;
    
    padding-left: 30px;
    margin-bottom: 40px;

    background-color: white;
    color: black;

    img {
        width: 100px;
    }
    h1 {
        padding: 30px;
        font-weight: 400;
        font-size: 44px;
    }
}
</style>