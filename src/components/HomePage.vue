<template>
    <v-app class="boxSize">
        <ItemAdder/>
    </v-app>
</template>

<script>
import ItemAdder from './ItemAdder.vue';

export default {
    components: {
        ItemAdder
    },
    data(){
        return {
        }
    },

}
</script>

<style scoped>

.boxSize {
    border: 3px solid black;
    width: 100%;
    height: 50%;
}

</style>