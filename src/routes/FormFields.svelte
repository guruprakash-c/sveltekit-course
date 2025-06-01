<script>
let today = (new Date()).getFullYear();
let dob = 0;
$: calculatedAge = (today - (new Date(dob)).getFullYear());
</script>

<input type="date" bind:value={dob} />
<p>You age is: {calculatedAge}</p>