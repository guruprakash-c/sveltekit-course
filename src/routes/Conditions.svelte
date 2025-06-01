<script>
let selectedOption = ''
$: handleSelect = ((selectedOption != '') ? 'You have selected: Option #'+ selectedOption : 'Choose an option');

let options = [
    {
        id: 1, text: 'Option #1'
    },
    {
        id: 2, text: 'Option #2'
    },
    {
        id: 3, text: 'Option #3'
    },
    {
        id: 4, text: 'Option #4'
    },
    {
        id: 5, text: 'Option #5'
    }
];
</script>

<select 
    bind:value={selectedOption} 
    on:change={handleSelect}
>
    <option value="">-- Select --</option>
    {#each options as option}
        <option value={option.id}>{option.text}</option>
    {/each}
</select>
{#if selectedOption > 3 && selectedOption <= 5 }
<p class="text-success">{handleSelect}</p>
{:else if selectedOption > 1 && selectedOption <= 3 }
<p class="text-info">{handleSelect}</p>
{:else} 
<p class="text-danger">{handleSelect}</p>
{/if}
<style>
.text-success{ color: green }
.text-info{ color: blue }
.text-danger{ color: red }
</style>