<script>
    import { page } from "$app/stores";
    import { onMount } from "svelte";
    let dashboardMenu =[
        { name: "Dashboard", href: "/dashboard", icon: null},
        { name: "Actividad", href: null, icon: null},
        { name: "Mensualidades", href: null, icon: null},
        { name: "Clientes", href: null, icon: null},
    ];

    let openMenu;
    onMount(() => {
        openMenu = window.innerWidth > 1024;
    });

    function toggleMenu() {
        openMenu = !openMenu;
    }
</script>

<main class="flex flex-row">
    <button class={`${openMenu ? "opacity-50" : "opacity-0 pointer-events-none"} fixed bg-black w-screen h-screen top-0 right-0 lg:hidden `} on:click={toggleMenu}></button>
    <nav class={`h-screen w-72 bg-gray-100 shadow flex flex-col p-4 fixed lg:static ${openMenu ? '':'-translate-x-full lg:absolute'}`}>
        <a class="flex items-center gap-2 self-center" href="/">
            <svg class="w-6 h-auto" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><!--!Font Awesome Free 6.6.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.--><path d="M135.2 117.4L109.1 192l293.8 0-26.1-74.6C372.3 104.6 360.2 96 346.6 96L165.4 96c-13.6 0-25.7 8.6-30.2 21.4zM39.6 196.8L74.8 96.3C88.3 57.8 124.6 32 165.4 32l181.2 0c40.8 0 77.1 25.8 90.6 64.3l35.2 100.5c23.2 9.6 39.6 32.5 39.6 59.2l0 144 0 48c0 17.7-14.3 32-32 32l-32 0c-17.7 0-32-14.3-32-32l0-48L96 400l0 48c0 17.7-14.3 32-32 32l-32 0c-17.7 0-32-14.3-32-32l0-48L0 256c0-26.7 16.4-49.6 39.6-59.2zM128 288a32 32 0 1 0 -64 0 32 32 0 1 0 64 0zm288 32a32 32 0 1 0 0-64 32 32 0 1 0 0 64z"/></svg>
            <span class="text-2xl font-bold">Parking Manager</span>
        </a>
        <span class="font-semibold text-sm self-center">v0.0.1</span>
        <div class="flex-1 mt-4">
            <hr>
            <ul class="pt-2">
                {#each dashboardMenu as menu}
                    <li>
                        <a class={`block text-lg py-2 px-4 rounded border-l-2 border-transparent hover:border-black mt-2 ${$page.url.pathname === menu.href ? 'font-bold bg-black text-white' : 'hover:bg-gray-200'}`} href={menu.href}>
                            {menu.name}
                        </a>
                    </li>
                {/each}
        </div>
    </nav>
    <div class="flex-1 p-4">
        <nav class="flex justify-between items-center">
            <button class="flex items-center gap-3" on:click={toggleMenu}>
                <svg xmlns="http://www.w3.org/2000/svg" fill="white" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-7 bg-black rounded-md p-1 stroke-white">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
                </svg>                                 
                <h1 class="text-1xl font-bold">Dashboard</h1>
            </button>
            <div class="flex items-center gap-3 font-bold text-1xl">
                <span>¡Bienvenido John Doe!</span>
                <img class="rounded-full size-7" src="https://ntrepidcorp.com/wp-content/uploads/2016/06/team-1.jpg" alt="">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="size-4">
                    <path fillRule="evenodd" d="M4.22 6.22a.75.75 0 0 1 1.06 0L8 8.94l2.72-2.72a.75.75 0 1 1 1.06 1.06l-3.25 3.25a.75.75 0 0 1-1.06 0L4.22 7.28a.75.75 0 0 1 0-1.06Z" clipRule="evenodd" />
                </svg>                                 
            </div>
        </nav>
        <div class="flex-1">
            <slot />
        </div>
    </div>
</main>