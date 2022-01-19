<template>
	<div class="job-list">
		<p>Ordered by {{ order }}</p>
		<ul>
			<li v-for="job in orderedJobs	" :key="job.id">
				<h2>{{ job.id }} who is a {{ job.title }} in {{ job.location }}</h2>
				<div class="salary">
					<p>{{ job.salary }} rupees</p>
				</div>
				<div class="description">
					<p>
						Lorem ipsum dolor sit amet consectetur adipisicing elit.
						Exercitationem unde ex autem cumque odio, dicta nostrum eligendi
						amet non. Facilis modi mollitia adipisci velit beatae incidunt
						temporibus culpa error tenetur. Let's go!
					</p>
				</div>
			</li>
		</ul>
	</div>
</template>
<script lang="ts">
import { computed, defineComponent, PropType } from "vue";
import Job from "./types/Job.ts/Job";
import OrderTerm from "./types/OrderTerm";

export default defineComponent({
	props: {
		jobs: {
			required: true,
			type: Array as PropType<Job[]>,
		},
		order: {
			required: true,
			type: String as PropType<OrderTerm>,
		},
	},
	setup(props) {
		const orderedJobs = computed(() => {
			return [...props.jobs].sort((a: Job, b: Job) => {
				return a[props.order] > b[props.order] ? 1 : -1;
			});
		});
		return { orderedJobs };
	},
});
</script>
