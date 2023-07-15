<script lang="ts">
    import Recommendations from '../components/Recommendations.svelte'
    import MainVid from '../components/MainVid.svelte'

    interface Rec {
        title: string,
        channel: string,
        url: string
        active: boolean
	}

    const recs: Rec[] = [
        {
            "title": "Ressurections (Celeste Rock DnB Remix)",
            "channel": "Kaijen Music",
            "url": "E6XVIlK6YnA",
            "active": true
        },
        {
            "title": "Shunji (Minecraft DnB Remix)",
            "channel": "Kaijen Music",
            "url": "-wztVGJr2n0",
            "active": false
        },
        {
            "title": "My Burden is Light (Oneshot DnB Remix)",
            "channel": "Kaijen Music",
            "url": "8mvjqYz0G5A",
            "active": false
        },
        {
            "title": "Gallery (Deltarune Chapter 2 DnB Remix)",
            "channel": "Kaijen Music",
            "url": "qwBPaho8_rw",
            "active": false,
        }
    ]


    //Kinda struggled here, but I think I got it working
    $: all_vids = recs
    $: active = getActive()

    $: setActive = function setActive(id: string) {
        for (let rec of all_vids) {
            if (rec.url === id) {
                rec.active = true
                active = rec
            } else {
                rec.active = false
            }
        }
    }

    function getActive(): any {
        for (let rec of all_vids) {
            if (rec.active) {
                return rec
            }
        }
    }
</script>

<style>
    .app {
        display: flex;
    }
</style>


<div class="app">
    <MainVid {active}/>
    <Recommendations {setActive} {recs}/>
</div>
