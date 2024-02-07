<script>
    import Calendar from '@event-calendar/core';
    import TimeGrid from '@event-calendar/time-grid';
    import Interaction from '@event-calendar/interaction'

    let plugins = [TimeGrid, Interaction];
    let options = {
        view: 'timeGridWeek',
        selectable: 'true',
        events: [
            // your list of events
        ]
    };

    function updateOptions() {
        options.slotDuration = '01:00';
    }
</script>

<button on:click={updateOptions}>Change slot duration</button>
<Calendar {plugins} {options} />