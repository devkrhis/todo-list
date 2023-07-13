<template>
    <div class="Tasks">
        <div>
            <label>  
                <input class="border" type="text" placeholder="Add Tasks" v-model="newItem" @keyup.enter="gettingTasks(newItem)">
                <button type="button" class="tableInput tableSize" @click="gettingTasks(newItem)"> + </button>
            </label>
            <div>
                <p class="borderParagraf" v-for="(item, index) in tasks" :key="item.id" 
                :class="{colorGreen: item.itemValue}" @click="changeColor(index)">
                    {{ item.name }}
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            newItem: '',
            tasks: [
                {
                    
                }   
            ],
            styleColor: {
                backgroundColor: 'green'
            }
        }
    },
    methods: {
        gettingTasks(value){
            this.tasks.unshift({
                name: value,
                itemValue: false
            })
            this.newItem = ''
        console.log(this.tasks)
        },
        changeColor(value){
            this.tasks.findIndex( => {
                
            })
            console.log("click do mouse",value)
        }
    }

}
</script>

<style scoped>

.tableInput{
    border: 1px solid black;
    margin-top: 10%;
    margin-left: 7px;
    margin-bottom: 10px;
}

.tableSize{
    width: 70px;
}

.Tasks {
    display: flex;
    align-items: center;
    justify-content: center;
}

.border{
    border: 2px solid black;
}

.borderParagraf{
    background-color: red;
    border: 2px solid black;
}

.colorGreen{
    background-color: green;
}

</style>