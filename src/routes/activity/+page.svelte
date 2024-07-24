<script>
  import PocketBase from "pocketbase";
  import { dataBase } from "../../global";
  import DashboardLayout from "../../layouts/DashboardLayout.svelte";
  import { onMount } from "svelte";
  import Card from "../../components/Card.svelte";
  import Buttons from "../../components/Buttons.svelte";

  const pb = new PocketBase(dataBase);
  let resultList;

  onMount(async () => {
    await updateQuery();
    pb.collection("activity").subscribe("*", updateQuery);
  });

  async function updateQuery() {
    resultList = await pb.collection("activity").getList(1, 50);
  }
</script>

<DashboardLayout pageTitle="Actividad">
  {#if resultList}
    <div class="flex flex-col gap-4">
      <div class="flex flex-row gap-4">
        <Buttons onClick={updateQuery}>Registrar vehiculo</Buttons
        >
        <input
          type="text"
          placeholder="Buscar..."
          class="input input-bordered w-full max-w-xs"
        />
      </div>
      {#if resultList.items && resultList.items.length > 0}
        <div class="grid grid-cols-2 lg:grid-cols-4 gap-4">
          {#each resultList.items as item}
            <Card>
              <div class="text-center overflow-hidden">
                <h1 class="text-3xl font-bold tracking-tight">
                  {item.plate}
                </h1>
                <p class="text-muted-foreground">
                  {item.description}
                </p>
              </div>
            </Card>
          {/each}
        </div>
      {:else}
        <p>No hay resultados</p>
      {/if}
    </div>
  {:else}
    <p>Cargando...</p>
  {/if}
</DashboardLayout>
