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
<p>{handleSelect}</p>