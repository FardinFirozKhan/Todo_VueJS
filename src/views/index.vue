<template>
    <div class="todo-app">
        <h1>Todo List</h1>
        <div class="add-task">
            <input v-model="newTask" type="text" id="new-task" placeholder="Add a new task">
            <button @click="addTask" id="add-button">Add</button>
        </div>
        <ul id="task-list">
            <li v-for="(task,i) in tasks" :key="i">
                {{task}}
            </li>
        </ul>
    </div>
</template>


<script>

    export default{
        data(){
            return{
                newTask: "",
                tasks:[]
            }
        },
        methods: {
        addTask() {
            if (this.newTask.trim() !== "") {
                this.tasks.push(this.newTask);
                this.newTask = "";
            }
        },
    },
    }

</script>


<style scoped>



body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f0f0f0;
}

.todo-app {
    background-color: #fff;
    max-width: 400px;
    margin: 20px auto;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}

h1 {
    text-align: center;
}

.add-task {
    display: flex;
    margin-bottom: 20px;
}

input[type="text"] {
    flex-grow: 1;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px 0 0 5px;
    font-size: 16px;
    outline: none;
}

button {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 0 5px 5px 0;
    cursor: pointer;
    font-size: 16px;
    outline: none;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #fff;
    margin-bottom: 10px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 18px;
}

li button {
    background-color: #ff3b3b;
    color: #fff;
    border: none;
    padding: 5px 10px;
    border-radius: 5px;
    cursor: pointer;
    font-size: 14px;
}


</style>