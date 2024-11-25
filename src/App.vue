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
  <input type="number" class="form-control" id="price">
      </div>
      <div class="text-center mb-3">
        <button type="button" class="btn btn-outline-success">Добавить</button>
      </div>
      </form>
    </div>
  </div>
</div>
</template>

<script setup>


</script>

<style>

</style>