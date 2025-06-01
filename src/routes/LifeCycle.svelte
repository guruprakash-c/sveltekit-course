<script>
import { onMount, beforeUpdate, afterUpdate, onDestroy, tick } from 'svelte'; 

onMount(() => { 
 console.log('mounted');
});
beforeUpdate(() => { 
 console.log('beforeUpdate');
});
afterUpdate(() => { 
 console.log('afterUpdate');
});
onDestroy(() => { 
 console.log('onDestroy');
});
</script>
<h1>Svelte JS: Life Cycle</h1>
<button>Press <code>Ctrl + Shift + C</code></button>