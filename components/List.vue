<template>
  <ul  class="item">
      <li v-for="list,index in lists" :key="index">
        <input type="checkbox" class="checkbox" v-model="list.done">
          <!-- <span :class=" { done : list.done }">{{list.title}}</span> -->
          <span  :class="{done : list.done }"> {{list.title}}</span>
        <button class="delete-item" @click="deleteItem(index)">X</button>
      </li>
    </ul>
</template>

<script>
export default {
  name: 'List',
  props : ['lists']
}
</script>

<style>

</style>
