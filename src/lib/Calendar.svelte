<script>
    import Calendar from '@event-calendar/core';
    import TimeGrid from '@event-calendar/time-grid';
    import Interaction from '@event-calendar/interaction'

    export let buff = 0;
    
    let ec;
    let plugins = [TimeGrid, Interaction];
    let events = [
        // initial list of events
    ];

    let options = {
        allDaySlot: false,
        view: 'timeGridWeek',
        events: events,
        eventColor: '#942248',
        eventClick: (info) => {
            ec.removeEventById(info.event.id)
        },
        slotMinTime: '08:00:00',
        slotMaxTime: '17:00:00',
        editable: true,
        selectable: true,
        select: (info) => {
            let newEvent = info;
            newEvent.extendedProps = {
                buffer: buff,
            };
            newEvent.title = {html: '<b>Busy</b><br>Buffer:' + newEvent.extendedProps.buffer};
            newEvent.textColor = '#f0d1db';
            
            ec.addEvent(info);
            ec.unselect();
        },
    };
</script>

<Calendar bind:this={ec} {plugins} {options} />