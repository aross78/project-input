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
        slotMinTime: '08:00:00',
        slotMaxTime: '17:00:00',
       // allDay: false,
        selectable: true,
        select: (info) => {
            const newEvent = {
                start: info.start,
                end: info.end,
            };
            ec.addEvent(newEvent);
        },
        editable: true,
        backgroundColor : '#278a27',
        events: events,
        select: function (info) {
            ec.addEvent(info);
            ec.unselect();



        },
    };
</script>

<Calendar bind:this={ec} {plugins} {options} />