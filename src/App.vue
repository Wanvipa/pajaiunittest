<template>
  <div id="app">
    <menus :foods="foods" :deletemenu="deletemenu" :edit-menu="editMenu"></menus>
    <add :add="add" >เพิ่ม</add>
  </div>
</template>

<script>
import menus from './components/menus'
import add from './components/add'

export default {
  name: 'app',
  data () {
    return {
      foods: [{
        id: '1',
        name: 'ต้มยำกุ้ง',
        price: '30 บาท'
      }]
    }
  },
  components: {
    menus,
    add
  },
  methods: {
    add (name, price) {
      var data = {
        id: Date.now(),
        name: name,
        price: price
      }
      this.foods.push(data)
    },
    deletemenu (id) {
      var index = this.foods.findIndex(food => food.id === id)
      this.foods.splice(index, 1)
    },
    editMenu (id, name, price) {
      var index = this.foods.findIndex(food => food.id === id)
      this.foods[index].name = name
      this.foods[index].price = price
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
