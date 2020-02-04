<template>
  <div class="columns">
    <div class="column has-text-centered">
      <strong>Notes</strong>
      <div v-for="note in notes" class="notes" v-bind:key="note">{{note}}</div>
    </div>
    <div class="column has-text-centered">
      <strong>Timestamp</strong>
      <div v-for="timestamp in timestamps" class="timestamps" v-bind:key="timestamp">{{timestamp}}</div>
    </div>
  </div>
</template>


<script>
export default {
  name: "notes",
  props:{
    notes:{
      type: Array,
      required: true
    },
    timestamps: {
      type: Array,
      required: true
    }
  }
};
</script>