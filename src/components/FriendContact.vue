<template>
  <li>
    <h2>{{ name }} {{ isFavorite ? "(favorite)" : "" }}</h2>
    <button @click="toggleDetails">Show details</button>
    <button @click="toggleFavorite">Toggle favorite</button>
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone: {{ mobilePhone }}</strong>
      </li>
      <li>
        <strong>Email: {{ emailAdress }}</strong>
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  // props: ["name", "mobilePhone", "emailAdress", "isFavorite"],
  props: {
    id: {
      type: String,
      required: true,
    },
    name: String,
    mobilePhone: String,
    emailAdress: String,
    isFavorite: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
  emits: ["toggle-favorite"],
  // emits: {
  //   "toggle-favorite": function (id) {
  //     if (id) {
  //       return true;
  //     } else {
  //       console.warn("Id is missing!");
  //       return false;
  //     }
  //   },
  // },
  data() {
    return {
      detailsAreVisible: false,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit("toggle-favorite", this.id);
    },
  },
};
</script>
