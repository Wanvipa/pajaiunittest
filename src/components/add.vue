<template lang="html">
<div class="">
  name : <input v-model="name">
  Price : <input v-model="price">
  <button  @click="addmenu"></button>

</div>
</template>

<script>
export default {
  props: ['add'],
  data () {
    return {
      name: '',
      price: ''
    }
  },
  computed: {},
  mounted () {},
  methods: {
    addmenu () {
      this.add(this.name, this.price)
      this.name = ''
      this.price = ''
    }
  },
  components: {}
}
</script>

<style lang="css">
</style>
