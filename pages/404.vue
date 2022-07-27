<template>
  <div class="container text-center">
    <nuxt-layout name="error">
      <template #header>
        <h1>
          page not found___404
          <h2>ارور سفارشی</h2>
        </h1>
      </template>
      <template #redirect>
        <nuxt-link class="btn btn-warning" to="/">go back</nuxt-link>
      </template>
    </nuxt-layout>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>

</style>