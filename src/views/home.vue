<script>
import { useDark, useToggle } from "@vueuse/core";
import headercomp from "../components/HeaderComp.vue";
import footercomp from "../components/FooterComp.vue";
import timeline from "../components/timeline.vue"
import headingcomp from "../components/HeadingComp.vue"
export default {
  components: { headercomp, footercomp, headingcomp, timeline },
  setup() {
    const isDark = useDark();
    const toggle = useToggle(isDark);
    return {
      isDark,
      toggle,
    };
  },
  data() {
    return {};
  },
  methods: {
    colorBody() {
      if (this.isDark == false) {
        return "bg-neutral-900 transition delay-150 duration-300 ease-in-out";
      } else {
        return "bg-white transition delay-150 duration-300 ease-in-out";
      }
    },
  },
};
</script>

<template>
  <body :class="colorBody()">
    <headercomp />
    <div v-if="isDark" class="video-container">
      <video width="1200" height="360" controls loop autoplay>
        <source src="../assets/proatividade.mp4" type="video/mp4">
        Seu navegador não suporta o elemento de vídeo.
      </video>
    </div>

    <div v-else class="video-container">
      <video width="1200" height="360" controls loop autoplay>
        <source src="../assets/automatize.mp4" type="video/mp4">
        Seu navegador não suporta o elemento de vídeo.
      </video>
    </div>

    <div class="m-20"></div>

    <headingcomp />

    <div class="center-timeline">
      <timeline />
    </div>

    <footercomp />
  </body>
</template>

<style scoped>
.center-timeline {
  display: flex;
  justify-content: center;
  align-items: center;
}

.video-container {
  display: flex;
  justify-content: center;
  align-items: center;
  /* Ajuste a altura conforme necessário */
}
</style>