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
<<<<<<< HEAD
=======
        slotMinTime: '08:00:00',
        slotMaxTime: '17:00:00',
       // allDay: false,
>>>>>>> 530eb85fa70cc52dd93bb650b401399805db7421
        selectable: true,
        select: (info) => {
            const newEvent = {
                start: info.start,
                end: info.end,
            };
            ec.addEvent(newEvent);
        },
        editable: true,
<<<<<<< HEAD
=======
        backgroundColor : '#278a27',
>>>>>>> 530eb85fa70cc52dd93bb650b401399805db7421
        events: events,
        select: function (info) {
            ec.addEvent(info);
            ec.unselect();



        },
    };
</script>

<Calendar bind:this={ec} {plugins} {options} />