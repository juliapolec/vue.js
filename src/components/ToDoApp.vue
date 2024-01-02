<template>
    <div>
        <div class="title">
            <input type="text" placeholder="todo" v-model="newItem">
            <button class="add" @click="addItem">Add</button>
        </div>
        <ToDoItem v-for="item in items" :key="item.id" :item="item" @itemDone="doneItem" />
    </div>
</template>

<script>
import ToDoItem from "./ToDoItem.vue";

export default {
    components: {ToDoItem},
    data(){
        return{
            newItem: '',
            items:[
                { title: 'doctor appointment', completed: false, id: 1 },
                { title: 'clean the kitchen', completed: false, id: 2 },
                { title: 'vacuum', completed: false, id: 3 },
                { title: 'laundry', completed: false, id: 4 },
                { title: 'haircut', completed: false, id: 5 }
            ]
        }
    },
    methods: {
        addItem(){
            this.items.push({
                title: this.newItem,
                completed: false,
                id: Math.random()
            })
            this.newItem = ''
        },
        doneItem(id){
            const index = this.items.findIndex(el => el.id === id)
            this.items[index].completed = true
        }
    }
}
</script>

<style>
.title {
    margin: 8px;
    padding: 5px;
    font-family: sans-serif;
}
.completed h2 {
    text-decoration: line-through #C1E1C1;
    color: #C1E1C1;
}
.add {
    background-color: #C1E1C1;
    color: 	#056608;
    font-size: 20px;
    font-family: serif;
    border-radius: 12px;
    border: none;
}
</style>

