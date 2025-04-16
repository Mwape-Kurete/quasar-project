<template>
  <!-- Main Quasar Layout -->
  <q-layout view="hHh lpR fFf">
    <!-- Fixed Header -->
    <q-header elevated class="bg-primary text-white" height-hint="98">
      <q-tabs align="left">
        <q-route-tab to="/page1" label="Page One" />
        <q-route-tab to="/page2" label="Page Two" />
        <q-route-tab to="/page3" label="Page Three" />
      </q-tabs>
    </q-header>

    <!-- Page Content Container -->
    <q-page-container class="q-pa-none">
      <!-- Removed padding here -->

      <!-- Main Content Sections -->
      <div class="container-fluid">
        <!-- Hero Parallax Section -->
        <div class="row">
          <div class="col-12 hero">
            <q-parallax src="../assets/bg.png" class="hero-parallax" style="height: 750px">
              <h1 class="text-white">Explore...</h1>
              <br />
              <p>A collection of photography I found on pinterest.</p>
            </q-parallax>
          </div>
        </div>

        <!-- Gallery Section -->
        <div class="row para-images">
          <div class="col-12">
            <GallaryPara />
          </div>
        </div>

        <!-- Stepper Section -->
        <div class="row stepper-section" id="first-sect">
          <div class="col-md-6 explainer">
            <h1 class="stepper-explain">Here's another Quasar Element...</h1>
          </div>
          <div class="col-md-6">
            <Stepper />
          </div>
        </div>
      </div>

      <!--Input field-->
      <div class="row newsletter">
        <div class="col-12 inputbox" align="center">
          <h5>If i had a newsletter, this is where you'd sign up for it</h5>
          <div class="actual-input">
            <q-input rounded outlined v-model="text" label="your email" />
          </div>
        </div>
      </div>

      <!-- Router View (for other pages) -->
      <router-view />
    </q-page-container>

    <!-- Footer -->
    <q-footer elevated class="footer-class text-white">
      <div align="center">
        <p>...</p>
      </div>
    </q-footer>
  </q-layout>
</template>

<script setup>
import GallaryPara from '../components/GalleryPara.vue'
import Stepper from '../components/VerticalStepper.vue'
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:ital,wght@0,100..700;1,100..700&family=Special+Gothic+Expanded+One&display=swap');

/* Base Styles */
body {
  margin: 0;
  padding: 0;
  background-color: #212121;
  font-family: 'Josefin Sans', sans-serif;
}

/* Typography */
h1 {
  font-family: 'Special Gothic Expanded One', sans-serif;
  font-weight: 400;
  font-size: 128px;
  margin: 0;
}

.q-parallax__media > img {
  height: 1080px !important;
}

.stepper-explain {
  font-size: 64px;
  padding-left: 15px;
  color: white;
}

p {
  font-weight: 300;
  font-style: italic;
  font-size: 32px;
  color: white;
  margin: 0;
}

/* Header */
.q-header {
  color: #ffdd33 !important;
  background-color: #212121 !important;
  font-weight: 400;
  padding: 10px;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;
}

.q-route-tab:hover {
  border-radius: 50px;
  background-color: rgba(255, 221, 51, 0.1);
}

/* Layout Adjustments */
.container-fluid {
  padding-top: -168px; /* Match header height */
  margin: 0;
  width: 100%;
}

/* Hero Parallax */
.hero-parallax {
  margin-top: -90px !important;
}

/* Stepper Section */
.stepper-section {
  margin-top: 45px;
  align-items: center;
}

/* Footer */
.footer-class {
  height: 50px;
  background-color: #ffdd33;
  color: #212121;
  padding: 10px;
}

.footer-class p {
  color: #212121;
}

.newsletter {
  margin-top: 5%;
  height: 400px;
  background-color: #c06726;
  display: flex;
  justify-content: center;
  align-self: center;
  align-items: center;
}

.q-input {
  width: 400px;
}

.q-field--highlighted .q-field__label {
  color: white !important;
}

.q-field--outlined .q-field__control:after {
  border-color: white !important;
}

/* Responsive Adjustments */
@media (max-width: 768px) {
  h1 {
    font-size: 64px;
  }
  .stepper-explain {
    font-size: 32px;
  }
  .hero-parallax {
    height: 500px;
    margin-top: -30px;
  }
}
</style>
