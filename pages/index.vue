<template>
  <div>
    <basic-section>
      <vueper-slides :fixed-height="true" :arrows="false">
        <vueper-slide v-for="(slide, i) in slides" :key="i" :title="slide.title" :content="slide.content" />
      </vueper-slides>
    </basic-section>
    <basic-section/>
    <basic-section/>
    <home-footer/>
  </div>
</template>

<script>
  import {
    VueperSlides,
    VueperSlide
  } from 'vueperslides'
  import 'vueperslides/dist/vueperslides.css'
  export default {
    components: {
      VueperSlides,
      VueperSlide,
    },
    data() {
      return {
        slides: [{
          title: 'Slide #1',
          content: '<img src="/_nuxt/assets/wall (1).png" alt="" srcset="">'
        },
        {
          title: 'Slide #2',
          content: '<img src="/_nuxt/assets/wall (1).png" alt="" srcset="">'
        }]
      }
    }
  }
</script>

<style>
.vueperslides,
.vueperslide__content,
.vueperslide__content img{
  width:100vw;
  height:100vh;
}
</style>