<template>
  <div class="app">
    <h1>{{ jobs[0].id }}</h1>
    <p>
      They live in {{ jobs[0].location }}. Their bff is {{ jobs[1].id }}, who
      makes {{ jobs[1].salary }} per year
    </p>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from "vue";
import Job from "../components/types/Job.ts/Job";

export default defineComponent({
  nama: "App",
  components: {},
  setup() {
    // const state = reactive({
    //   name: "Link" as string,
    //   age: 25 as number | string,
    // });

    // state.name = "r-dog";

    // return {
    //   ...toRefs(state),
    // };
    // const name = ref<string>("Link");
    // const age = ref<number | string>(25);
    // // Or
    // // const name = ref("Link" as string);
    // // const age = ref(25 as number | string);

    // name.value = "René";
    // age.value = "25";

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
        location: "Cunky-Land",
        salary: 10000000000,
        id: "cmonkey",
      },
    ]);

    return { jobs };
  },
  methods: {},
});
</script>

<style lang="sass">
</style>
