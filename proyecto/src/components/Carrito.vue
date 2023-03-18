import { useStore } from 'vuex';
<template>
  <div class="my-5">
          <h4>Carrito de compras</h4>
          <table class="table">
            <thead>
              <tr>
                <th scope="col">#</th>
                <th scope="col">Item</th>
                <th scope="col">Cantidad</th>
                <th scope="col">Acción</th>
                <th scope="col">Total</th>
              </tr>
            </thead>
            <tbody id="items">
              {{ item }}
              <Item v-for="item in items" :key="item.id"
              :item="item" />
            </tbody>
            <tfoot>
              <tr id="footer">
                <th scope="row" colspan="5">Carrito vacío - comience a comprar!</th>
              </tr>
            </tfoot>
          </table>
          <h4>Cards</h4>
          <div class="row" id="cards"></div>
        </div>
</template>

<script>
import { Computed } from 'vuex'
import {useStore} from 'vuex'
import Item from './Item.vue'

export default {
  components: {Item},

  setup() {
    const store = useStore()
    const items = computed(() => store.state.carrito)

    return {items}
  } 
}
</script>

<style>

</style>