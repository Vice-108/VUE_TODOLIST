<script>
export default {
  data() {
    return {
      goals: [],
      Value: ""
    }
  },
  methods: {
    addItem() {
      this.goals.push(this.Value);
      this.Value = "";
    },
    delItem(index) {
      this.goals.splice(index, 1);
    }
  }
}
</script>



<template>
  <span class="mainContainer">
  <h1 style="color:cyan">TO-DO LIST IN VUE</h1>
  <span class="inputs">
    <input type="text" id="goal" v-model="Value">
    <button class="addBtn" @click="addItem">
      ADD
    </button>
  </span>  
  <div v-if="goals.length!=0" class="todocontainer">
    <ul class="todoitems">
      <li class="item" v-for="(goal, index) in goals" :key="index">
        {{ goal }}
        <button class="delBtn" @click="delItem(index)">DELETE</button>
      </li>
    </ul>
  </div>
</span>
</template>

<style scoped>
.item{
  color: rgb(74, 66, 66);
  padding: 5px;
  border-radius: 5px;
  border: 1px solid black;
  display: flex;
  gap:1em;
  align-items: center;
  justify-content: space-between;
}
.todocontainer{
  background-color: azure;
  display: flex;
  padding: 1em;
  border-radius: 5px;
}
.todoitems{
  list-style: none;
  padding: 5px;;
  display: flex;
  flex-direction:column;
  gap:10px;
  background-color: white;
}
.mainContainer{
  position: relative;
  top:2em;
  border-radius: 15px;
  padding: 15px;
  display: flex;
  align-items: center;
  flex-direction: column;
  gap:25px;
}
input{
  border-radius: 5px;
}
button{
  padding: 5px;
  border-radius: 5px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
.addBtn{
  background-color: aqua;
}
.delBtn{
  font-size: 10px;
  background-color: rgb(255, 234, 0);
}
.inputs{
  display: flex;
  gap:10px;
}
</style>