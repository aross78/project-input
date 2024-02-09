<script>
  import Calendar from './lib/Calendar.svelte'
  import Output from './lib/Output.svelte'

  let buffer = 0;

</script>

<head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@event-calendar/build@2.6.1/event-calendar.min.css">
  <script src="https://cdn.jsdelivr.net/npm/@event-calendar/build@2.6.1/event-calendar.min.js"></script>
</head>

<main>
 <a href="https://github.com/aross78/project-input">
      <img src="src\assets\harvard_time_logo.png" class="logo" alt="Harvard Time Logo" />
 </a>             
 <h1>WhenNOTToMeet</h1>
 <div style = "width:45%; height: 30%; float:left;">
  <h2 style = "color:cadetblue;"> Input When You Are Busy</h2>
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

  </div>

  <div style= "float:right;">
    <h2 style = "color:cadetblue"> Group Availability</h2>
    <label> Buffer Time: {buffer}</label>
    <Output />
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
