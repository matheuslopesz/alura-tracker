<template>
  <div class="box has-text-weight-bold">
    <slot></slot>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "TaskBox",
  components: {},
  props: {},
});
</script>
