<script>
  import Counter from './lib/Counter.svelte'
  import Calendar from './lib/Calendar.svelte'
  import Output from './lib/Output.svelte'

  let buffer = 1;

</script>

<head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@event-calendar/build@2.6.1/event-calendar.min.css">
  <script src="https://cdn.jsdelivr.net/npm/@event-calendar/build@2.6.1/event-calendar.min.js"></script>
</head>

<main>
 <h1> Time Scheduler</h1>
 <div style = "width:40%; height:30%; float:left;">
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

</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #6e1010);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
