<script>
    let links = [
        { name: 'Inicio', href: '/' },
        { name: 'Nuestro Software', href: '/' },
        { name: 'Contacto', href: '/' }
    ]
</script>

<nav class="bg-gray-200 shadow">
    <div class="max-w-7xl px-5 py-3 mx-auto text-lg flex justify-between">
        <a href="/"><img src="https://pngimg.com/d/parking_PNG36.png" alt="" class="transition-all w-5 h-auto hover:scale-105"></a>
        <ul class="flex gap-4 font-semibold">
            {#each links as link}
                <li>
                    <a href={link.href} class="transition-all hover:text-blue-800">{link.name}</a>
                </li> 
            {/each}
        </ul>
</nav>
<div class="max-w-7xl mx-auto px-5 py-3">
    <slot/>
</div>
<footer>

</footer>