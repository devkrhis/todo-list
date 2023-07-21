<template>
    <div class="Tasks">
        <div>
            <label>  
                <input class="border" type="text" placeholder="Add Tasks" v-model="newItem" @keyup.enter="gettingTasks(newItem)">
                <button type="button" class="tableInput tableSize" @click="gettingTasks(newItem)"> + </button>
            </label>
            <div class="alignItens" v-for="(item, index) in tasks" :key="item.id">
                <li class="borderParagraf"
                :class="{colorGreen: item.itemValue}" @click="changeColor(index)">
                    {{ item.name }}
                </li>
                <button type="button" @click="deleteItem(item)"> X </button>
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
            ],
            styleColor: {
                backgroundColor: 'green'
            }
        }
    },
    methods: {
        gettingTasks(value){
            this.tasks.push({
                name: value,
                itemValue: false
            })
            this.newItem = ''
        console.log(this.tasks)
        },
        changeColor(value){
            if(this.tasks[value].itemValue == false){
                this.tasks[value].itemValue = true
                console.log('event0', value)
            } else {
                this.tasks[value].itemValue = false
                console.log('event1', value)
            }
        },
        deleteItem(item){
            const index = this.tasks.indexOf(item)
            if(index > -1){
                this.tasks.splice(index, 1)
            } else {
                alert("Não encontramos o item!")
            }
        }
    },
    watch: {
        tasks: {
            deep: true,
            handler(){
                localStorage.setItem('tasks', JSON.stringify(this.tasks))
            }
        }
    },
    created(){
        const json = localStorage.getItem('tasks')
        // this.tasks = JSON.parse(json) || [] -> pode fazer dessa forma, caso não tenha nada vai ser um array vazio.
        const array = JSON.parse(json)
        // if(Array.isArray(array)){ - Pode fazer essa verificação
        //     this.tasks = array
        // } else {
        //     this.tasks = []
        // }
        // Melhor opção é realizar da seguinte forma:
        this.tasks = Array.isArray(array) ? array : [] // Dessa forma eu faço com o operador ternario se isso 
        // for um array eu retorno um array, caso contrario retorno um array vazio
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
    margin-bottom: 10px;
    margin-right: 5px;
}

.colorGreen{
    background-color: green;
}

.alignItens{
    display: flex;
    align-items: center;
    justify-content: center;
}

</style>