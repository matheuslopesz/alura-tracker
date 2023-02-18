<template>
  <button class="button" @click="clicked" :disabled="disabled">
    <span class="icon">
      <i :class="icon"></i>
    </span>
    <span>{{text}}</span>
  </button>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "TaskButton",
  emits: ['clicked'],
  props: {
    disabled: {
      type: Boolean
    },
    icon: {
      type: String,
      required: true
    },
    text: {
      type: String,
      required: true
    },
  },
  methods: {
    clicked () {
      this.$emit('clicked')
    }
  }
});
</script>