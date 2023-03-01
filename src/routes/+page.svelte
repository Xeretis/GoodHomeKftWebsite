<script>
    import { fade, fly } from "svelte/transition";
    import { sineInOut } from "svelte/easing";
    import { onMount } from "svelte";
    import { inview } from "svelte-inview";
    import Countup from "svelte-countup";
    import handhakeImg from "$lib/assets/handshake.jpg";
    import houseBlockImg from "$lib/assets/houseblock.jpg";
    import aboutimage from "$lib/assets/aboutimage.jpg";
    import SvgTitle from "$lib/components/svgTitle.svelte";
    import LinkButton from "$lib/components/linkButton.svelte";

    let drawLanding = false;

    onMount(() => {
        drawLanding = true;
    });

    let aboutInView;
    let contactInView;
</script>

<section class="flex justify-center items-center flex-col h-screen relative" id="landing" role="banner">
    {#if drawLanding}
        <SvgTitle />
        <p
            class="text-center pt-4 text-blue-500 max-sm:text-xs"
            transition:fly={{ duration: 3000, delay: 2200, y: 20 }}
        >
            Közösképviselés és könyvelés már x éve Kecskeméten
        </p>
        <div class="flex gap-4 pt-4" transition:fly={{ duration: 2500, delay: 2200, y: 20 }}>
            <LinkButton href="#about" text="Rólunk" />
            <LinkButton href="#" text="Ügyfélkapu" />
        </div>
        <img
            class="absolute w-96 h-64 bottom-8 sm:left-8 rounded-lg opacity-75 grayscale shortHidden"
            src={handhakeImg}
            transition:fly={{ duration: 2500, delay: 2200, y: 20 }}
            alt="Két kéz, kézfogás közben"
        />
        <div
            class="dottedBg absolute bottom-8 sm:bottom-12 sm:left-14 left-6 w-96 h-72 z-10 shortHidden"
            transition:fade={{ duration: 2500, delay: 2200 }}
        />
        <img
            class="absolute w-72 h-48 top-8 sm:right-8 rounded-lg opacity-80 brightness-[.65] grayscale shortHidden"
            src={houseBlockImg}
            transition:fly={{ duration: 2500, delay: 2200, y: 20 }}
            alt="Egy társasház"
        />
        <div
            class="dottedBg absolute top-16 right-6 sm:right-20 w-72 h-48 z-10 shortHidden"
            transition:fade={{ duration: 2500, delay: 2200 }}
        />
        <div
            class="dottedBg absolute bottom-4 right-4 w-[448px] h-72 z-10 max-lg:hidden"
            transition:fade={{ duration: 2500, delay: 2200 }}
        />
        <div
            class="dottedBg absolute top-8 left-8 w-32 h-32 z-10 max-sm:hidden"
            transition:fade={{ duration: 2500, delay: 2200 }}
        />
    {/if}
</section>
<section
    class="flex min-h-screen justify-center items-center flex-col relative"
    id="about"
    role="article"
    use:inview={{ unobserveOnEnter: true, rootMargin: "-20%" }}
    on:change={({ detail }) => {
        aboutInView = detail.inView;
    }}
>
    {#if aboutInView}
        <div class="flex gap-6 m-4 w-3/4 max-md:flex-col" in:fade={{ duration: 3000, easing: sineInOut }}>
            <img src={aboutimage} alt="About us" class="w-64 h-96 rounded-lg max-md:hidden" />
            <div class="flex flex-col gap-4">
                <h2 class="text-4xl underline decoration-blue-500 max-md:text-center">Rólunk</h2>
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium dolorum dolores ab, modi
                    possimus illo fugit, necessitatibus odit saepe, hic ad ducimus! In at praesentium repellendus minima
                    quis aut delectus! Lorem ipsum dolor sit amet consectetur adipisicing elit. Sed veritatis qui fugit
                    necessitatibus voluptatibus repudiandae mollitia quos alias, non praesentium ipsa illo rem labore
                    amet earum vel optio ut corporis!
                </p>
                <div class="flex gap-4 lg:mt-6 md:h-full md:items-center">
                    <div class="flex flex-1 flex-col p-2">
                        <div class="w-8 h-8 sm:w-12 sm:h-12 self-center">
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                viewBox="0 0 24 24"
                                stroke-width="1.5"
                                stroke="#3b82f6"
                                preserveAspectRatio="xMinYMin meet"
                                fill="none"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                            >
                                <title>Társasház ikon</title>
                                <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                                <path d="M3 21l18 0" />
                                <path d="M9 8l1 0" />
                                <path d="M9 12l1 0" />
                                <path d="M9 16l1 0" />
                                <path d="M14 8l1 0" />
                                <path d="M14 12l1 0" />
                                <path d="M14 16l1 0" />
                                <path d="M5 21v-16a2 2 0 0 1 2 -2h10a2 2 0 0 1 2 2v16" />
                            </svg>
                        </div>
                        <p class="p-2 text-center">
                            <span class="text-blue-500 font-bold">
                                <Countup value={30} />+
                            </span> társasház
                        </p>
                    </div>
                    <div class="flex flex-1 flex-col p-2">
                        <div class="w-8 h-8 sm:w-12 sm:h-12 self-center">
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                preserveAspectRatio="xMinYMin meet"
                                viewBox="0 0 24 24"
                                stroke-width="1.5"
                                stroke="#3b82f6"
                                fill="none"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                            >
                                <title>Lakók ikon</title>
                                <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                                <path d="M9 7m-4 0a4 4 0 1 0 8 0a4 4 0 1 0 -8 0" />
                                <path d="M3 21v-2a4 4 0 0 1 4 -4h4a4 4 0 0 1 4 4v2" />
                                <path d="M16 3.13a4 4 0 0 1 0 7.75" />
                                <path d="M21 21v-2a4 4 0 0 0 -3 -3.85" />
                            </svg>
                        </div>
                        <p class="p-2 text-center">
                            <span class="text-blue-500 font-bold">
                                <Countup value={600} />+
                            </span> elégedett lakó
                        </p>
                    </div>
                </div>
            </div>
        </div>
    {/if}
</section>
<section
    class="flex min-h-screen justify-center items-center flex-col relative"
    id="contact"
    role="article"
    use:inview={{ unobserveOnEnter: true, rootMargin: "-20%" }}
    on:change={({ detail }) => {
        contactInView = detail.inView;
    }}
>
    {#if contactInView}
        <div class="flex flex-col m-4 w-3/4 max-md:flex-col" in:fade={{ duration: 3000, easing: sineInOut }}>
            <h2 class="text-4xl underline decoration-blue-500 text-center mb-8">Kapcsolat</h2>
            <div class="flex justify-between p-4 mb-4 gap-2 bg-gray-50 shadow-sm rounded-md">
                <div class="flex gap-2">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="24"
                        height="24"
                        viewBox="0 0 24 24"
                        stroke-width="2"
                        stroke="currentColor"
                        fill="none"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                    >
                        <title>Email ikon</title>
                        <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                        <path d="M12 12m-4 0a4 4 0 1 0 8 0a4 4 0 1 0 -8 0" />
                        <path d="M16 12v1.5a2.5 2.5 0 0 0 5 0v-1.5a9 9 0 1 0 -5.5 8.28" />
                    </svg>
                    <p class="font-medium">Email</p>
                </div>
                <a href="mailto:katticka@gmail.com" class="text-blue-500 underline truncate block">katticka@gmail.com</a
                >
            </div>
            <div class="flex justify-between p-4 mb-4 gap-2 bg-gray-50 shadow-sm rounded-md">
                <div class="flex gap-2">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="24"
                        height="24"
                        viewBox="0 0 24 24"
                        stroke-width="2"
                        stroke="currentColor"
                        fill="none"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                    >
                        <title>Telefon ikon</title>
                        <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                        <path
                            d="M5 4h4l2 5l-2.5 1.5a11 11 0 0 0 5 5l1.5 -2.5l5 2v4a2 2 0 0 1 -2 2a16 16 0 0 1 -15 -15a2 2 0 0 1 2 -2"
                        />
                    </svg>
                    <p class="font-medium">Telefon</p>
                </div>
                <a href="tel:+36202636776" class="text-blue-500 underline truncate block">+36 20 263 6776</a>
            </div>
            <div class="flex justify-between gap-2 p-4 mb-4 bg-gray-50 shadow-sm rounded-md">
                <div class="flex gap-2">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="24"
                        height="24"
                        viewBox="0 0 24 24"
                        stroke-width="2"
                        stroke="currentColor"
                        fill="none"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                    >
                        <title>Cím ikon</title>
                        <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                        <path d="M12 11m-3 0a3 3 0 1 0 6 0a3 3 0 1 0 -6 0" />
                        <path d="M17.657 16.657l-4.243 4.243a2 2 0 0 1 -2.827 0l-4.244 -4.243a8 8 0 1 1 11.314 0z" />
                    </svg>
                    <p class="font-medium">Cím</p>
                </div>
                <a
                    href="https://goo.gl/maps/BYYd15k9dCtmVwLn7"
                    target="_blank"
                    rel="noreferrer"
                    class="text-blue-500 underline truncate block"
                >
                    6000, Kecskemét, Alpár u. 7.
                </a>
            </div>
            <div class="flex justify-center">
                <LinkButton href="#landing" text="Vissza az oldal tetejére" />
            </div>
        </div>
        <a
            href="https://github.com/Xeretis/GoodHomeKftWebsite"
            target="_blank"
            rel="noreferrer"
            class="absolute bottom-5 right-5"
            aria-label="Forrás kód megtekintése GitHubon"
            in:fade={{ duration: 3000, easing: sineInOut }}
        >
            <svg
                xmlns="http://www.w3.org/2000/svg"
                class="icon icon-tabler icon-tabler-brand-github"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                stroke-width="2"
                stroke="#3B82F6"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
            >
                <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                <path
                    d="M9 19c-4.3 1.4 -4.3 -2.5 -6 -3m12 5v-3.5c0 -1 .1 -1.4 -.5 -2c2.8 -.3 5.5 -1.4 5.5 -6a4.6 4.6 0 0 0 -1.3 -3.2a4.2 4.2 0 0 0 -.1 -3.2s-1.1 -.3 -3.5 1.3a12.3 12.3 0 0 0 -6.2 0c-2.4 -1.6 -3.5 -1.3 -3.5 -1.3a4.2 4.2 0 0 0 -.1 3.2a4.6 4.6 0 0 0 -1.3 3.2c0 4.6 2.7 5.7 5.5 6c-.6 .6 -.6 1.2 -.5 2v3.5"
                />
            </svg>
        </a>
    {/if}
</section>

<style>
    .dottedBg {
        background-image: radial-gradient(#93c5fd 3px, transparent 0);
        background-size: 40px 40px;
    }

    @media (max-height: 816px) {
        .shortHidden {
            display: none;
        }
    }
</style>
