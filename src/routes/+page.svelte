<script>
    import HomeLayout from "../components/layouts/HomeLayout.svelte";
</script>

<HomeLayout>
    <section class="bg-primary text-primary-foreground py-12 md:py-24 lg:py-32">
        <div class="container px-4 md:px-6 grid gap-8 lg:grid-cols-2 lg:gap-16">
          <div class="space-y-4">
            <h1 class="text-4xl font-bold tracking-tight sm:text-5xl md:text-6xl">
              Transforma tu negocio con nuestra plataforma
            </h1>
            <p class="text-xl text-muted-foreground">
              Ofrecemos herramientas poderosas y fáciles de usar para impulsar tu éxito en línea.
            </p>
            <div class="flex gap-4">
              <button class="inline-flex items-center justify-center whitespace-nowrap rounded-md text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 h-10 px-4 py-2">
                Empezar
              </button>
              <a href="#caracteristicas" class="inline-flex items-center justify-center whitespace-nowrap rounded-md text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 border border-input bg-background hover:bg-accent hover:text-accent-foreground h-10 px-4 py-2">
                Más información
              </a>
            </div>
          </div>
          <img src="https://backend.vivendo.co/sites/default/files/styles/display_post/public/2020-03/parqueadero.png.jpg?itok=GvVfphSo" width="600" height="400" alt="Hero" class="mx-auto aspect-video overflow-hidden rounded-xl object-cover"
          />
        </div>
      </section>
      <section class="py-12 md:py-24 lg:py-32" id="caracteristicas">
        <div class="container px-4 md:px-6 space-y-8">
          <div class="text-center space-y-4" >
            <h2 class="text-3xl font-bold tracking-tight sm:text-4xl">Características destacadas</h2>
            <p class="max-w-[700px] mx-auto text-muted-foreground md:text-xl">
              Descubre cómo nuestra plataforma puede transformar tu negocio.
            </p>
          </div>
          <div class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
            <div class="bg-muted rounded-lg p-6 space-y-2">
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
                class="h-8 w-8 text-primary"
              >
                <path d="M4.5 16.5c-1.5 1.26-2 5-2 5s3.74-.5 5-2c.71-.84.7-2.13-.09-2.91a2.18 2.18 0 0 0-2.91-.09z"></path>
                <path d="m12 15-3-3a22 22 0 0 1 2-3.95A12.88 12.88 0 0 1 22 2c0 2.72-.78 7.5-6 11a22.35 22.35 0 0 1-4 2z"></path>
                <path d="M9 12H4s.55-3.03 2-4c1.62-1.08 5 0 5 0"></path>
                <path d="M12 15v5s3.03-.55 4-2c1.08-1.62 0-5 0-5"></path>
              </svg>
              <h3 class="text-xl font-bold">Lanzamiento rápido</h3>
              <p class="text-muted-foreground">
                Despliega tu aplicación en cuestión de minutos sin preocuparte por la infraestructura.
              </p>
            </div>
            <div class="bg-muted rounded-lg p-6 space-y-2">
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
                class="h-8 w-8 text-primary"
              >
                <path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"></path>
                <circle cx="12" cy="12" r="4"></circle>
              </svg>
              <h3 class="text-xl font-bold">Escalabilidad infinita</h3>
              <p class="text-muted-foreground">
                Nuestro servicio se adapta a tu crecimiento sin necesidad de configuración.
              </p>
            </div>
            <div class="bg-muted rounded-lg p-6 space-y-2">
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
                class="h-8 w-8 text-primary"
              >
                <rect width="16" height="16" x="4" y="4" rx="2"></rect>
                <rect width="6" height="6" x="9" y="9" rx="1"></rect>
                <path d="M15 2v2"></path>
                <path d="M15 20v2"></path>
                <path d="M2 15h2"></path>
                <path d="M2 9h2"></path>
                <path d="M20 15h2"></path>
                <path d="M20 9h2"></path>
                <path d="M9 2v2"></path>
                <path d="M9 20v2"></path>
              </svg>
              <h3 class="text-xl font-bold">Análisis en tiempo real</h3>
              <p class="text-muted-foreground">Obtén métricas detalladas sobre el rendimiento de tu aplicación.</p>
            </div>
            <div class="bg-muted rounded-lg p-6 space-y-2">
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
                class="h-8 w-8 text-primary"
              >
                <path d="m12.83 2.18a2 2 0 0 0-1.66 0L2.6 6.08a1 1 0 0 0 0 1.83l8.58 3.91a2 2 0 0 0 1.66 0l8.58-3.9a1 1 0 0 0 0-1.83Z"></path>
                <path d="m22 17.65-9.17 4.16a2 2 0 0 1-1.66 0L2 17.65"></path>
                <path d="m22 12.65-9.17 4.16a2 2 0 0 1-1.66 0L2 12.65"></path>
              </svg>
              <h3 class="text-xl font-bold">Personalización avanzada</h3>
              <p class="text-muted-foreground">Entrega contenido dinámico y personalizado a tus usuarios.</p>
            </div>
            <div class="bg-muted rounded-lg p-6 space-y-2">
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
                class="h-8 w-8 text-primary"
              >
                <path d="M20 13c0 5-3.5 7.5-7.66 8.95a1 1 0 0 1-.67-.01C7.5 20.5 4 18 4 13V6a1 1 0 0 1 1-1c2 0 4.5-1.2 6.24-2.72a1.17 1.17 0 0 1 1.52 0C14.51 3.81 17 5 19 5a1 1 0 0 1 1 1z"></path>
              </svg>
              <h3 class="text-xl font-bold">Seguridad de primera</h3>
              <p class="text-muted-foreground">Protege tus datos con nuestras funciones de seguridad avanzadas.</p>
            </div>
            <div class="bg-muted rounded-lg p-6 space-y-2">
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
                class="h-8 w-8 text-primary"
              >
                <path d="M16 20V4a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v16"></path>
                <rect width="20" height="14" x="2" y="6" rx="2"></rect>
              </svg>
              <h3 class="text-xl font-bold">Colaboración integrada</h3>
              <p class="text-muted-foreground">
                Facilita el trabajo en equipo con herramientas de revisión de código.erramientas de revisión de
              </p>
            </div>
          </div>
        </div>
      </section>
      <section class="bg-muted py-12 md:py-24 lg:py-32">
        <div class="container px-4 md:px-6 space-y-8">
          <div class="text-center space-y-4">
            <h2 class="text-3xl font-bold tracking-tight sm:text-4xl">Lo que dicen nuestros clientes</h2>
            <p class="max-w-[700px] mx-auto text-muted-foreground md:text-xl">
              Escucha las historias de éxito de empresas que han confiado en nuestra plataforma.
            </p>
          </div>
          <div class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
            <div
              class="rounded-lg border text-card-foreground shadow-sm bg-background p-6 space-y-4"
              data-v0-t="card"
            >
              <div class="flex items-center gap-4">
                <img
                  src="https://media.istockphoto.com/id/1386479313/photo/happy-millennial-afro-american-business-woman-posing-isolated-on-white.jpg?s=612x612&w=0&k=20&c=8ssXDNTp1XAPan8Bg6mJRwG7EXHshFO5o0v9SIj96nY="
                  width="48"
                  height="48"
                  alt="Avatar"
                  class="rounded-full"
                  style="aspect-ratio: 48 / 48; object-fit: cover;"
                />
                <div>
                  <h4 class="font-bold">John Doe</h4>
                  <p class="text-muted-foreground">CEO, Acme Inc</p>
                </div>
              </div>
              <p class="text-muted-foreground">
                "La plataforma de Acme Inc ha sido un verdadero\n transformador para nuestro negocio. Nos ha
                permitido\n lanzar nuevas funcionalidades de manera rápida y eficiente." un verdadero transformador
                para nuestro negocio. Nos ha permitido
              </p>
            </div>
            <div
              class="rounded-lg border text-card-foreground shadow-sm bg-background p-6 space-y-4"
              data-v0-t="card"
            >
              <div class="flex items-center gap-4">
                <img
                  src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRij6dtiHizH96qpCOe8WeXXP3yLyQJkPdGVg&s"
                  width="48"
                  height="48"
                  alt="Avatar"
                  class="rounded-full"
                  style="aspect-ratio: 48 / 48; object-fit: cover;"
                />
                <div>
                  <h4 class="font-bold">Jane Smith</h4>
                  <p class="text-muted-foreground">CTO, Globex Inc</p>
                </div>
              </div>
              <p class="text-muted-foreground">
                "Hemos estado utilizando la plataforma de Acme Inc durante\n más de un año y no podríamos estar más
                satisfechos. La\n escalabilidad y las funciones de análisis han sido\n invaluables para nuestro
                negocio."cme Inc durante más de un año y no podríamos estar más satisfechos. La escalabilidad y las
                funciones de análisis han sido
              </p>
            </div>
            <div
              class="rounded-lg border text-card-foreground shadow-sm bg-background p-6 space-y-4"
              data-v0-t="card"
            >
              <div class="flex items-center gap-4">
                <img
                  src="https://t4.ftcdn.net/jpg/03/64/21/11/360_F_364211147_1qgLVxv1Tcq0Ohz3FawUfrtONzz8nq3e.jpg"
                  width="48"
                  height="48"
                  alt="Avatar"
                  class="rounded-full"
                  style="aspect-ratio: 48 / 48; object-fit: cover;"
                />
                <div>
                  <h4 class="font-bold">Michael Johnson</h4>
                  <p class="text-muted-foreground">Founder, Stark Industries</p>
                </div>
              </div>
              <p class="text-muted-foreground">
                "La plataforma de Acme Inc ha sido un verdadero juego\n cambiante para nosotros. Nos ha permitido
                centrarnos en\n nuestro negocio sin preocuparnos por la infraestructura."erdadero juego
              </p>
            </div>
          </div>
        </div>
      </section>
</HomeLayout>