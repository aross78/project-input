<script>
    import Calendar from '@event-calendar/core';
    import TimeGrid from '@event-calendar/time-grid';
   // import Calendar from './Calendar.svelte';

    let plugins = [TimeGrid];
    export let events = [
        // initial list of events
    ];

    let options = {
        allDaySlot: false,
        view: 'timeGridWeek',
        events: events,
        eventBackgroundColor: '#01010',
        slotMinTime: '08:00:00',
        slotMaxTime: '17:00:00',
        editable: false,
        selectable: false,
    };

    function updateOptions() {
        options.slotDuration = '01:00';
    }
</script>

<Calendar {plugins} {options} />