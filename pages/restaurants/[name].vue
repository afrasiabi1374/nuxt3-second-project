<script setup lang="ts">
    import {} from "#app"
    import restaurants from "@/data.json"
    const route = useRoute()
    const name = route.params.name

    const restaurant = restaurants.find(r => r.name === name)
</script>

<template>
    <div>
        {{ restaurant }}
    </div>
</template>