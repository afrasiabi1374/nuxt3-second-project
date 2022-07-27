<script>
  
</script>
<template>
  <div>
    <Html :lang="dynamic > 50 ? 'en-GB' : 'en-US'">
      <Head>
        <Title>Restaurantly!!!</Title>
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
    <div class="container" >
      <h1>welcome to restaurantly Index Page</h1>
      <NuxtLink to="/restaurants">restaurant</NuxtLink>
    </div>

  </div>
</template>
<style scoped>
.container {
  text-align: center;
  margin-top: 5rem;
}
</style>