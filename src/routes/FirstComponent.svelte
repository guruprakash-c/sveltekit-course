<script>
export let src = 'https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExZzl0Ym11NWRoa3V2dWF6aTZmbWdzNXFuMWs3ejJtYW94YmN1NXA3aiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/VDMHgvx8N9U7UUlczQ/giphy.gif'; 
export let name = 'Run'; 
</script>
<h1>Svelte JS : Components & Bindings</h1>
<figure>
<img {src} alt={name} width="100"/>
<figcaption><a href="{src}" target="_blank">{name}</a></figcaption>
</figure>

<style>
    figure {
        max-width: 200px; 
        background: #eee;
        border-radius: 12px
    }
    figure img{
        max-width: 100%; 
    }
    figcaption a{
        color: blue;
        text-decoration: none; 
    }
</style>