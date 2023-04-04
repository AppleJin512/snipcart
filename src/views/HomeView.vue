<script>
  import Banner from "../sections/home/Banner.vue"
  export default {
    components: {
      Banner
    },
    data() {
      return {
        products: [
          {
            name: "Glade Aromatherapy Candle Moment of Zen 260g",
            id: "1assdfaserw432445435435232346516ds",
            price: 3.5,
            description: "lorem ip sum. lorem ip sum. lorem ip sum. lorem ip sum. lorem ip sum.",
            image: "http://localhost:5173/src/assets/product-image1.jpg",
            quantity: 45,
            max_quantity: 100,
            min_quantity: 0,
            stackable: "auto",
            quantity_step: 1,
            categories: ["aaa", "bbb", "ccc"],
            metadata: {
              key1: 'value1',
              key2: 'value2',
            },
            taxable: true,
            taxes: ["tax1", "tax2"],
            hax_taxes_included: true
          },
          {
            name: "Elastoplast Water Resistant Plasters 20 pack",
            id: "1assdafassdfaserw4324423413124346516ds",
            price: 3.5,
            description: "lorem ip sum. lorem ip sum. lorem ip sum. lorem ip sum. lorem ip sum.",
            image: "http://localhost:5173/src/assets/product-image2.jpg",
            quantity: 45,
            max_quantity: 100,
            min_quantity: 0,
            stackable: "auto",
            quantity_step: 1,
            categories: ["aaa", "bbb", "ccc"],
            metadata: {
              key1: 'value1',
              key2: 'value2',
            },
            taxable: true,
            taxes: ["tax1", "tax2"],
            hax_taxes_included: true
          }
        ]
      }
    },
    methods: {
    }
  }
</script>

<template>
  <div class="flex flex-col justify-center items-center pb-10">
    <div class="bg-black h-16 flex items-center justify-center w-full">
        <span class="text-white text-xl">Snipcart-powered demo store.</span>
    </div>
    <button
      class="bg-blue-950 py-3 px-5 text-white text-lg rounded-xl border-2 border-black-300 mt-3 tracking-widest snipcart-checkout"
      @click="showBucket"
    >
      CHECKOUT
    </button>
    <div class="mt-5">
      <template v-for="product in products">
        <div class="flex flex-row">
          <div class="product-info flex flex-col mr-10 mt-10 text-gray-500 max-w-xs">
            <span class="text-2xl font-bold text-black"><code>{{ product.name }}</code></span>
            <span class="text-lg font-bold"><code>{{ product.description }}</code></span>
            <span class="font-bold">Price: <code>{{ product.price }}</code></span>
            <span class="font-bold">Quantity: <code>{{ product.quantity }}</code></span>
            <span class="font-bold">MaxQuantity: <code>{{ product.max_quantity }}</code></span>
            <span class="font-bold">MinQuantity: <code>{{ product.min_quantity }}</code></span>
            <span class="font-bold">Stackable: <code>{{ product.stackable }}</code></span>
            <span class="font-bold">QuantityStep <code>{{ product.quantity_step }}</code></span>
            <span class="font-bold">Categories: <code>{{ product.categories.join(" ") }}</code></span>
            <span class="font-bold">Taxable: <code>{{ product.taxable? "YES" : "NO" }}</code></span>
            <span class="font-bold">Taxes: <code>{{ product.taxes.join(" ")}}</code></span>
            <span class="font-bold">Has Taxes Included: <code>{{ product.hax_taxes_included ? "YES" : "NO"}}</code></span>
            <button
              class="snipcart-add-item bg-blue-950 py-3 px-5 text-white text-lg rounded-xl border-2 border-black-300 mt-3 tracking-widest snipcart-checkout"
              :data-item-id="product.id"
              :data-item-name="product.name"
              :data-item-image="product.image"
              :data-item-price="product.price"
              :data-item-stackable="product.stackable"
              :data-item-description="product.description"
              :data-item-has-taxes-included="product.hax_taxes_included"
              :data-item-taxes="product.taxes"
            >Add to cart</button>
          </div>
          <div class="flex items-center ml-10">
            <img :src="product.image" alt="product-image" class="w-96 h-96"/>
          </div>
        </div>
      </template>
    </div>
  </div>
</template>

<style scoped>
</style>
