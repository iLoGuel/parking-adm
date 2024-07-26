<script>
  let links = [
    { name: "Inicio", href: "/" },
    { name: "Caracteristicas", href: "#caracteristicas" },
    { name: "Contacto", href: "/" },
    { name: "Ingresar", href: "/login" },
  ];

  let openMenu = false;

  function toggleMenu() {
    openMenu = !openMenu;
  }
</script>

<header
  class="bg-primary text-primary-foreground px-4 lg:px-6 py-6 flex items-center justify-between sticky top-0 bg-white"
>
  <a class="flex items-center gap-2" href="/">
    <svg class="w-6 h-auto" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><!--!Font Awesome Free 6.6.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.--><path d="M135.2 117.4L109.1 192l293.8 0-26.1-74.6C372.3 104.6 360.2 96 346.6 96L165.4 96c-13.6 0-25.7 8.6-30.2 21.4zM39.6 196.8L74.8 96.3C88.3 57.8 124.6 32 165.4 32l181.2 0c40.8 0 77.1 25.8 90.6 64.3l35.2 100.5c23.2 9.6 39.6 32.5 39.6 59.2l0 144 0 48c0 17.7-14.3 32-32 32l-32 0c-17.7 0-32-14.3-32-32l0-48L96 400l0 48c0 17.7-14.3 32-32 32l-32 0c-17.7 0-32-14.3-32-32l0-48L0 256c0-26.7 16.4-49.6 39.6-59.2zM128 288a32 32 0 1 0 -64 0 32 32 0 1 0 64 0zm288 32a32 32 0 1 0 0-64 32 32 0 1 0 0 64z"/></svg>
    <span class="text-2xl font-bold">Parking Manager</span>
  </a>
  <button
    class={`${openMenu ? "opacity-50" : "opacity-0 pointer-events-none"} fixed bg-black w-screen h-screen top-0 right-0 lg:hidden `}
    on:click={toggleMenu}
  ></button>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
  <nav
    class={`${openMenu ? "" : "translate-x-full lg:translate-x-0"} fixed flex flex-col p-5 gap-4 w-7/12 h-screen top-0 right-0 bg-white lg:static lg:w-auto lg:h-auto lg:flex-row lg:right-0 lg:p-0`}
  >
    {#each links as link}
      <a class="text-lg font-medium hover:underline" href={link.href}
        >{link.name}</a
      >
    {/each}
  </nav>
  <button
    on:click={toggleMenu}
    class="inline-flex items-center justify-center whitespace-nowrap rounded-md text-sm font-medium ring-offset-background focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 border border-input bg-background hover:bg-accent hover:text-accent-foreground h-10 px-4 py-2 lg:hidden"
  >
    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="24"
      height="24"
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
      class="h-6 w-6"
    >
      <line x1="4" x2="20" y1="12" y2="12"></line>
      <line x1="4" x2="20" y1="6" y2="6"></line>
      <line x1="4" x2="20" y1="18" y2="18"></line>
    </svg>
    <span class="sr-only">Abrir menú</span>
  </button>
</header>
<div class="max-w-7xl mx-auto px-5 py-3">
  <slot />
</div>
<footer
  class="bg-muted text-muted-foreground px-4 md:px-6 py-6 flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between"
>
  <p class="text-sm text-center lg:text-start">© 2024 Parking Manager. Todos los derechos reservados.</p>
  <nav class="flex gap-4 sm:gap-6 justify-center lg:justify-start">
    <a class="text-sm hover:underline" href="/" rel="ugc">
      Términos de servicio
    </a>
    <a class="text-sm hover:underline" href="/" rel="ugc"> Privacidad </a>
  </nav>
</footer>
