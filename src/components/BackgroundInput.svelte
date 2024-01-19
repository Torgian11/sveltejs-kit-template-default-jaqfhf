<script>
import { createEventDispatcher } from 'svelte';

const dispatch = createEventDispatcher();

let updatedString = ""
function handleUpdate() {
  dispatch('update-background', updatedString)
}
</script>

<input class="color-input" type="text" bind:value="{updatedString}" on:input={handleUpdate}/>

<style scoped>
.color-input {
  font-size: 14px;
  height: 25px;
  max-width: 75px;
}
</style>