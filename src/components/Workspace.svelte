<script>
import BackgroundInput from "./BackgroundInput.svelte";
import Panel from "./Panel.svelte";
import PingPong from "./PingPong.svelte";

let backgroundColor = "";
let ping = true;
function updatePing(){
  ping = !ping
}

function updateBackground(ev) {
  backgroundColor = ev.detail;
}
</script>

<div class="workspace">
  <Panel>
    <PingPong isPing={ping} on:ping-pong={updatePing}/>
  </Panel>
  <Panel backgroundColor="teal">
    <PingPong isPing={!ping} name="Pong"  on:ping-pong={updatePing}/>
  </Panel>
  <Panel useBackgroundInput />
</div>

<style scoped>
.workspace {
  border: 2px dashed black;
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  height: 200px;
  width: 400px;
}
</style>