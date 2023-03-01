<script lang="ts">
    export let href: string;
    export let text: string;
</script>

<a {href} class="relative inline-block text-lg group">
    <span
        class="relative z-10 block px-3 py-2 sm:px-5 sm:py-3 overflow-hidden leading-tight text-blue-500 transition-colors duration-300 ease-out border-[1px] sm:border-2 border-blue-500 rounded-lg group-hover:text-white"
    >
        <span class="absolute inset-0 w-full h-full px-3 py-2 sm:px-5 sm:py-3 rounded-lg bg-gray-50" />
        <span
            class="absolute left-0 w-96 h-96 -ml-2 transition-all duration-300 origin-top-right -rotate-90 -translate-x-full translate-y-12 bg-blue-500 group-hover:-rotate-180 ease"
        />
        <span class="relative">{text}</span>
    </span>
    <span
        class="absolute bottom-0 right-0 w-full h-10 sm:h-12 -mb-1 -mr-1 transition-all duration-200 ease-linear bg-blue-500 rounded-lg group-hover:mb-0 group-hover:mr-0"
        data-rounded="rounded-lg"
    />
</a>
