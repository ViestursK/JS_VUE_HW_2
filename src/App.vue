<template>
    <HeaderComponent></HeaderComponent>
    <div id="body">
        <NavigationComponent></NavigationComponent>
        <router-view></router-view>
    </div>
</template>

<script>
import { store } from './store';

export default {

    data() {
        return {
            store
        }
    }
}
</script>

<style>
body {
    margin: 0;
    height: 100vh;
    width: 100vw;
}
</style>