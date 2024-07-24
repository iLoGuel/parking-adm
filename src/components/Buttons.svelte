<script>
  export let type = null;
  export let onClick;

  let typeMap = {
    primary: "bg-black text-white border-transparent",
  };

  let buttonClass = `rounded px-5 py-2 text-semibold border ${typeMap[type] || typeMap.primary}`;
</script>

<button class={buttonClass} on:click={onClick}><slot /></button>
