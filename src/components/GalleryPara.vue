<template>
  <div class="gallery-para-wrapper">
    <q-parallax class="gallery-parallax" :height="800">
      <template v-slot:media>
        <div class="image-container">
          <img src="~assets/download (1).jpg" class="gallery-img img-1" alt="image 1" />
          <img src="~assets/download (2).jpg" class="gallery-img img-2" alt="image 2" />
          <img src="~assets/download (3).jpg" class="gallery-img img-3" alt="image 3" />
          <img src="~assets/download (4).jpg" class="gallery-img img-4" alt="image 4" />
          <img src="~assets/download (5).jpg" class="gallery-img img-5" alt="image 5" />
          <img src="~assets/download (6).jpg" class="gallery-img img-6" alt="image 6" />
          <img src="~assets/download (7).jpg" class="gallery-img img-7" alt="image 7" />
        </div>
      </template>

      <template v-slot:content="scope">
        <div class="parallax-content" :style="contentStyle(scope)">
          <h1 class="text-white">I think this looks cool, do you?...</h1>
        </div>
      </template>
    </q-parallax>
  </div>
</template>

<script>
export default {
  methods: {
    contentStyle(scope) {
      return {
        opacity: 0.45 + (1 - scope.percentScrolled) * 0.55,
        top: scope.percentScrolled * 80 + '%',
      }
    },
  },
}
</script>

<style scoped>
.gallery-para-wrapper {
  width: 100%;
  height: 800px;
  position: relative;
  margin-bottom: 40px;
}

.image-container {
  left: 800px !important;
}

.gallery-para-wrapper .gallery-parallax {
  height: 100% !important;
  margin: 0 !important;
  padding: 0 !important;
}

.gallery-para-wrapper .image-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: visible; /* Changed from hidden */
}

.gallery-para-wrapper .gallery-img {
  position: absolute;
  height: 300px; /* Changed from max-height */
  width: auto;
  object-fit: cover;
  transition: transform 0.3s ease;
  z-index: 1;
}

.gallery-para-wrapper .gallery-img:hover {
  transform: scale(1.05);
  z-index: 10;
}

/* Individual image positions */
.gallery-para-wrapper .img-1 {
  top: 10%;
  left: 5%;
}
.gallery-para-wrapper .img-2 {
  top: 30%;
  left: 70%;
}
.gallery-para-wrapper .img-3 {
  top: 60%;
  left: 15%;
}
.gallery-para-wrapper .img-4 {
  top: 20%;
  left: 40%;
}
.gallery-para-wrapper .img-5 {
  top: 70%;
  left: 60%;
}
.gallery-para-wrapper .img-6 {
  top: 40%;
  left: 25%;
}
.gallery-para-wrapper .img-7 {
  top: 10%;
  left: 80%;
}

.gallery-para-wrapper .parallax-content {
  position: absolute;
  left: 0;
  right: 0;
  text-align: center;
  z-index: 5;
}
</style>
