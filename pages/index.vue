<template>
  <div>
      {{ name }} <br>
  <nuxt-link to="/fruits">Фрукты</nuxt-link> <br>
    <div v-for="(fruit, key) in fruits" :key="key">
      <h2>{{ fruit.title }}</h2>
      <p>{{ fruit.price }}</p>
      <button @click="addToCart(fruit)">Добавить</button>
    </div>
    <div>
      Корзина: {{ basket }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return {
      name: 'Tamik',
      fruits: [
        {
          title: 'Яблоко',
          price: 232,
        },
                {
          title: 'Груша',
          price: 232,
        },
                {
          title: 'Киви',
          price: 232,
        },
      ],
      basket: []
    }
  },
  methods: {
    addToCart(obj) {
      this.basket.push(obj)
      console.log('added')
    }
  }
}
</script>
