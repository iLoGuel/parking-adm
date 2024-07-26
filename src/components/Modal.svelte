<script>
  import { fade } from "svelte/transition";
  export let showModal; // boolean
</script>

{#if showModal}
  <button
    class="fixed inset-0 bg-black bg-opacity-50 flex justify-center items-center cursor-default p-4 z-[1000]"
    on:click|self={() => showModal = false}
    transition:fade={{ duration: 150 }}
  >
    <dialog open class="bg-transparent">
      <slot />
    </dialog>
  </button>
{/if}
