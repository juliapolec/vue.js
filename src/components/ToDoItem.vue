<template>
    <div class="item" v-bind:class="{completed: item.completed}">
        <h2>{{ item.title }}</h2>
        <button class="done" v-if="!item.completed" @click="doneItem">done</button>
    </div>
</template>
<script>
export default {
    props:['item'],
    methods: {
        doneItem(){
            this.$emit('itemDone', this.item.id)
        }
    }
}
</script>

<style>
.item {
    border: 1px solid #cdcdcd;
    margin: 8px;
    padding: 5px;
    font-family: sans-serif;
}

.done {
    background-color: #C1E1C1;
    color: 	#056608;
    font-size: 20px;
    font-family: serif;
    border-radius: 12px;
    border: none;
}
</style>
