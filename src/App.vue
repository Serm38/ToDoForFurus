<script>
  export default{
    data(){
      return{
        cases: [],
        case: ''
      }
    },
    methods:{
      //Метод для добавления элемента case в массив cases
      addCase(){
        //Проверка на пустоту
        if (this.case != '') this.cases.push( this.case )
        //Очистка case
        this.case = ''
      },
      //Метод для удаления элемента case из массива cases
      delCase(i){
        this.cases.splice(i, 1)
      }
    }
  }
</script>

<template>
  <div>Список дел</div>
  <input type="text" v-model="this.case">
  <button @click="addCase">Добавить</button>
  <hr>

  <ul>
    <li v-for="(item, i) in cases">
      <div>{{ item }}</div>
      <button @click="delCase(i)">Удалить</button>
    </li>
  </ul>

  <hr>
  <div>Всего дел {{ cases.length }} </div>
</template>

<style>
  ul{
    list-style: none;
    padding: 0;
    margin: 0;
  }
  li{
    width: 245px;
    display: flex;
    justify-content: space-between;
    padding: 10px 0;
  }
</style>