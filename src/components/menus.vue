<template lang="html">
<div class="">
  <menuf v-for = "food in foods" :food="food" :deletemenu="deletemenu" :edit-menu="editMenu"></menuf>

</div>
</template>

<script>
import menuf from './menu'
export default {
  props: ['foods', 'deletemenu', 'editMenu'],
  data () {
    return {}
  },
  computed: {},
  mounted () {},
  methods: {},
  components: {
    menuf
  }
}
</script>

<style lang="css">
</style>
