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
        events: events,
        slotMinTime: '08:00:00',
        slotMaxTime: '17:00:00',
        editable: true,
        selectable: true,
        select: (info) => {
            ec.addEvent(info);
            ec.unselect();
        },
    };
</script>

<Calendar bind:this={ec} {plugins} {options} />