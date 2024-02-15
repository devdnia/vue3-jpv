<template>
    <navbar-vue />
    <main-vue />
    <works-vue />
    <works-slider-vue />
    <contact-form-vue />
    <footer-vue />
</template>

<script>
import NavbarVue from '../components/Navbar.vue'
import MainVue from '../components/Main.vue'
import WorksVue from '../components/Works.vue'
import WorksSliderVue from '../components/WorksSlider.vue'
import ContactFormVue from '../components/ContactForm.vue'
import FooterVue from '../components/Footer.vue'
    

export default {
    components :{
        NavbarVue,
        MainVue,
        WorksVue,
        WorksSliderVue,
        ContactFormVue,
        FooterVue
    }
}
</script>

<style>

</style>