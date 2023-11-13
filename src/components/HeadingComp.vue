<script>
import { useDark, useToggle } from "@vueuse/core";
export default {
  setup() {
    const isDark = useDark();
    const toggle = useToggle(isDark);
    return {
      isDark,
      toggle,
    };
  },
  methods: {
    colorText() {
      if (this.isDark == false) {
        return "mb-4 text-4xl font-extrabold leading-none tracking-tight text-white md:text-text-4xl lg:text-7xl transition delay-150 duration-300 ease-in-out";
      } else {
        return "mb-4 text-4xl font-extrabold text-neutral-700 md:text-text-4xl lg:text-7xl transition delay-150 duration-300 ease-in-out";
      }
    },
    colorButton() {
      if (this.isDark == false) {
        return "m-10 inline-flex items-center justify-center px-5 py-3 text-base font-extrabold text-center text-slate-800 bg-[radial-gradient(ellipse_at_top_left,_var(--tw-gradient-stops))] from-purple-200 via-emerald-600 to-emerald-300 rounded-lg transition delay-150 duration-300 ease-in-out";
      } else {
        return "m-10 inline-flex items-center justify-center px-5 py-3 text-base font-extrabold text-center text-white bg-[radial-gradient(ellipse_at_top_left,_var(--tw-gradient-stops))] from-purple-200 via-emerald-600 to-emerald-300 rounded-lg transition delay-150 duration-300 ease-in-out";
      }
    },
  },
};
</script>

<template>
  <div class="all">
    <div class="flex items-center justify-center">
      <img v-if="isDark == false" class="w-60 transition delay-150" src="../assets/vgstack-mini-white.png" alt="">
      <img v-if="isDark == true" class="w-60 transition delay-150" src="../assets/vgstack-mini-black.png" alt="">
    </div>
    <div class="flex justify-center">
      <h1 :class="colorText()">a sua solução</h1>
    </div>
    <div class="flex justify-center">
      <p class="mb-6 text-lg font-normal text-gray-500 lg:text-xl sm:px-16 xl:px-48">
        Veja como podemos solucionar o seu problema e o problema de muitos outros
        microempreendedores!
      </p>
    </div>
    <div class="flex justify-center">
      <a href="https://wa.me/5547992126662" target="_blank" :class="colorButton()">
        Fale conosco!
        <svg class="w-5 h-5 ml-2 -mr-1" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd"
            d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z"
            clip-rule="evenodd"></path>
        </svg>
      </a>
    </div>
  </div>
</template>

<style scoped>
.all {
  padding: 1rem;
}
</style>
