<script>
    import LinkButton from "$lib/components/linkButton.svelte";
</script>

<div class="flex justify-center items-center flex-col h-screen">
    <h1 class="font-medium text-8xl text-blue-500">404</h1>
    <p class="text-lg text-gray-600 text-center px-4 pb-4">
        Úgy néz ki ez az oldal nem található. Lehetséges, hogy elírta az oldal címét!
    </p>
    <LinkButton href="/" text="Ugrás a kezdőlapra" />
    <div class="dottedBg absolute bottom-4 right-4 w-[448px] h-72 z-10 max-lg:hidden" />
    <div class="dottedBg absolute top-8 left-8 w-32 h-32 z-10 max-sm:hidden" />
</div>

<style>
    .dottedBg {
        background-image: radial-gradient(#93c5fd 3px, transparent 0);
        background-size: 40px 40px;
    }
</style>
