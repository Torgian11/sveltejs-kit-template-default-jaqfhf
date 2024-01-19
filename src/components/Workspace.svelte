<script>
import Panel from "./Panel.svelte";
import PingPong from "./PingPong.svelte";

let ping = true;
function updatePing(){
  ping = !ping
}

function updateBackground(ev) {
  backgroundColor = ev.detail;
}
</script>

<div class="workspace">
  <div class="row">
    <Panel backgroundColor="#d1d322">
      <PingPong isPing={ping} on:ping-pong={updatePing}/>
    </Panel>
    <Panel backgroundColor="teal">
      <PingPong isPing={!ping} name="Pong"  on:ping-pong={updatePing}/>
    </Panel>
    <Panel useBackgroundInput />
  </div>
</div>

<style scoped>
.workspace {
  border: 2px dashed black;
  min-height: 200px;
  width: 400px;
}

.row {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin: 0.5rem;
}
</style>