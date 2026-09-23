<script>
    import { fade } from "svelte/transition";
    import LinkButton from "$lib/components/linkButton.svelte";

    // Actual project data from the document
    let projectData = {
        kedvezmenyezettiNeve: "GOOD HOME Társasházkezelő Korlátolt Felelősségű Társaság",
        projektAzonositoSzama: "DIMOP_PLUSZ-1.2.6-24-2025-01658",
        fejlesztesTargya: "A GOOD HOME Társasházkezelő Kft. digitalizációs célú növekedési támogatás",
        szerzodottTamogatasOsszege: "5.979.295 Ft",
        projektBefejezesDatum: "2027.02.28.",
        megvalosulasHelyszine: "Kecskemét",
        finanszorozoProgramok: [
            "Széchenyi Terv Plusz program",
            "Digitális Megújulás Operatív Program Plusz",
            "Európai Unió és Magyar Állam társfinanszírozás"
        ]
    };

    let projektLeiras = `A GOOD HOME Társasházkezelő Kft. 5,98 millió forint vissza nem térítendő európai uniós támogatásban részesült a Széchenyi Terv Plusz program keretében. A projekt célja a társasházkezelési szolgáltatások digitalizálása, a belső működési folyamatok hatékonyságának növelése, valamint az ügyfélkapcsolatok korszerűsítése.

A Kecskeméten megvalósuló projekt keretében a vállalkozás átfogó informatikai fejlesztést hajt végre. A beruházás során korszerű számítástechnikai és hálózati eszközök kerülnek beszerzésre, amelyek stabilabb, gyorsabb és biztonságosabb informatikai hátteret biztosítanak a napi munkavégzéshez.

A projekt részeként adattárolási, ERP és munkafolyamat-irányítási rendszerek integrálására, valamint az ügyfélkapcsolatokat és a szolgáltatások elérését támogató digitális megoldások bevezetésére kerül sor. A fejlesztések hozzájárulnak ahhoz, hogy a társaság munkafolyamatai átláthatóbbá és hatékonyabbá váljanak, miközben az ügyfélkiszolgálás gyorsabbá és rugalmasabbá válik.

A projekt kiemelt eleme az informatikai biztonság növelése. Az IKT-biztonsági szoftverek, tűzfalak és vírusvédelmi rendszerek bevezetése erősíti az informatikai rendszerek védelmét, és hozzájárul a vállalkozás adatainak biztonságos kezeléséhez. Az online ügyfélkapcsolati és értékesítési modulok pedig támogatják az ügyfelekkel történő kommunikációt és a szolgáltatások könnyebb elérését.`;
</script>

<svelte:head>
    <title>EU Projekt Adatok - GOOD HOME Kft</title>
    <meta name="description" content="Kedvezményezetti információk EU támogatású projektről - DIMOP_PLUSZ-1.2.6-24-2025-01658" />
</svelte:head>

<section class="flex min-h-screen justify-center items-center flex-col p-8 relative bg-white">
    <div class="flex flex-col gap-6 w-3/4 max-md:w-full" in:fade={{ duration: 2000 }}>
        <h1 class="text-4xl underline decoration-blue-500 text-center mb-8">
            EU Projekt Adatok
        </h1>

        <!-- Key Funding Information -->
        <div class="bg-gray-50 shadow-sm rounded-md p-6 space-y-4">
            <div class="border-b pb-3">
                <h2 class="text-xl font-bold text-blue-600 mb-2">Kedvezményezetti Információk</h2>
                <dl class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div>
                        <dt class="font-medium text-gray-700">Kedvezményezett neve:</dt>
                        <dd class="text-gray-900">{projectData.kedvezmenyezettiNeve}</dd>
                    </div>
                    <div>
                        <dt class="font-medium text-gray-700">Projekt azonosító szám:</dt>
                        <dd class="text-gray-900 font-mono">{projectData.projektAzonositoSzama}</dd>
                    </div>
                    <div class="md:col-span-2">
                        <dt class="font-medium text-gray-700">A fejlesztés tárgya:</dt>
                        <dd class="text-gray-900">{projectData.fejlesztesTargya}</dd>
                    </div>
                    <div>
                        <dt class="font-medium text-gray-700">Szerződött támogatás összege:</dt>
                        <dd class="text-gray-900 font-semibold">{projectData.szerzodottTamogatasOsszege}</dd>
                    </div>
                    <div>
                        <dt class="font-medium text-gray-700">Projekt befejezés dátuma:</dt>
                        <dd class="text-gray-900">{projectData.projektBefejezesDatum}</dd>
                    </div>
                    <div>
                        <dt class="font-medium text-gray-700">Megvalósítás helyszíne:</dt>
                        <dd class="text-gray-900">{projectData.megvalosulasHelyszine}</dd>
                    </div>
                </dl>
            </div>

            <!-- Funding Programs -->
            <div class="border-b pb-3">
                <h2 class="text-xl font-bold text-blue-600 mb-2">Finanszírozás</h2>
                <ul class="list-disc list-inside text-gray-700 space-y-1">
                    {#each projectData.finanszorozoProgramok as program}
                        <li>{program}</li>
                    {/each}
                </ul>
            </div>

            <!-- Project Description -->
            <div>
                <h2 class="text-xl font-bold text-blue-600 mb-2">Projekt Részletes Leírása</h2>
                <div class="text-gray-700 leading-relaxed whitespace-pre-line">
                    {projektLeiras}
                </div>
            </div>
        </div>

        <!-- Navigation -->
        <div class="flex justify-center mt-6">
            <LinkButton href="/" text="Vissza a főoldalra" />
        </div>
    </div>
</section>
