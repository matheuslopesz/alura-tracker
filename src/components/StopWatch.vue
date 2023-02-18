<template>
  <section>
    <strong>{{ spentTime }}</strong>
  </section>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "StopWatch",
  props: {
    timeInSeconds: {
      type: Number,
      required: true,
    },
  },
  computed: {
    spentTime() {
      return new Date(this.timeInSeconds * 1000).toISOString().substr(11, 8);
    },
  },
});
</script>