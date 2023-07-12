<template>
    <div class="Tasks">
        <label>  
            <input type="text" placeholder="Add Tasks" v-model="name" value="name" @keyup.enter="gettingTasks(name)">
            <button type="button" class="tableInput tableSize"> + </button>
        </label>
    </div>
</template>

<script>
export default {
    data(){
        return {
            tasks: {
                name: '',
                itemValue: false
            }
        }
    },
    methods: {
        gettingTasks(value){
            console.log("Enter foi pressionado", value)
        }

    }

}
</script>

<style scoped>

.tableInput{
    border: 1px solid black;
    margin-top: 10%;
    margin-left: 7px;
}

.tableSize{
    width: 70px;
}

.Tasks {
    display: flex;
    align-items: center;
    justify-content: center;
}

</style>