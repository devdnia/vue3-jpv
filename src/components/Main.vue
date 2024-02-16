<template>
      <div class="flex items-center banner-1">
      <div class="w-11/12 space-y-5 md:space-y-10">
        <h3
          class="hello-button text-white w-fit md:py-3 md:px-5 py-1 px-2 rounded-lg 3xl:text-3xl 2xl:text-xl lg:text-xl md:text-md text-sm font-semibold font-work_sans"
        >
           ! A PINTAR!
        </h3>
        <h1
          class="3xl:text-8xl 2xl:text-7xl xl:text-6xl lg:text-4xl md:text-3xl sm:text-3xl text-xl font-Eczar font-bold leading-tight text-gray-700"
        >
          Soy
          <a
            href="mailto:iperezportillo1984@gmail.com?Subject=Interesado%20en%20pintar"
            target="_blank"
            class="text-black hover:underline"
          >
            Jordi Portillo</a
          >🎨<br />un pintor de altura
        </h1>

        <div class="md:flex gap-1 md:gap-10">
          <a 
            class="text-white bg-gray-800 submit-button hidden md:block hover:bg-slate-600"
            href="#testimonial" v-smooth-scroll
          >
            MIS TRABAJOS
          </a>
          <a
            class="text-gray-800 border-4 border-gray-800 submit-button mb-5 md:mb-0 hover:bg-red-200"
            href="#about" v-smooth-scroll
          >
            CONTACTO
          </a>
        </div>
      </div>

      <div class="w-8/12 flex justify-end">
        <img
          class="3xl:h-[800px] 2xl:h-[650px] xl:h-[550px] lg:h-[550px] md:h-[450px] sm:h-[350px]"
          src="../assets/profile-female.png"
          alt="user image"
        />
      </div>
    </div>
</template>

<script>
export default {

}
</script>

<style>

</style>