<template lang="html">
  <div class="">
    <div v-show="!edit">
      {{food.name}}
      {{food.price}}
      <button @click="openEdit"> แก้ไข</button>
    </div>
    <div v-show="edit">
      <input v-model="name">
      <input v-model="price">
      <button @click="editConfirm">ยืนยัน</button>
    </div>

    <button @click="deletemenu(food.id)">ลบ</button>


  </div>
</template>

<script>
export default {
  props: ['food', 'deletemenu', 'editMenu'],
  data () {
    return {
      name: '',
      price: '',
      edit: false
    }
  },
  computed: {},
  mounted () {},
  methods: {
    openEdit () {
      this.edit = true
      this.name = this.food.name
      this.price = this.food.price
    },
    editConfirm () {
      this.editMenu(this.food.id, this.name, this.price)
      this.edit = false
    }
  },
  components: {}
}
</script>

<style lang="css">
</style>
