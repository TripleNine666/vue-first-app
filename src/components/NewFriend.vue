<template>
  <form @submit.prevent="submitData">
    <div>
      <label>Имя</label>
      <input type="text" v-model="name" />
    </div>
    <div>
      <label>Телефон</label>
      <input type="tel" v-model="phone" />
    </div>
    <div>
      <label>Email</label>
      <input type="email" v-model="email" />
    </div>
    <div>
      <button>Добавить</button>
    </div>
  </form>
</template>

<script>
export default {
  emits: ["add-friend"],
  data() {
    return {
      id: "",
      name: "",
      phone: "",
      email: "",
    };
  },
  methods: {
    submitData() {
      this.$emit("add-friend", this.name, this.phone, this.email);
    },
  },
};
</script>
