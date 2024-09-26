<script>
  import { untrack } from "svelte";

    let value = $state('');

    let firstRun = $state(true);
    $effect(() => {
        console.log('effect')
        if (untrack(() => firstRun)) {
            firstRun = false;
            console.log("First run");
        } else {
            console.log("Not first run");
            console.log(value)
        }
    });
</script>

<p>{value}</p>
<input bind:value type="text" name="" id="">
