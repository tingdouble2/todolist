<template>
<div class="list-item">
   <ul  class="item">
      <li v-for="list,index in lists" :key="index">
        <input type="checkbox" class="checkbox" v-model="list.done">
          <span  :class="{done : list.done }"> {{list.title}}</span>
        <button class="delete-item" @click="$emit('OnRemove' ,index)">X</button>
      </li>
    </ul>
</div>

</template>

<script>
export default {
  name: 'List',
  props : ['lists']
}
</script>

<style>

</style>
