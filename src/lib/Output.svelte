<script>
    import Calendar from '@event-calendar/core';
    import TimeGrid from '@event-calendar/time-grid';

    let ec;
    let plugins = [TimeGrid];
    let events = [
        // initial list of events
    ];

    let options = {
        allDaySlot: false,
        view: 'timeGridWeek',
        events: events,
        slotMinTime: '08:00:00',
        slotMaxTime: '17:00:00',
        editable: false,
        selectable: false,
    };

    function updateOptions() {
        options.slotDuration = '01:00';
    }
</script>

<style>
    .ec {
        --ec-bg-fallback-color: green;
    }
</style>

<Calendar {plugins} {options} />