<template>
    <div class="boxTasks">
        <p v-for="itens in tasks" :key="itens.id"> 
            {{ itens }} 
        
        </p>
        <div class="ClearAll">
            <button type="button"> Clear All </button>
        </div>
    </div>
</template>

<script>
export default {
    props:['tasks']
}
</script>

<style scoped>

.boxTasks{
    border: 1px solid black;
    margin-top: 1%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.ClearAll {
    border: 1px solid black;
    background-color: blueviolet;
    color: white;
    padding-top: 5px;

}

</style>