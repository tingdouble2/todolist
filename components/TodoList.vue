<template>
  <div class="todolist">
    <input v-model="newitem" type="text" class="input-item">
    <button class="btn-add" @click="addNewItem">ADD</button>
    <List :lists="lists"/>
    <!-- <ul  class="item">
      <li v-for="list,index in lists" :key="index">
        <input type="checkbox" class="checkbox" v-model="list.done"> -->
          <!-- <span :class=" { done : list.done }">{{list.title}}</span> -->
          <!-- <span  :class="{done : list.done }"> {{list.title}}</span>
        <button class="delete-item" @click="deleteItem(index)">X</button>
      </li>
    </ul> -->
     <!-- <Footer :title="title" /> -->
  </div>
</template>

<script>
export default {
name: 'TodoList',
  data () {
    return {
      newitem: '',
      lists: [],
      done:false,
      // title: 'FOOTER'
    }
  },
  methods : {
    addNewItem() {
      this.lists.push({
        title : this.newitem
      })
      this.newitem =''
    },
    deleteItem(index) {
      // this.$delete(this.lists,index)
      // const index = this.lists.indexOf(list)
      this.lists.splice(index ,1)
      console.log(index)
    },
    checkDone() {
      let total = document.querySelectorAll('input[type="checkbox"]:checked').length
      // const checked = document.getElementsByClassName('checkbox')
      if (total > 0) {

      }
    }
  }
}
</script>

<style lang="scss">

.todolist {
  max-width: 700px;
  margin:10%  auto;
  padding: 10px;
  background-color: rgba(255, 255, 255, .2);
  box-shadow: 0 0 20px rgba(0, 0, 0, .1);

    .input-item {
      width: 280px;
      height: 40px;
      padding: 10px;
      border-radius: 5px;
      border: 1px solid #d3d3d3;
      margin-left: 50px;
    }


    .btn-add {
      width: 80px;
      height: 25px;
      background: none;
      border: none;
      margin: 10px;
      font-weight: 585;

        &:hover {
          color :rgba(34, 33, 33, 0.5);
          cursor: pointer;
        }
    }

    .btn-delete {
      width: 80px;
      height: 25px;
      background: none;
      border: none;
      margin: 10px;
      font-weight: 585;
      color :rgba(177, 10, 10, 0.5);
        &:hover {
          cursor: pointer;
        }
    }

    li {
        font-size: 18px;
        padding: 10px;
        list-style: none;
        position: relative;
      }

    .delete-item {
      height: 25px;
      background: none;
      border: none;
      margin: 10px;
      font-weight: 585;
      position: absolute;
      right: 0;
      bottom: 0;
      color :rgba(143, 6, 6, 0.5);
        &:hover {
          cursor: pointer;
        }
    }

    .done  {
    text-decoration: line-through;
  }
}

</style>
