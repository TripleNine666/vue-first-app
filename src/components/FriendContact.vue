<template>
  <li>
    <h2>{{ name }} {{ isFavoriteFriend === "1" ? "(favorite)" : "" }}</h2>
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
  props: ["name", "mobilePhone", "emailAdress", "isFavorite"],
  data() {
    return {
      detailsAreVisible: false,
      friend: {
        id: "Stepa",
        name: "Степа Постухов",
        phone: "+375 (44) 123-45-67",
        email: "stepa@gmail.com ",
      },
      isFavoriteFriend: this.isFavorite,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      if (this.isFavoriteFriend === "1") {
        this.isFavoriteFriend = "0";
      } else {
        this.isFavoriteFriend = "1";
      }
    },
  },
};
</script>
