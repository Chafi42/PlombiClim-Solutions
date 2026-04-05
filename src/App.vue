<template>
  <div class="app ">
    <Navbar />
    <main>
      <Hero id="accueil" />
      <Specialties id="specialites"/>
      <Services id="services"/>
      <Testimonials id="temoignages"/>
      <div id="contact">
        <ContactForm />
      </div>
      
      
    </main>
    <Footer />
  </div>
</template>

<script setup>
// IMPORTATION VITALE : Assure-toi que le chemin est correct
import './assets/main.css'; 

import Navbar from '@/components/Navbar.vue';
import Hero from '@/components/Hero.vue';
import Specialties from '@/components/Specialties.vue';
import Services from '@/components/Services.vue';
import Testimonials from '@/components/Testimonials.vue';
import ContactForm from '@/components/ContactForm.vue';
import Footer from '@/components/Footer.vue'; 

</script>

<style>

.manrope {
  font-family: "Manrope", sans-serif;
  font-optical-sizing: auto;
  font-weight: 400;
  font-style: normal;
}
</style>