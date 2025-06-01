<script lang="ts">
import { fade, fly, slide, crossfade } from 'svelte/transition';
import { flip } from 'svelte/animate';
import FirstComponent from './FirstComponent.svelte';
let src:string = '';
let name:string = '';

let cats:{src:string,name:string}[] = [];

let apiUrl = 'https://api.thecatapi.com/v1/images/search?size=med&mime_types=jpg&format=json&has_breeds=false&order=RANDOM&page=0&limit=5'; 
const headers = new Headers({
    "Content-Type": "application/json",
});
const requestOptions = {
    method: 'GET',
    headers: headers
};
const getCats = async () => {
    let resp = await fetch(apiUrl, requestOptions); 
    const respJson = await resp.json(); 
    return respJson.map((c:any) => {
        return { src: c.url, name: c.id }
    })
}
const selectedCats = (s:string,n:string) => {
    debugger;
    src = s; 
    name = n;
}
</script>
<h1>Svelte JS : API Call</h1>
<div in:slide class="buttons">
    {#await getCats() }
    <div class="loader"/>
    {:then cats }
    {#each cats as {src, name}, i}
    <button  
        on:click={() => selectedCats(src, name)}>🐈 -  Cat #{i}</button>
    {/each}
    {:catch error}
    <p class="error">{error}</p>
    {/await}
</div>
{#key src}
<div in:fade={{ duration: 2000 }} out:fade>
<FirstComponent {src} {name}/>
</div>
{/key}
<style>
.buttons{
    display: flex; 
    flex-direction: columns;
    gap: .9rem
}
.loader {
  border: 16px solid #f1f1f1;
  border-top: 16px solid orange; 
  border-radius: 50%;
  width: 32px;
  height: 32px;
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
.error{ color: red }
</style>