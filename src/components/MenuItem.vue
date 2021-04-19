<template>
  <div class="menu-item">
    <img
        class="menu-item__image"
        :src="item.image.source"
        :alt="item.image.alt"
    />
    <div>
      <h3>{{ item.name }}</h3>
      <p v-if="item.inStock">En stock</p>
      <p v-else>En rupture de stock</p>
      <div>
        <label for="add-item-quantity"
        >Quantité : {{ item.quantity }}</label
        >
        <input
            v-model.number="item.quantity"
            id="add-item-quantity"
            type="number"
        />
        <button @click="addToShoppingCart(item.quantity)">
          Ajouter au panier d'achat
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MenuItem",
  props: ["item", "addToShoppingCart"]
}
</script>

<style scoped>

</style>
