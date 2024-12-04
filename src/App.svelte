<script>
	import Booking from "./Booking.svelte";
	import { getData } from "./data.js";

	const dataset = getData();
</script>

<Booking data={dataset} />
