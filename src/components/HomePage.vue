<template>
    <v-app class="boxSize">
        <ItemAdder/>
        <ItemsPage/>
    </v-app>
</template>

<script>
import ItemsPage from './ItemsPage.vue';
import ItemAdder from './ItemAdder.vue';

export default {
    components: {
        ItemsPage,
        ItemAdder

    }

}
</script>

<style scoped>

.boxSize {
    border: 3px solid black;
    width: 100%;
    height: 50%;
}

</style>