<script>
	import Schedule from './components/Schedule.svelte'
	import axios from 'axios'
	
	let channel
	axios.get("https://tmtv-schedule.herokuapp.com/").then((response) => {
		console.log(response.data.rss.channel[0].item[0 ])
		channel = response.data.rss.channel
	})
</script>

<main>
	{#if channel}
		<Schedule schedule={channel[0].item}/>
	{/if}
</main>

<style>
	main {
		text-align: left;
		padding: 1em;
		/* max-width: 240px; */
		margin: 0 auto;
	}
</style>