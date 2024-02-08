<script>
    import Calendar from '@event-calendar/core';
    import TimeGrid from '@event-calendar/time-grid';
    import Interaction from '@event-calendar/interaction'
    
    let ec;
    let plugins = [TimeGrid, Interaction];
    let events = [
        // initial list of events
    ];

    let options = {
        view: 'timeGridWeek',
        editable: true,
        selectable: true,
        select: (info) => {
            const newEvent = {
                start: info.start,
                end: info.end,
            };
            ec.addEvent(newEvent);
        },
        events: events,
    };
</script>

<Calendar bind:this={ec} {plugins} {options} />