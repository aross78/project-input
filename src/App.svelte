<script>
  import Counter from './lib/Counter.svelte'
  import Calendar from './lib/Calendar.svelte'

  let buffer = 1;

</script>

<head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@event-calendar/build@2.6.1/event-calendar.min.css">
  <script src="https://cdn.jsdelivr.net/npm/@event-calendar/build@2.6.1/event-calendar.min.js"></script>
</head>

<main>
 <h1> Time Scheduler</h1>
 <label> Preferred Buffer Time: </label>
 <label>
	<input type="radio" bind:group={buffer} value={0} />
	0 Minutes
</label>

<label>
	<input type="radio" bind:group={buffer} value={15} />
	15 Minutes
</label>

<label>
	<input type="radio" bind:group={buffer} value={30} />
	30 Minutes
</label>

  <Calendar />

  <div class="card">
    <Counter />
  </div>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">
    Hello World!
  </p>
</main>

<style>

  .read-the-docs {
    color: #888;
  }
</style>
