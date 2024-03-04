<script>
export default {
    name: 'AppLogo',
}
</script>

<template>
<div class="logo-container">
    <img id="logo" src="/img/logo.png" alt="logo yu-gi-oh">
</div>
</template>

<style lang="scss">
@use '../styles/general' as *;
@use '../styles/variables' as *;

.logo-container {
    display: flex;
    justify-content: center;
    padding: 50px;
    #logo {
        max-width: 300px;
    }
}
</style>
