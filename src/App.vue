<template>
  <div id="app">
    <h1 class="title">Digital posit</h1>
    <p>Single page appliaction to take notes. Start by typing something in the input field. When you are ready press enter.</p>
    <div class="message is-info">
      <p class="message-body">Start by typing something in the input field. When you are ready press enter.</p>
    </div>
    <notes v-bind:notes="notes" v-bind:timestamps="timestamps"></notes>
    <input-component v-bind:placedata="placeholder" @newInput="addNote"></input-component>
  </div>
</template>

<script>
import inputComponent from "./components/input-component.vue";
import notes from "./components/notes.vue";

export default {
  name: "app",
  components: {
    inputComponent,
    notes
  },
  data() {
    return {
      notes: [],
      timestamps: [],
      placeholder: "Enter a note"
    };
  },
  computed: {},
  methods: {
    addNote(data) {
      this.notes.push(data.note);
      this.timestamps.push(data.timestamp);
    }
  }
};
</script>


<style lang="scss">
@import "bulma";
html,
body {
  height: 100%;
}

body {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

#app {
  width: 100%;
  max-width: 600px;
  max-height: 300px;
  height: 100%;
  margin: 0 auto;
}

p{
  margin-bottom: 20px;
}

.message-body{
  padding: 15px;
  margin-bottom: 50px;
}

</style>