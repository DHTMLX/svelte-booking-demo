<script>
    import { onMount, onDestroy } from "svelte";
    import { Booking } from "@dhx/trial-booking";
    import "@dhx/trial-booking/dist/booking.css";
    
    export let data;

    let container;
    let booking;

    onMount(() => {
        booking = new Booking(container, {
            data
        })

        booking.setConfirmHandler(function(event){
			const { confirm } = event;
			setTimeout(() => {
				Math.random() < 0.5 ? confirm.error() : confirm.done();
			}, 1000);
		})
    });
    
    onDestroy(() => {
        booking.destructor();
    });
</script>

<div bind:this={container} class="widget"></div>
