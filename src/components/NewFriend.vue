<template>
  <form @submit.prevent="addContact">
    <div><label>Name</label> <input v-model="inputName" type="text" /></div>
    <div><label>Phone</label> <input v-model="inputPhone" type="tel" /></div>
    <div><label>Email</label> <input v-model="inputEmail" type="email" /></div>

    <button>Add contact</button>
  </form>
</template>

<script>
export default {
  emits: ["add-contact"],
  data() {
    return {
      inputName: "",
      inputPhone: "",
      inputEmail: "",
    };
  },
  methods: {
    addContact() {
      this.$emit("add-contact", this.inputName, this.inputPhone, this.inputEmail);
      this.inputName = '';
      this.inputPhone = '';
      this.inputEmail = '';
    },
  },
};
</script>
