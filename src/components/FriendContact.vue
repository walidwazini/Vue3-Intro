<template>
  <li>
    <!-- <h2>{{ name }} {{isFavourite == '1' ? '(Favourite)' : ''}} </h2> -->
    <h2>{{ name }} {{ isFavourite ? "(Favourite)" : "" }}</h2>
    <button @click="toggleFavourite">Toggle Favourite</button>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Hide" : "Show" }}
    </button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone: </strong> {{ phoneNumber }}</li>
      <li><strong>Email: </strong> {{ emailAddress }}</li>
    </ul>
    <button @click="$emit('delete', id)">Delete</button>
  </li>
</template>

<script>
export default {
  //  props: ["name", "phoneNumber", "emailAddress", "isFavourite"],
  props: {
    id: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: String,
      required: true,
    },
    emailAddress: {
      type: String,
      required: true,
    },
    isFavourite: {
      type: Boolean,
      required: false,
      default: false,
      // validator: function(value){
      //     return value === '1' || value === '0'
      // }
    },
  },
  emits: ["toggle-favourite", 'delete'],
  data() {
    return {
      detailsAreVisible: false,
      //   friend: {
      //     id: "manuel",
      //     name: "Manuel Lorenz",
      //     phone: "0123456789",
      //     email: "manuel@localhost.com",
      //   },
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavourite() {
      //this.friendIsFavourite = !this.friendIsFavourite
      this.$emit("toggle-favourite", this.id);
      console.log("Here");
    },
  },
};
</script>