<script>
//import FirstComponent from './FirstComponent.svelte';
//import FormFields from './FormFields.svelte';
//import Conditions from './Conditions.svelte';
//import ApiCall from './ApiCall.svelte';
import LifeCycle from './LifeCycle.svelte';
</script>
<!-- FirstComponent src={'https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExZzl0Ym11NWRoa3V2dWF6aTZmbWdzNXFuMWs3ejJtYW94YmN1NXA3aiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/VDMHgvx8N9U7UUlczQ/giphy.gif'} name={'running'}/ -->

<!-- FormFields / -->
<!-- Conditions / -->
<!-- ApiCall/ -->
<LifeCycle />

<style>
    body{
        background: linear-gradient(#eee, #000) !important; 
        background-size: 100% 100%;
    }
    :global(input),
    :global(select){
        background: #c0c0c0;
    }
    :global(h1){
        color: orange;
    }
</style>