<template>
  <div>
    {{footer}} {{title}}
  </div>
</template>

<script>
export default {
  props: {
    title : {
      type: String
    }
  },
  data () {
    return {
      footer : 'Copyright'
    }
  }
}
</script>

<style>

</style>
