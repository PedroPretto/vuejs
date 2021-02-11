<template>
  <header class="header">
    <div class="header-group w-4/5">
        <div class="flex items-center justify-between py-10">
            <div class="w-28 text-white lg:w-36 ">
                LOGO
            </div>
            <div class="flex">
                <button @click="() => emit('login')" class="px-6 py-2 font-bold bg-white rounded-full text-brand-main focus:outline-none">Entrar</button>
                <button class="px-6 py-2 font-bold rounded-full text-white focus:outline-none">Crie uma conta</button>
            </div>
        </div>
        <div class="flex flex-col mt-28">
            <h1 class="text-4xl font-black text-white">
                Tenha um feedback. <br>
                E faça seus clientes mais <br class="hidden  lg:inline-block">
                felizes!
            </h1>
            <p class="text-lg font-medium text-white">
                Receba ideias, reclamações e feedbacks com um <br class="hidden lg:inline-block">
                simplles widget na página
            </p>
        </div>
        <div>
            <button class="px-6 py-2 font-bold bg-white rounded-full text-brand-main focus:outline-none">Crie uma conta grátis</button>
        </div>

    </div>
  </header>
</template>

<script>
export default {
  setup (_, { emit }) { return { emit } }
}
</script>

<style lang="postcss" scoped>
.header{
    @apply bg-brand-main w-full flex justify-center;
    height: 700px;
}

@media (min-width: 640px){

}
</style>
