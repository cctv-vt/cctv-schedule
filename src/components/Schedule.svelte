<script>
import { each } from "svelte/internal";


   export let schedule
</script>

<main>
    <div>
        <!-- <h3>{title}</h3> -->
        {#each schedule as scheduleItem, index}
        <div>
            <p><strong>{scheduleItem.comments}</strong> {#if scheduleItem.psg_attribute && scheduleItem.psg_attribute[1]} <a href={scheduleItem.psg_attribute[1]._}>{scheduleItem.title}</a>{:else}{scheduleItem.title}{/if}</p>
        </div>
        {/each}
    </div>
</main>