<template>
  <v-app>
    <v-content>
      <div class="register-wrapper">
        <v-container class="fill-height login-container">
          <v-row align="center" justify="center" class="login-area">
            <!-- Register Form -->
            <v-col cols="12" sm="12" md="6" class="login-area__left">
              <div class="login-form__wrapper">
                <h4>Welcome to Criarme</h4>
                <v-form
                  ref="form"
                  v-model="valid"
                  lazy-validation
                  class="login-form"
                >
                  <v-text-field
                    class="custom-text-field"
                    v-model="name"
                    :rules="[rules.required]"
                    maxlength="20"
                    label="Display Name"
                    required
                    outlined
                    dense
                    prepend-inner-icon="fa-user"
                  ></v-text-field>

                  <v-text-field
                    class="custom-text-field"
                    v-model="email"
                    :rules="emailRules"
                    label="E-mail"
                    required
                    outlined
                    dense
                    prepend-inner-icon="fa-envelope"
                  ></v-text-field>

                  <v-text-field
                    class="custom-text-field"
                    v-model="password"
                    :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                    :type="show1 ? 'text' : 'password'"
                    :rules="[rules.required, rules.min]"
                    label="Password"
                    required
                    outlined
                    dense
                    prepend-inner-icon="fa-lock"
                    @click:append="show1 = !show1"
                  ></v-text-field>

                  <v-text-field
                    class="custom-text-field"
                    v-model="verify"
                    :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                    :type="show1 ? 'text' : 'password'"
                    :rules="[rules.required, passwordMatch]"
                    label="Confirm Password"
                    required
                    outlined
                    dense
                    prepend-inner-icon="fa-lock"
                    @click:append="show1 = !show1"
                  ></v-text-field>

                  <v-checkbox
                    v-model="checkbox"
                    :rules="[(v) => !!v || 'You must agree to continue!']"
                    label="I agree with Criarme's terms and services."
                    required
                  ></v-checkbox>

                  <v-btn
                    :disabled="!valid"
                    color="primary"
                    class="primary-btn"
                    rounded
                    @click="validate"
                  >
                    Create an Account
                  </v-btn>
                </v-form>
                <!-- Signup Options -->
                <div class="social-login">
                  <div class="or-sign-up">Or Sign up with</div>
                  <ul class="mt-5">
                    <li>
                      <a href="#">
                        <div class="img-wrapper">
                          <img
                            src="../assets/images/social-icons/Google.svg"
                            alt=""
                          />
                        </div>
                        <p class="label">Google</p>
                      </a>
                    </li>
                    <li>
                      <a href="#">
                        <div class="img-wrapper">
                          <img
                            src="../assets/images/social-icons/fb.svg"
                            alt=""
                          />
                        </div>
                        <p class="label">Facebook</p>
                      </a>
                    </li>
                    <li>
                      <a href="#">
                        <div class="img-wrapper">
                          <img
                            src="../assets/images/social-icons/twitter.svg"
                            alt=""
                          />
                        </div>
                        <p class="label">Twitter</p>
                      </a>
                    </li>
                  </ul>
                </div>
                <!-- Already have an account? Login Here -->
                <div class="mt-3">
                  <p class="login-link">
                    Already have an account ?
                    <a href="#" class="primary-text" @click="gotoLogin()">
                      Login Here
                    </a>
                  </p>
                </div>
              </div>
            </v-col>
            <!-- Login Screen -->
            <v-col cols="12" sm="6" md="6" class="login-area__right">
              <div class="login-screen">
                <div class="logo-wrapper">
                  <img
                    src="../assets/images/logo.png"
                    alt="Criarme Logo"
                    class="logo"
                  />
                </div>
                <div class="illustration-img">
                  <img src="../assets/images/Saly.png" alt="" />
                </div>
                <div class="welcome-text">
                  <h4 class="font-weight-bold">Welcome to Criarme</h4>
                  <p>just a couple of clicks and we start</p>
                </div>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </div>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: "Register",
  computed: {
    passwordMatch() {
      return () => this.password === this.verify || "Password must match";
    },
  },
  data: () => ({
    valid: true,

    name: "",
    email: "",
    password: "",
    verify: "",
    loginPassword: "",
    loginEmail: "",
    loginEmailRules: [
      (v) => !!v || "Required",
      (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
    ],
    emailRules: [
      (v) => !!v || "Required",
      (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
    ],

    show1: false,
    rules: {
      required: (value) => !!value || "Required.",
      min: (v) => (v && v.length >= 8) || "Min 8 characters",
    },
  }),

  methods: {
    validate() {
      this.$refs.form.validate();
    },
  },
};
</script>

<style lang="scss">
$bg-gradient: conic-gradient(
  from 180deg at 50% 50%,
  #fc913a 0deg,
  rgba(252, 145, 58, 0.76) 360deg
);
$box-shadow: 0px 4px 16px #00000017;
$bg-color: #fafafa;

.register-wrapper {
  height: auto !important;
}

.login-wrapper,
.register-wrapper {
  position: relative;
  height: 100vh;

  .bg-overlay {
    position: relative;
    top: 0;
    height: 100%;

    img {
      width: 100%;
      object-fit: contain;
      position: absolute;
      bottom: 0;
    }
  }

  .login-container {
    height: 100%;
    justify-content: center;
    padding: 3rem;

    .login-area {
      max-width: 90% !important;
      height: 100%;
      box-shadow: $box-shadow;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 16px;

      .login-area__left,
      .login-area__right {
        padding: 0;
        height: 100%;
      }

      .login-screen {
        height: 100%;
        background: $bg-gradient;
        text-align: center;
        border-radius: 0 16px 16px 0;
        padding: 2rem;

        .logo-wrapper {
          .logo {
            height: 3rem;
          }
        }

        .illustration-img {
          height: 64%;
          display: flex;
          align-items: center;
          justify-content: center;

          img {
            height: 100%;
          }
        }

        .welcome-text {
          color: #fff;
          margin-top: 2.5rem;
        }
      }

      .login-form__wrapper {
        padding: 2rem 3rem;
        text-align: center;
        height: 100%;

        .login-form {
          margin-top: 2rem;

          .v-label {
            font-size: 14px;
          }
          .v-icon.v-icon {
            font-size: 16px;
            color: #949494;
          }

          .custom-text-field {
            .v-input__slot {
              border-radius: 8px;
            }
          }

          .v-input--selection-controls {
            margin-top: 0;
            padding-top: 0;
          }

          button {
            width: 100%;
            height: 3rem;
            box-shadow: none;
          }
        }
      }

      .social-login {
        position: relative;
        .or-sign-up {
          margin: 1rem 0;
          position: relative;
          font-size: 12px;

          &::before {
            content: "";
            display: block;
            height: 1px;
            background: #e5e5e5;
            position: absolute;
            top: 8px;
            width: 21%;
            left: 13%;
          }

          &::after {
            content: "";
            display: block;
            height: 1px;
            background: #e5e5e5;
            position: absolute;
            top: 8px;
            width: 21%;
            right: 13%;
          }
        }

        ul {
          list-style: none;
          display: flex;
          align-items: center;
          justify-content: space-around;

          li {
            display: block;
            text-align: center;

            a {
              text-decoration: none;
              .img-wrapper {
                background: #f5f5f5;
                border-radius: 40px;
                height: 2.5rem;
                width: 2.5rem;
                display: inline-flex;
                align-items: center;
                justify-content: center;
                margin-bottom: 1rem;

                img {
                  height: 1.3rem;
                  transition: all 0.3s ease-in-out;
                }
              }

              .label {
                color: #979797;
                font-size: 14px;
              }

              &:hover {
                .img-wrapper img {
                  transform: scale(1.1);
                }
              }
            }
          }
        }
      }
    }
  }

  .login-link{
    font-size: 13px;
  }
}

@media screen and (max-width: 767px) {
  .login-wrapper, .register-wrapper {
    .login-container {
      padding: 0;
      .login-area__right {
        display: none;
      }
    }
  }
}

@media screen and (max-width: 520px) {
  .login-wrapper, .register-wrapper {
    .login-container {
      .login-area {
        max-width: 100% !important;
        box-shadow: none;

        .login-form__wrapper {
          padding: 1rem;

          .login-form .v-label {
            font-size: 12px;
          }
        }
      }
    }
  }
}
</style>
