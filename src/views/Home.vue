<template>
	<div class="app">
		<header class="btn-container">
			<button @click="handleClick('title')">Order by title</button>
			<button @click="handleClick('salary')">Order by salary</button>
			<button @click="handleClick('location')">Order by location</button>
		</header>
		<JobList :jobs="jobs" :order="order" />
	</div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref } from "vue";
import JobList from "../components/JobList.vue";
import Job from "../components/types/Job.ts/Job";
import OrderTerm from "../components/types/OrderTerm";

export default defineComponent({
	nama: "App",
	components: { JobList },
	setup() {
		const jobs = ref<Job[]>([
			{
				title: "developer",
				location: "Mars",
				salary: 5,
				id: " rtorres",
			},
			{
				title: "developer",
				location: "Mars",
				salary: 7,
				id: "phamer",
			},
			{
				title: "bed-warmer",
				location: "Chunky-Land",
				salary: 10000000000,
				id: "cmonkey",
			},
		]);
		const order = ref<OrderTerm>("title");
		const handleClick = (term: OrderTerm) => {
			order.value = term;
		};

		return { jobs, handleClick, order };
	},
	methods: {},
});
</script>

<style lang="sass"></style>
