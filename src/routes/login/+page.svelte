<script>
  import PocketBase from "pocketbase";
  import { dataBase } from "../../global";
  import Card from "../../components/Card.svelte";
  import { onMount } from "svelte";

  const pb = new PocketBase(dataBase);
  let email, password, errorMessage;

  function login() {
    pb.collection("users")
      .authWithPassword(email, password)
      .then(() => {
        window.location.href = "/dashboard";
      })
      .catch(() => {
        errorMessage = "Credenciales incorrectas";
      });
  }
</script>

<main class="flex w-screen h-screen justify-center items-center">
  <Card>
    <div class="p-4 max-w-7xl">
      <div class="mx-auto w-full max-w-md space-y-8 rounded-2xl bg-card p-8">
        <div class="text-center">
          <h1 class="text-3xl font-bold tracking-tight">
            Bienvenido de vuelta
          </h1>
          <p class="text-muted-foreground">
            Inicia sesión en tu cuenta para continuar
          </p>
        </div>
        <form class="space-y-6 flex flex-col gap-1">
          <div>
            <label
              class="text-sm font-medium leading-none peer-disabled:cursor-not-allowed peer-disabled:opacity-70"
              for="email"
            >
              Correo electrónico
            </label>
            <input
              bind:value={email}
              class="flex h-10 w-full rounded-md border border-input bg-background px-3 py-2 text-sm ring-offset-background file:border-0 file:bg-transparent file:text-sm file:font-medium placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:cursor-not-allowed disabled:opacity-50"
              type="email"
              id="email"
              placeholder="name@example.com"
              required=""
            />
          </div>
          <div>
            <div class="flex items-center justify-between">
              <label
                class="text-sm font-medium leading-none peer-disabled:cursor-not-allowed peer-disabled:opacity-70"
                for="password"
              >
                Contraseña
              </label>
              <a
                class="text-sm font-medium underline underline-offset-4 hover:text-primary"
                href="/"
              >
                ¿Olvidaste tu contraseña?
              </a>
            </div>
            <input
              bind:value={password}
              class="flex h-10 w-full rounded-md border border-input bg-background px-3 py-2 text-sm ring-offset-background file:border-0 file:bg-transparent file:text-sm file:font-medium placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:cursor-not-allowed disabled:opacity-50"
              type="password"
              id="password"
              required=""
            />
          </div>
          {#if errorMessage}
            <p class="text-red-500">{errorMessage}</p>
          {/if}
          <div class="mt-4 flex items-center justify-between">
            <div class="text-sm">
              ¿No tienes cuenta aún? <a
                href="/"
                class="text-black font-bold underline"
              >
                Crea una
              </a>
            </div>
          </div>

          <button
            on:click={login}
            class="inline-flex items-center justify-center whitespace-nowrap rounded-md text-sm font-medium ring-offset-background focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 border border-input bg-background hover:bg-accent hover:text-accent-foreground h-10 px-4 py-2 hover:border-black hover:bg-black hover:text-white"
            type="submit"
          >
            Iniciar sesión
          </button>
        </form>
      </div>
    </div></Card
  >
</main>
