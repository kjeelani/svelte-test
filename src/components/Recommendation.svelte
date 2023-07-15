<script lang="ts">
    interface Rec {
			title: string,
			channel: string,
			url: string,
            active: boolean
	}

	export let rec: Rec;
    export let setActive: (arg0: string) => void;
</script>


<style>
  .grid-item {
    padding: 20px;
    text-align: left;
  }
  p {
    color: rgb(101, 101, 101);
  }
  .rec-frame {
    border-color: rgba(255, 255, 255, 0);
    border-radius: 5%;
    border-width: .7px;
    padding: 1%;
    background-color: white;
    transition: ease-in-out .4s;
  }
  .rec-frame:hover {
    border-color: rgb(0, 0, 0);
    background-color: rgb(223, 255, 244);
  }
</style>


{#if !rec.active}
<div class="grid-item">
    <button on:click={() => setActive(rec.url)} class="rec-frame">
        <iframe 
            width="320" height="180" 
            src={`https://www.youtube.com/embed/${rec.url}`}
            title="YouTube video player" frameborder="0" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
            allowfullscreen>
        </iframe>
        <h3>{rec.title}</h3>
        <p>{rec.channel}</p>
    </button>
</div>
{:else}
<div>

</div>
{/if}
