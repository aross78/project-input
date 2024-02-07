<script>
    import Calendar from '@event-calendar/core';
    import TimeGrid from '@event-calendar/time-grid';
    import Interaction from '@event-calendar/interaction'

    function add_buffer(e, incr){

    }

    

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

    function handleDrag(new_e){
        options.events = [... options.events, new_e];
    }

</script>

<Calendar {plugins} {options} />