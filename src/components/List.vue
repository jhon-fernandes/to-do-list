<template>
    
    <div class="container-form">
        <h2> Tarefas </h2>
        
        <div v-for="todo in todos" :key="todo" 
        class="listagem"
        :class="todo.done === true? 'risc' : '' "
        
         @click="todo.done = !todo.done" >
            {{ todo.text }}
        </div>

        <form>
            <input type="text" 
            placeholder="Adicione uma nova tarefa ..." 
            class="input-form" 
            v-model="newTodo.text">   
            <br>

           <input type="button" value="Adicionar"
           class="btn btn-add" @click="add()"> 

           <div v-if="showRemove()">
               
               <input type="button" value="Limpar"
               class="btn btn-remove" @click="removeAll()">
           </div>
        </form>    

        <ul>
            <li> Adicione uma tarefa </li>
            <li> Clique em cima da tarefa para marcar </li>
            <li> Clique em limpar todas </li>
        </ul>
    </div>

</template>

<script>
    export default {
       data(){
           return{
                todos: [],
                newTodo: {
                    done: false
                }
           }
       },

       methods: {
           add(){
               /*
               this.todos.push(this.newTodo);
               this.newTodo = {
                    done: false
                };
                */ 

              if(this.newTodo.text)
              {
                  this.todos.push(this.newTodo);
                    this.newTodo = {
                            done: false
                        };
              }   else 
              {
                  alert("Campo de descrição é obrigatório")
              }
           },

           removeAll(){
               this.todos.splice(this.newTodo)
           },

           showRemove() {
               if( this.todos.length == 0 )
               {
                   return false 
               }   else 
               {
                   return true
               }
           }
       }
    }
</script>

<style scoped>
    .container-form
    {
        max-width: 500px;
        padding-top: 30px;
        padding-bottom: 30px;
        margin: 30px auto; 
        text-align: center;
        border: 1px solid lightgrey;
        background-color: rgb(248, 248, 248);
        font-family: 'Times New Roman', Times, serif;
    }

    .listagem 
    {
        font-weight: 200;
        cursor: pointer;
    }

    .risc 
    {
        text-decoration: line-through;
        color: brown;
        font-weight: 500;
        transition: 0.5s;
    }
    .input-form 
    {
        background-color: transparent; 
        text-align: center;
        width: 50%;
        border-top: none;
        border-left: none;
        border-right: none;
        border-bottom: 1px solid lightgrey;
        height: 20px;
        margin-bottom: 10px;
    }

    .btn
    {
        color: white;
        border: none;
        height: 30px;
        width: 100px;
        border-radius: 10px;
        cursor: pointer;
        transition: 0.5s;
        margin-bottom: 5px;
    }

    .btn-add 
    {
        background-color: blue;
    }

    .btn-remove 
    {
        background-color: red;
    }

    .btn:hover
    {
        border: 1px solid black;
    }

    ul 
    {
        margin-left: -50px;
    }

    ul li 
    {
        color: lightslategrey;
        list-style: none;
    }
</style>