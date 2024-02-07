<script>
    import Calendar from '@event-calendar/core';
    import TimeGrid from '@event-calendar/time-grid';

    let plugins = [TimeGrid];
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

<Calendar {plugins} {options} />