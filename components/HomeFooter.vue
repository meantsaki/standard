<template>
    <footer>
        <div class="copywrite">
            &#169; The standard Copywrite 2020
        </div>
        <div class="cookies">
            <NuxtLink to="/cookies">Cookies</NuxtLink> | <NuxtLink to="/privecy">Privecy</NuxtLink>
        </div>
        <div class="logo">
            <img src="~assets/s_big.svg" alt="" srcset="">
        </div>
    </footer>
</template>

<script>
    export default {
    }
</script>

<style>
footer{
        height: 48px;
    display: flex;
    align-items: center;
    font-size: 16px;
    background-color: var(--dark);
    color: white;
    padding: 0 72px;
}

footer > *{
    flex-basis: 33.33%;
}

footer .cookies{
    font: normal normal 800 18px/22px Montserrat;
    letter-spacing: 0px;
    text-align: center;
    text-decoration: none;
    color: inherit;
}

footer .cookies a{
    text-decoration-line: none;
    color: inherit;
}

footer .logo{
    text-align: right;
}
</style>