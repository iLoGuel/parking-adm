<script>
  import DashboardLayout from "../../layouts/DashboardLayout.svelte";
  import Card from "../../components/Card.svelte";
</script>

<DashboardLayout pageTitle="Actividad">
  <div>
    <div class="grid grid-cols-2 lg:grid-cols-4 gap-4">
      <Card>
        <div
          class="space-y-1.5 p-6 flex flex-row items-center justify-between pb-2"
        >
          <h3 class="whitespace-nowrap tracking-tight text-sm font-medium">
            Total Vehicles
          </h3>
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
            class="w-4 h-4 text-muted-foreground"
          >
            <path
              d="M19 17h2c.6 0 1-.4 1-1v-3c0-.9-.7-1.7-1.5-1.9C18.7 10.6 16 10 16 10s-1.3-1.4-2.2-2.3c-.5-.4-1.1-.7-1.8-.7H5c-.6 0-1.1.4-1.4.9l-1.4 2.9A3.7 3.7 0 0 0 2 12v4c0 .6.4 1 1 1h2"
            ></path>
            <circle cx="7" cy="17" r="2"></circle>
            <path d="M9 17h6"></path>
            <circle cx="17" cy="17" r="2"></circle>
          </svg>
        </div>
        <div class="p-6">
          <div class="text-2xl font-bold">4</div>
        </div>
      </Card>
    </div>
  </div>
</DashboardLayout>
