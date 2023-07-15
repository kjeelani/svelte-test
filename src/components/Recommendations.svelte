<script lang="ts">
	import Recommendation from "./Recommendation.svelte";
  
  interface Rec {
        title: string,
        channel: string,
        url: string
        active: boolean
	}

  export let recs: Rec[];
  export let setActive: (arg: string) => void
</script>


<style>
  .grid-container {
    width: 100%;
    display: flex;
    flex-direction: column;
    margin-bottom: 15px;
    margin-top: 15px;
  }
</style>


<div class="grid-container">
  {#each recs as rec}
    <Recommendation {setActive} {rec}/>
  {/each}
</div>