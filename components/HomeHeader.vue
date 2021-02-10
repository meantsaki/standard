<template>
    <v-app-bar class="flex-container" fixed app>
        <div class="logo">

        </div>
        
        <div class="links">
            <NuxtLink to="/">Home page</NuxtLink>
            <NuxtLink to="/1">Lol2</NuxtLink>
            <NuxtLink to="/2">Lol2</NuxtLink>
        </div>        
        
        <div class="logo">
            EN | GR
        </div>
        <!-- <v-icon>mdi-application</v-icon> example of icon -->
    </v-app-bar>
</template>

<script>
    export default {
    }
</script>

<style>

.v-application header .logo{
    color: white;
}
.v-application header a{
    color: var(--white);
    text-transform: capitalize;
    text-decoration: none;
    border-top: 8px solid transparent;
    border-bottom: 8px solid transparent;
    padding: 5px;
    margin: 0 5px;
}

.v-application header a.nuxt-link-exact-active,
.v-application header a:hover{
    color: var(--green);
    border-bottom: 8px solid var(--green);
}

.v-toolbar__content{
    display: flex;
    justify-content: space-between;
    background-color: var(--dark);
}
header .logo{
    width: 144px;
    min-height: 1px;
    text-align: right;
}
header .logo::after{
    content: '';
    background: transparent url(/_nuxt/assets/s_big.svg) no-repeat padding-box;
    height: 72px;
    width: 72px;
    position: fixed;
    background-size: contain;
    left: 72px;
    top: 26px;
}

.links{
    display: flex;
    font:18px;
    flex-grow: 1;
    justify-content: center;
}
</style>