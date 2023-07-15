<script lang="ts">
	import Rec from "./Recommendation.svelte";

    export let active: Rec;
</script>

<style>
    .search-container {
        display: flex;
        align-items: center;
        width: 1080px;
        border: 1px solid #ccc;
        border-radius: 4px;
        overflow: hidden;
        margin-bottom: 1%;
    }

    input[type="text"] {
        flex-grow: 1;
        padding: 8px;
        border: none;
        outline: none;
    }

    button[type="submit"] {
        background-color: rgb(103, 177, 196);
        color: #fff;
        padding: 8px 12px;
        border: none;
        cursor: pointer;
        font-weight: bold;
    }

    button[type="submit"]:hover {
        background-color: rgb(55, 124, 141);
        transition: ease-in-out .2s;
    }
</style>


<div>
    <div class="search-container">
        <input type="text" placeholder="Search YouTube">
        <button type="submit">Search</button>
    </div>
    <iframe 
        width="1080" height="560" 
        src={`https://www.youtube.com/embed/${active.url}`}
        title="YouTube video player" frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
        allowfullscreen>
    </iframe>
    <h1>{active.title}</h1>
</div>