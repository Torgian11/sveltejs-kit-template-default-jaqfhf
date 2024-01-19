<script>
import { createEventDispatcher } from 'svelte';

export let disabledBtn = false;
export let isPing = false;
export let name = "Ping"

const dispatch = createEventDispatcher();

function handlePingPong() {
  dispatch('ping-pong')
}

</script>

<button class="ping-pong" on:click="{handlePingPong}" disabled="{!isPing}">{name}</button>

<style scoped>
.ping-pong {
  font-size: 18px;
}
</style>