<template>
    <navbar-vue />
    <main-vue />
    <works-vue />
    <carousel />
    <contact-form-vue />
    <footer-vue />
</template>

<script>
import NavbarVue from '../components/Navbar.vue'
import MainVue from '../components/Main.vue'
import WorksVue from '../components/Works.vue'
import ContactFormVue from '../components/ContactForm.vue'
import FooterVue from '../components/Footer.vue'
import Carousel from '../components/Carousel.vue'

    

export default {
    components :{
        NavbarVue,
        MainVue,
        WorksVue,
        ContactFormVue,
        FooterVue,
        Carousel
    }
}
</script>

<style>

</style>