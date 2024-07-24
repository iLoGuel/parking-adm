<script>
  import PocketBase from "pocketbase";
  import { dataBase } from "../../global";
  import DashboardLayout from "../../layouts/DashboardLayout.svelte";
  import { onMount } from "svelte";
  import Buttons from "../../components/Buttons.svelte";
  import Modal from "../../components/Modal.svelte";
  import Card from "./../../components/Card.svelte";

  const pb = new PocketBase(dataBase);
  let resultList;
  let showModal = false;
  let plateInfo = null;

  onMount(async () => {
    await updateQuery();
    pb.collection("plates").subscribe("*", updateQuery);
  });

  async function updateQuery() {
    resultList = await pb.collection("plates").getList(1, 50);
  }

  function showCardModal(item) {
    showModal = !showModal;
    plateInfo = item;
  }
  function closeModal() {
    showModal = false;
  }
</script>

<DashboardLayout pageTitle="Actividad">
  {#if resultList}
    <div class="flex flex-col gap-4">
      <div class="flex flex-row gap-4">
        <Buttons onClick={updateQuery}>Registrar vehiculo</Buttons>
      </div>
      {#if resultList.items && resultList.items.length > 0}
        <div class="grid grid-cols-2 lg:grid-cols-4 gap-4">
          {#each resultList.items as item}
            <button on:click={showCardModal(item)}>
              <Card>
                <div class="text-center overflow-hidden">
                  <h1 class="text-3xl font-bold tracking-tight">
                    {item.name}
                  </h1>
                  <p class="text-muted-foreground">
                    {item.description}
                  </p>
                </div>
              </Card>
            </button>
          {/each}
          <Modal bind:showModal>
            <Card>
              <div class="p-4 flex flex-col gap-4 w-96">
                <h1 class="text-2xl font-bold tracking-tight text-start">
                  Información adicional
                </h1>
                <hr />
                <p class="text-start">Placa: {plateInfo.name}</p>
                <Buttons
                  onClick={() => {
                    showModal = !showModal;
                  }}>Cerrar</Buttons
                >
              </div>
            </Card>
          </Modal>
        </div>
      {:else}
        <p>No hay resultados</p>
      {/if}
    </div>
  {:else}
    <p>Cargando...</p>
  {/if}
</DashboardLayout>
