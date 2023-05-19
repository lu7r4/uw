<template>
    <div class="ex_component">
      <p>{{ message }}</p>
    </div>
  </template>

<script>
export default {
  name: 'ExComponent',
  props: {
    message: {
      type: String,
      default: 'Это компонент-заглушка для перехода на другие страницы'
    }
  }
}
</script>

<style scoped>
.ex_component {
  width: 300px;
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.5rem;
  color: #555;
}
</style>