<template>
  <li>
    <h2>{{ friend.name }}</h2>
    <button @click="toggleDetails">Show details</button>
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone: {{ friend.phone }}</strong>
      </li>
      <li>
        <strong>Email: {{ friend.email }}</strong>
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  data() {
    return {
      detailsAreVisible: false,
      friend: {
        id: "Stepa",
        name: "Степа Постухов",
        phone: "+375 (44) 123-45-67",
        email: "stepa@gmail.com ",
      },
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
  },
};
</script>
