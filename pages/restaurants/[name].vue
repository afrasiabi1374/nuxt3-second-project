<script setup lang="ts">
    import {} from "#app"
    import restaurants from "@/data.json"

    const route = useRoute()
    const name = route.params.name
    const restaurant = restaurants.find(r => r.name === name)

    // تعریف متا توی اسکریپت
    useHead({
        title: `${name}<= رستوران`,
        viewport: 'width=device-width, initial-scale=1, maximum-scale=1',
        charset: 'utf-8',
        meta: [
            { name: 'description', content: 'My amazing site.' }
        ],
        bodyAttrs: {
            class: 'test'
        }
    })
</script>

<template>
    <div>
        <NuxtLayout name="custom" v-if="restaurant">
            <p >
                {{ restaurant }}
            </p>
        </NuxtLayout>
        <NuxtLayout   name="error" v-else>
            <template #header>
                <h1>
                رستورانی با این اسم وجود ندارد!
                <h2>ارور سفارشی</h2>
                </h1>
            </template>
            <template #redirect>
                <nuxt-link class="btn btn-success" to="/restaurants">go back!</nuxt-link>
            </template>
        </NuxtLayout>
    </div>
</template>
<style scoped>
  img {
    width:10rem
  }
</style>