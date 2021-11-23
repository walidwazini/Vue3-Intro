<template>
  <section>
    <h2>My Friends</h2>
    <ul>
        <friend-contact></friend-contact>
        <friend-contact></friend-contact>
        <friend-contact></friend-contact>
    </ul>
  </section>
  
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: "manuel",
          name: "Manuel Lorenz",
          phone: "0123456789",
          email: "manuel@localhost.com",
        },
        {
          id: "altair",
          name: "Altair",
          phone: "0123456789",
          email: "altair@localhost.com",
        },
        {
          id: "luna",
          name: "Lunafreya",
          phone: "0123456789",
          email: "lunafreya@localhost.com",
        },
      ],
    };
  },
};
</script>