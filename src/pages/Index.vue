<template>
<q-page class="q-pa-xs flex flex-center">
  <q-card class="my-card" flat bordered>
      <q-img
        src="https://cdn.quasar.dev/img/parallax2.jpg"
      />

      <q-card-section>
        <div class="text-overline text-orange-9">Welcome to</div>
        <div class="text-h5 q-mt-sm q-mb-xs">Advance edu</div>
        <div class="text-caption text-grey">
          This is a free educational platform that you can use to access, share and download educational material for various education levels; such as high school diploma, bachelors' degree and Masters' degree 
        </div>
      </q-card-section>

      <q-card-actions>
        <q-btn flat color="accent" label="Share" />
        <q-btn flat color="primary" label="Join" />

        <q-space />
      </q-card-actions>
  </q-card>
      <!--<img
      alt="Quasar logo"
      src="~assets/Advance-Vertical-logo.svg"
      style="width: 500px; height: 500px"
    >
   

  <div class="row q-pa-md ">
    <div class="col">
    <q-card class="my-card q-ma-sm">

      <q-card-section class="bg-info text-white">
        <div class="text-h6">Intro to HTML and CSS</div>
        <div class="text-subtitle2">by John Doe</div>
      </q-card-section>
      
      <q-separator />

      <q-card-actions align="center">
        <q-btn flat>Enrol</q-btn>
        <q-btn flat>Study</q-btn>
      </q-card-actions>
    </q-card>
  </div>
  </div>
-->
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex'
})
</script>
