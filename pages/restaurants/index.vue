<script setup>

</script>
<template>
    <div>
        <Html :lang="dynamic > 50 ? 'en-GB' : 'en-US'">
            <Head>
                <Title>پنجاه رستون برتر تو دنیا</Title>
                <Meta
                name="description"
                content="My Page is cool"
                />
                <Link 
                rel="preload" 
                href="https://www.iconpacks.net/icons/2/free-sad-face-icon-2691-thumb.png" 
                as="script"
                />
            </Head>
        </Html>
        <NuxtLayout name="custom">
            <div class="container">
                <RestaurantTable />
            </div>
        </NuxtLayout>

    </div>
</template>
<style>

</style>