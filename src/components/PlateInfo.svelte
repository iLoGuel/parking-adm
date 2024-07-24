<script>
  import Card from "./Card.svelte";
  import Modal from "./Modal.svelte";

  export let showModal = false;

  export let data;
</script>

<Modal bind:showModal>
    <Card>
      {data.plate}{showModal}
    </Card>
</Modal>
