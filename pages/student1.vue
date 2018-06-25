<template>
<body>
  <h3 align="center"><div><h1>LOGIN</h1>
    <v-form v-model="valid">
      <v-text-field
        v-model="name"
        :rules="nameRules"
        :counter="10"
        label="Name"
        required
      />
      <v-text-field
        v-model="email"
        :rules="emailRules"
        label="E-mail"
        required
      />
    </v-form>
    <v-btn color="red lighten-1" dark>Accept
      <v-icon dark right>check_circle</v-icon>
    </v-btn>
    <v-btn dark>
      <v-icon dark left>remove_circle</v-icon>Cancel
    </v-btn>

  </div
  ></h3>
</body>
</template>

<script>
export default {
  data() {
    return {
      id: 1,
      valid: false,
      name: "",
      nameRules: [
        v => !!v || "Name is required",
        v => v.length <= 10 || "Name must be less than 10 characters"
      ],
      email: "",
      emailRules: [
        v => !!v || "E-mail is required",
        v =>
          /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) ||
          "E-mail must be valid"
      ]
    };
  }
};
</script>