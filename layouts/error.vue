<template>
    <div class="bg-info container">
        <h1>
            some header here  with custom layout
        </h1>
        <slot name="header"></slot>
        <img
            src="https://www.iconpacks.net/icons/2/free-sad-face-icon-2691-thumb.png"
            alt=""
        />
        <slot name="redirect"></slot>
    </div>
</template>
<style scoped>
    img {
        width: 10rem;
    }
    .container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
</style>
