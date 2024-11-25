<template>
<div class="container">
  <div class="row">
    <div class="col">
      <h1 class="text-center mt-4">Учёт товаров</h1>
      <form>
        <div class="mb-3">
  <label for="name" class="form-label">Название</label>
  <input type="text" v-model="name" class="form-control" :class="{'is-invalid' : !name}" id="name">
  <div class="invalid-feedback">
      Пожалуйста заполните назавние
    </div>

      </div>
      <div class="mb-3">
  <label for="date" class="form-label">Дата</label>
  <input type="date" v-model="date" class="form-control" :class="{'is-invalid' : !date}" id="date">
  <div class="invalid-feedback">
      Пожалуйста заполните дату
    </div>
      </div>
      <div class="mb-3">
  <label for="count" class="form-label">Колличество</label>
  <input type="number" v-model="count" class="form-control" :class="{'is-invalid' : !count}" id="count">
  <div class="invalid-feedback">
      Пожалуйста заполните колличество
    </div>
      </div>
      <div class="mb-3">
  <label for="price" class="form-label">Цена</label>
  <input type="number" v-model="price" class="form-control" :class="{'is-invalid' : !price}" id="price" min="1">
  <div class="invalid-feedback">
      Пожалуйста заполните цену
    </div>
      </div>
      <div class="text-center mb-3">
        <button type="button" @click="addProduct" class="btn btn-outline-success">Добавить</button>
      </div>
      </form>
    </div>
  </div>

  <div class="row row-cols-1 row-cols-md-3 g-3">
  <div class="col" v-for="product in products" :key="product.id">
    <div class="card h-100">
      <div class="card-body">
        <h5 class="card-title">{{ product.name }}</h5>
        <p class="card-text">{{ product.date }}</p>
        <p class="card-text">${{ product.price }}</p>
        <p class="card-text">x{{ product.count }}</p>
      </div>
      <div class="card-footer text-end">
        <button @click="removeProduct(product.id)" class="btn btn-outline-danger">Удалить</button>
      </div>
    </div>
  </div>
</div>
<div class="row my-4">
  <div class="col">
    <h3 class="text-end">Общая сумма: ${{ totalSum }}</h3>
  </div>
</div>
</div>
</template>

<script setup>
import { ref, computed } from 'vue';


const products = ref([
  {
    id: 1,
    name: 'iPhone 16',
    date: '25.11.2024',
    count: 10,
    price: 1500,
  },
  {
    id: 2,
    name: 'Samsung s23 PLUS',
    date: '12.07.2024',
    count: 15,
    price: 1000,
  },
  {
    id: 3,
    name: 'Xiaomi Mi 14',
    date: '12.05.2024',
    count: 20,
    price: 700,
  },
  {
    id: 4,
    name: 'Huawei p40',
    date: '27.12.2024',
    count: 10,
    price: 1350,
  }

]);
const name = ref('');
const date = ref('');
const count = ref(1);
const price = ref(0);

const addProduct = () => {
  if (name.value && date.value && count.value && price.value) {
    products.value.push(
      {
    id: Date.now(),
    name: name.value,
    date: date.value,
    count: count.value,
    price: price.value,
  }
    );
  }
}

const removeProduct = (id) => {
  products.value = products.value.filter((product) => product.id != id);
}

const totalSum = computed(() => {
  return products.value.reduce((sum, product) => sum + (product.price * product.count), 0)
});
</script>

<style>

</style>