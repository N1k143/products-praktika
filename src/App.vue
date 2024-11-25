<template>
<div class="container">
  <div class="row">
    <div class="col">
      <h1 class="text-center mt-4">Учёт товаров</h1>
      <form>
        <div class="mb-3">
  <label for="name" class="form-label">Название</label>
  <input type="text" class="form-control" id="name">
      </div>
      <div class="mb-3">
  <label for="date" class="form-label">Дата</label>
  <input type="date" class="form-control" id="date">
      </div>
      <div class="mb-3">
  <label for="count" class="form-label">Колличество</label>
  <input type="number" class="form-control" id="count">
      </div>
      <div class="mb-3">
  <label for="price" class="form-label">Цена</label>
  <input type="number" class="form-control" id="price" min="1">
      </div>
      <div class="text-center mb-3">
        <button type="button" class="btn btn-outline-success">Добавить</button>
      </div>
      </form>
    </div>
  </div>

  <div class="row row-cols-1 row-cols-md-3 g-3">
  <div class="col">
    <div class="card h-100">
      <div class="card-body">
        <h5 class="card-title">iPhone</h5>
        <p class="card-text">25.11.2024</p>
        <p class="card-text">$150</p>
        <p class="card-text">x10</p>
      </div>
      <div class="card-footer text-end">
        <button class="btn btn-outline-danger">Удалить</button>
      </div>
    </div>
  </div>
</div>
<div class="row my-4">
  <div class="col">
    <h3 class="text-end">Общая сумма: $4500</h3>
  </div>
</div>
</div>
</template>

<script setup>


</script>

<style>

</style>