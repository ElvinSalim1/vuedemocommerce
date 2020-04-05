<template>
  <div class="row mt-5" v-if="product">
      <div class="col-4">
          <img :src="product.image" class="w-100" />
      </div>
      <div class="col-8">
          <h1>{{ product.name }}</h1>
          <h3>${{ product.price }}</h3>
          <p class="mt-4">{{ product.description }}</p>
      </div>
  </div>
</template>

<script>
export default {
    props: ["id"],

    computed: {
        product() {
            return this.$store.state.product;
        }
    },

    mounted() {
        this.$store.dispatch('getProduct', this.id)
    }
}
</script>

<style>

</style>