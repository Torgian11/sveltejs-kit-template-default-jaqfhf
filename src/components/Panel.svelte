<script>
import { createEventDispatcher } from 'svelte';
import BackgroundInput from './BackgroundInput.svelte';

const dispatch = createEventDispatcher();

export let useBackgroundInput = false;

export let backgroundColor = ""

function updateBackground(ev) {
  backgroundColor = ev.detail
}

</script>

<div class="panel" style="background:{backgroundColor};">
  <slot>
  </slot>
  {#if useBackgroundInput}
    <BackgroundInput on:update-background={updateBackground} />
  {/if}
  
</div>

<style scoped>
.panel {
  background-color: cornflowerblue;
  border: solid black 2px;
  display: flex;
  height: 100px;
  justify-content: center;
  width: 100px;
  align-items: center;
}
</style>