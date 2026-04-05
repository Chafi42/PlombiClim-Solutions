<template>
  <div>
   
    <Hero />
    <Specialties />
    <ContactForm />
   
  </div>
</template>

<script setup>
import Hero from '@/components/Hero.vue';
import Specialties from '@/components/Specialties.vue';
import ContactForm from '@/components/ContactForm.vue';

App.value = {
  components: {
    App,
    Header,
    Hero,
    Specialties,
    ContactForm
  }
}
</script>