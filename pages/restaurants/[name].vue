<script setup lang="ts">
    import {} from "#app"
    import restaurants from "@/data.json"
    const route = useRoute()
    const name = route.params.name

    const restaurant = restaurants.find(r => r.name === name)
</script>

<template>
    <div>
        <NuxtLayout name="custom" v-if="restaurant">
            <p >
                {{ restaurant }}
            </p>
        </NuxtLayout>
        <div v-else>
            <img
                src="https://www.iconpacks.net/icons/2/free-sad-face-icon-2691-thumb.png"
                alt="error-image"
            />
            <nuxt-link to="/">go back!</nuxt-link>
        </div>
    </div>
</template>
<style scoped>
  img {
    width:10rem
  }
</style>