<template>
  <div class="banner-2 md:flex items-center md:justify-evenly" id="about">
    <img
      class="md:h-[500px] h-[400px]"
      src="../assets/about-female.png"
      alt="user image"
    />
    <div class="space-y-5 py-8 px-8 md:py-16 md:px-20 md:w-1/2">
      <h4 class="project-title2 item">CONTACTO</h4>

      <Form
        action="https://formsubmit.co/devdnia@gmail.com" method="POST"
        @submit="submitForm"
        :validation-schema="schema"
        v-slot="{ errors }"
        class="max-w-sm mx-auto"
      >
        <!-- Nombre -->
        <div class="mb-5">
          <label for="name" class="block mb-2 text-sm font-medium text-white"
            >Nombre</label
          >
          <Field
            v-model="formData.name"
            type="text"
            id="name"
            name="name"
            :class="{ 'border-purple-600 border-2': errors.name }"
            class="bg-green-50 border placeholder-slate-40 text-sm rounded-lg block w-full p-2.5"
            placeholder="Nombre"
          />
          <span v-if="errors.name" class="text-purple-800 mt-4">{{ errors.name }}</span>
        </div>

        <!-- Email -->
        <div class="mb-5">
          <label for="email" class="block mb-2 text-sm font-medium text-white"
            >Correo electrónico</label
          >
          <Field
            v-model="formData.email"
            type="email"
            id="email"
            name="email"
            :class="{ 'border-purple-600 border-2': errors.email }"
            class="bg-green-50 border placeholder-slate-40 text-sm rounded-lg block w-full p-2.5"
            placeholder="Correo electrónico"
          />
          <span v-if="errors.email" class="text-purple-800 mt-4">{{ errors.email }}</span>
        </div>

        <!-- Teléfono -->
        <div>
          <label for="phone" class="block mb-2 text-sm font-medium text-white"
            >Teléfono</label
          >
          <Field
            v-model="formData.phone"
            type="number"
            id="phone"
            name="phone"
            :class="{ 'border-purple-600 border-2': errors.phone }"
            class="bg-red-50 border placeholder-slate-400 text-sm rounded-lg block w-full p-2.5"
            placeholder="Teléfono"
          />
          <span v-if="errors.phone" class="text-purple-800 mt-4">{{
            errors.phone
          }}</span>
        </div>

     <!-- Comentario -->
     <div class="mt-5">
          <label for="comment" class="block mb-2 text-sm font-medium text-white"
            >¿ En qué le puedo ayudar? </label
          >
            <Field
              as="textarea"
              v-model="formData.comment"
              :bind="field"
              id="comment"
              name="comment"
              :class="{ 'border-purple-600 border-2': errors.comment }"
              class="bg-red-50 border placeholder-slate-400 text-sm rounded-lg block w-full p-2.5"
            />
          <span v-if="errors.comment" class="text-purple-800 mt-4">{{
            errors.comment
          }}</span>
        </div>


        <button
          type="submit"
          class="bg-white mt-8 rounded-full p-3 hover:bg-gray-200 border-2 border-gray-800 3xl:text-xl 2xl:text-xl lg:text-xl md:text-xl text-xs py-2 px-4 lg:py-4 lg:px-8 rounded-2xl font-work_sans font-semibold"
        >
          ENVIAR
        </button>
      </Form>

    </div>
  </div>
</template>

<script>
import * as Yup from "yup";
import { Form, Field } from "vee-validate";

export default {
  components:{
    Form,
    Field,
  },
  data() {
    const schema = Yup.object().shape({
      name: Yup.string().required("El nombre es obligatorio"),
      email: Yup.string().email("Introduce un formato de email válido"),
      phone: Yup.string().required("El teléfono es obligatorio").min(9, "Son 9 dígitos como mínimo"),
      comment: Yup.string()
    }) 
    return {
      formData: {
        name: "",
        email: "",
        phone: "",
        comment: "",
      },
      errors: {},
      schema,
    };
  },
  methods: {
    async submitForm( values ) {

      if( values.email === undefined ){
        this.formData.email = "Sin correo electrónico"
      }
      if( values.comment === undefined ){
        this.formData.comment = "Sin comentarios"
      }
      this.formData.name    = values.name
      this.formData.phone   = values.phone
      this.formData.comment = values.comment


    },
  },
};
</script>

<style>
/* Aquí puedes añadir estilos adicionales si es necesario */
</style>
