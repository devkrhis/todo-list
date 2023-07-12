<template>
    <div class="boxTasks">
        <td>
            item 1
        </td>
        <td>item 2</td>

        <div class="ClearAll">
            <button type="button"> Clear All </button>
        </div>
    </div>
</template>

<script>
export default {

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