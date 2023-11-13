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
    data() {
        return {};
    },
    methods: {
        colorBody() {
            if (this.isDark == false) {
                return "text-white transition delay-150 duration-300 ease-in-out";
            } else {
                return "text-neutral-900 transition delay-150 duration-300 ease-in-out";
            }
        },
    },
};
</script>


<template>
    <section class="">
        <div class="container max-w-5xl px-4 py-12 mx-auto">
            <div class="grid gap-4 mx-4 sm:grid-cols-12">
                <div class="col-span-12 sm:col-span-3">
                    <div
                        class="text-center sm:text-left mb-14 before:block before:w-24 before:h-3 before:mb-5 before:rounded-md before:mx-auto sm:before:mx-0 before:dark:bg-emerald-400">
                        <h3 :class="colorBody()" class="text-3xl font-semibold">Nossa linha de desenvolvimento:</h3>
                    </div>
                </div>
                <div class="relative col-span-12 px-4 space-y-6 sm:col-span-9">
                    <div
                        class="col-span-12 space-y-12 relative px-4 sm:col-span-8 sm:space-y-8 sm:before:absolute sm:before:top-2 sm:before:bottom-0 sm:before:w-0.5 sm:before:-left-3 before:dark:bg-gray-700">
                        <div
                            class="flex flex-col sm:relative sm:before:absolute sm:before:top-2 sm:before:w-4 sm:before:h-4 sm:before:rounded-full sm:before:left-[-35px] sm:before:z-[1] before:dark:bg-emerald-400">
                            <h3 :class="colorBody()" class="text-xl font-semibold tracki">Semana de alinhamento. </h3>
                            <time class="text-xs tracki uppercase dark:text-gray-400">Semana do seu pedido</time>
                            <p :class="colorBody()" class="mt-3">Nesta semana alinhamos e fazemos o orçamento do seu
                                micro-sistema ou site e
                                documentamos todas as regras de negócio.</p>
                        </div>
                        <div
                            class="flex flex-col sm:relative sm:before:absolute sm:before:top-2 sm:before:w-4 sm:before:h-4 sm:before:rounded-full sm:before:left-[-35px] sm:before:z-[1] before:dark:bg-emerald-400">
                            <h3 :class="colorBody()" class="text-xl font-semibold tracki">In Progress.</h3>
                            <time class="text-xs tracki uppercase dark:text-gray-400">Segunda semana</time>
                            <p :class="colorBody()" class="mt-3">Nesta semana desenvolvemos todo o produto pensado para o
                                seu empreendimento.</p>
                        </div>
                        <div
                            class="flex flex-col sm:relative sm:before:absolute sm:before:top-2 sm:before:w-4 sm:before:h-4 sm:before:rounded-full sm:before:left-[-35px] sm:before:z-[1] before:dark:bg-emerald-400">
                            <h3 :class="colorBody()" class="text-xl font-semibold tracki">Entrega!</h3>
                            <time class="text-xs tracki uppercase dark:text-gray-400">Terceira semana</time>
                            <p :class="colorBody()" class="mt-3">Ao final da segunda semana de desenvolvimento seu produto
                                estará pronto para
                                uso, que tal?</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
