<script>
  import PocketBase from "pocketbase";
  import { dataBase } from "../../global";
  import DashboardLayout from "../../layouts/DashboardLayout.svelte";
  import { onMount } from "svelte";
  import Card from "../../components/Card.svelte";

  const pb = new PocketBase(dataBase);
  let resultList;

  onMount(async () => {
    await updateQuery();
    pb.collection("activity").subscribe("*", updateQuery);
  });

  async function updateQuery() {
    return resultList = await pb.collection("activity").getList(1, 50);
  }
</script>

<DashboardLayout pageTitle="Actividad">
  {#if resultList}
    <div>
      <div class="grid grid-cols-2 lg:grid-cols-4 gap-4">
        {#each resultList.items as item}
          <Card>
            <div class="text-center">
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
    </div>
  {:else}
    <div class="text-center">
      <h1 class="text-3xl font-bold tracking-tight">
        Cargando...
      </h1>
    </div>
  {/if}
</DashboardLayout>
