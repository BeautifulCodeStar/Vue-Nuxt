<template>
    <div id="mySidenav" class="sidenav">
        <div class="logo">
            <app-logo />
        </div>
        <a href="#"><i class="material-icons">account_circle</i><p>About</p></a>
        <a href="#"><i class="material-icons">build</i>Services</a>
        <a href="#"><i class="material-icons">favorite_border</i>Clients</a>
        <a href="#"><i class="material-icons">phone</i>Contact</a>
    </div>
</template>

<script>
    import AppLogo from '~/components/AppLogo.vue'
    export default {
        components: {
            AppLogo
        }
    }
</script>
