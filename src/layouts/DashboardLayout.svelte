<script>
  import PocketBase from "pocketbase";
  import { page } from "$app/stores";
  import { onMount } from "svelte";
  import { appName, dataBase } from "../global";
  let dashboardMenu = [
    { name: "Dashboard", href: "/dashboard", icon: null },
    { name: "Actividad", href: "/activity", icon: null },
    { name: "Mensualidad", href: null, icon: null },
    { name: "Clientes", href: null, icon: null },
    { name: "Reportes", href: null, icon: null },
    { name: "Configuración", href: null, icon: null },
    { name: "Ayuda", href: null, icon: null },
  ];
  const pb = new PocketBase(dataBase);
  export let pageTitle;

  let openMenu;
  onMount(() => {
    openMenu = window.innerWidth > 1024;
    if (!pb.authStore.isValid) {
      window.location.href = "/login";
    }
  });

  function toggleMenu() {
    openMenu = !openMenu;
  }

  function logout() {
    pb.authStore.clear();
    window.location.href = "/";
  }
</script>

<svelte:head>
  <title>{appName} - {pageTitle}</title>
</svelte:head>
{#if pb.authStore.isValid}
  <main class="flex flex-row">
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div
      class={`fixed lg:static inset-0  z-10 navDashboard ${openMenu ? "active" : "pointer-events-none"}`}
      on:click|self={toggleMenu}
    >
      <nav
        class={`h-screen overflow-y-auto w-72 bg-gray-100 shadow flex flex-col p-4 fixed lg:static z-50 ${openMenu ? "" : "-translate-x-full lg:absolute"}`}
      >
        <a class="flex items-center gap-2 self-center" href="/">
          <svg
            class="w-6 h-auto"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 512 512"
            ><!--!Font Awesome Free 6.6.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.--><path
              d="M135.2 117.4L109.1 192l293.8 0-26.1-74.6C372.3 104.6 360.2 96 346.6 96L165.4 96c-13.6 0-25.7 8.6-30.2 21.4zM39.6 196.8L74.8 96.3C88.3 57.8 124.6 32 165.4 32l181.2 0c40.8 0 77.1 25.8 90.6 64.3l35.2 100.5c23.2 9.6 39.6 32.5 39.6 59.2l0 144 0 48c0 17.7-14.3 32-32 32l-32 0c-17.7 0-32-14.3-32-32l0-48L96 400l0 48c0 17.7-14.3 32-32 32l-32 0c-17.7 0-32-14.3-32-32l0-48L0 256c0-26.7 16.4-49.6 39.6-59.2zM128 288a32 32 0 1 0 -64 0 32 32 0 1 0 64 0zm288 32a32 32 0 1 0 0-64 32 32 0 1 0 0 64z"
            /></svg
          >
          <span class="text-2xl font-bold">Parking Manager</span>
        </a>
        <span class="font-semibold text-gray-400 text-sm self-center"
          >v0.0.1</span
        >
        <div class="flex-1 mt-4">
          <hr />
          <ul class="pt-2">
            {#each dashboardMenu as menu}
              <li>
                <a
                  class={`block text-lg py-2 px-4 rounded border-l-4 border-transparent hover:border-black mt-2 ${$page.url.pathname === menu.href ? "font-bold bg-black text-white" : "hover:bg-gray-200"}`}
                  href={menu.href}
                >
                  {menu.name}
                </a>
              </li>
            {/each}
          </ul>
        </div>
        <div class="flex items-center justify-between gap-3 font-bold mb-6">
          <div class="flex items-center gap-2">
            <img
              class="rounded-full size-10"
              src="https://ntrepidcorp.com/wp-content/uploads/2016/06/team-1.jpg"
              alt=""
            />
            <div class="flex flex-col overflow-hidden text-nowrap">
              <!-- nombre del usuario logeado -->
              <span class="text-sm">{pb.authStore.model.name}</span>
              <span class="text-xs font-normal">{pb.authStore.model.email}</span
              >
            </div>
          </div>
          <button on:click={logout}>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="size-6 stroke-red-500"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M8.25 9V5.25A2.25 2.25 0 0 1 10.5 3h6a2.25 2.25 0 0 1 2.25 2.25v13.5A2.25 2.25 0 0 1 16.5 21h-6a2.25 2.25 0 0 1-2.25-2.25V15m-3 0-3-3m0 0 3-3m-3 3H15"
              />
            </svg>
          </button>
        </div>
        <hr />
        <p class="text-xs text-center text-gray-400 mt-3">
          Todos los derechos reservados &copy; 2024
        </p>
      </nav>
    </div>
    <div class="flex-1 flex flex-col p-4 gap-4">
      <nav class="flex justify-between items-center sticky top-0 py-4 bg-white">
        <button class="flex items-center gap-3" on:click={toggleMenu}>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="white"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="size-7 bg-black rounded-md p-1 stroke-white"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
            />
          </svg>
          <h1 class="text-2xl font-bold">{pageTitle}</h1>
        </button>
        <button>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            strokeWidth={1.5}
            stroke="currentColor"
            class="size-7"
          >
            <path
              strokeLinecap="round"
              strokeLinejoin="round"
              d="M9.879 7.519c1.171-1.025 3.071-1.025 4.242 0 1.172 1.025 1.172 2.687 0 3.712-.203.179-.43.326-.67.442-.745.361-1.45.999-1.45 1.827v.75M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Zm-9 5.25h.008v.008H12v-.008Z"
            />
          </svg>
        </button>
      </nav>
      <slot />
    </div>
  </main>
{/if}

<style scoped>
  @media (max-width: 1024px) {
    .navDashboard {
      background-color: transparent;
    }

    .navDashboard.active {
      background-color: rgba(0, 0, 0, 0.5);
    }
  }
</style>
