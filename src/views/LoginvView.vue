<template>
  <v-container fluid fill-height class="my-auto d-flex flex h-100">
    <v-row align="center" justify="center" no-gutters class="my-auto">
      <v-col cols="12" sm="6" md="6" class="my-auto d-sm-flex">
        <v-container fill-height class="d-flex align-center my-auto">
          <v-row align="center" justify="center">
            <v-col cols="12" class="text-center">
              <h1 class="display-2 font-weight-bold mb-4">
                Welcome to Our App
              </h1>
              <p class="subheading">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed
                euismod, nisl vel tincidunt lacinia, nisl nisl aliquam nisl, eu
                aliquam nisl nisl eu nisl.
              </p>
            </v-col>
            <v-col class="">
              <v-img src="../assets/spherewave.gif" height="550px" />
            </v-col>
          </v-row>
        </v-container>
      </v-col>
      <v-col cols="12" sm="6" md="6" class="px-16">
        <v-card class="elevation-12">
          <v-toolbar class="gradient" flat>
            <v-toolbar-title>Start For Free</v-toolbar-title>
          </v-toolbar>
          <v-card-text class="pa-12">
            <v-form ref="form" lazy-validation>
              <v-text-field
                v-model="email"
                label="Email"
                type="email"
                required
                :rules="emailRules"
                class="mb-4"
              >
                <template v-slot:prepend-inner>
                  <v-icon>mdi-email</v-icon>
                </template>
              </v-text-field>
              <v-text-field
                v-model="password"
                label="Password"
                type="password"
                required
                :rules="passwordRules"
                class="mb-4"
              >
                <template v-slot:prepend-inner>
                  <v-icon>mdi-lock</v-icon>
                </template>
              </v-text-field>
              <v-checkbox v-model="rememberMe" label="Remember me" />
              <v-btn text small @click="forgotPassword" class="gradient mt-4"
                >Forgot Password?</v-btn
              >
            </v-form>
          </v-card-text>
          <v-card-actions class="pb-8">
            <v-spacer />
            <v-btn class="gradient" @click="login" block>Login</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      rememberMe: false,
      emailRules: [
        (v) => !!v || "Email is required",
        (v) => /.+@.+\..+/.test(v) || "Email must be valid",
      ],
      passwordRules: [(v) => !!v || "Password is required"],
    };
  },
  methods: {
    forgotPassword() {
      console.log("Forgot password button clicked!");
    },
    login() {
      console.log("Login button clicked!");
    },
  },
};
</script>

<style scoped>
.v-card {
  border-radius: 10px !important;
}

.v-toolbar {
  border-radius: 10px 10px 0 0 !important;
}

.v-card__text {
  padding: 0 !important;
}

.v-input {
  margin-bottom: 10px !important;
}

.v-input__slot {
  border: 1px solid #ddd !important;
  border-radius: 5px !important;
}

.v-label {
  color: #666 !important;
}

.v-btn {
  text-transform: capitalize !important;
}

.v-btn--text {
  color: #007bff !important;
}

.v-btn--text:hover {
  text-decoration: underline !important;
}

.v-checkbox {
  margin-top: 10px !important;
}

.v-card__actions {
  padding: 10px !important;
  border-top: 1px solid #ddd !important;
}

.v-icon {
  font-size: 1.5rem !important;
}

@media (max-width: 960px) {
  .d-none {
    display: none;
  }
}

.gradient {
  font-size: 14px;
  padding: 6px 16px;
  font-weight: 400;
  border: none;
  outline: none;
  color: #000;
  background: linear-gradient(
    65deg,
    #999 5%,
    #fff 10%,
    #ccc 30%,
    #ddd 50%,
    #ccc 70%,
    #fff 80%,
    #999 95%
  );
  text-shadow: 1px 1px 2px rgba(255, 255, 255, 0.5);
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
  cursor: pointer;
  transition: all 0.2s ease-in-out;
}

.gradient:hover {
  transform: translateY(-2px);
}
</style>
