<template>
  <div class="dash-header fixed-top">
    <v-container>
      <v-row class="navbar" align="center" justify="space-between">
        <div
          class="text-center navbar-brand-wrapper d-flex align-items-center justify-content-center"
        >
          <a class="navbar-brand brand-logo mr-5" href="/">
            <img src="assets/images/logo.svg" class="mr-2" alt="logo" />
          </a>
        </div>
        <div class="d-flex align-center">
          <div class="mr-8">
            <a href="" class="page-link">
              My Page
              <span class="mdi mdi-trending-up"></span>
            </a>
          </div>
          <div class="notifications mr-8">
            <v-badge overlap>
              <span class="mdi mdi-bell-outline icon"></span>
            </v-badge>
          </div>
          <div class="d-flex align-center">
            <v-avatar color="primary" size="38" class="dash-avatar mr-2">
              <img
                src="https://i.pinimg.com/originals/2e/89/8a/2e898af8c48ab1a3af5b370e5eb015e0.jpg"
                alt=""
              />
            </v-avatar>
            <span class="username">Marco Valentina</span>
          </div>
        </div>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  name: "DashHeader",
};
</script>
<style lang="scss">
.fixed-top {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 1030;
}

.dash-header {
  box-shadow: 0px 5px 21px -5px #cdd1e1;
  font-weight: 400;
  padding: 1rem 0;
  background: #fff;

  .navbar {
    .navbar-brand-wrapper {
      .navbar-brand {
        img {
          max-width: 100%;
          height: 34px;
          margin: auto;
          vertical-align: middle;
        }
      }
    }

    .dash-avatar {
      img {
        object-fit: cover;
      }
    }

    .username {
      font-size: 12px;
    }

    .notifications {
      .icon {
        font-size: 1.5rem;
      }
    }

    .page-link {
      background: #58a2cc;
      color: #fff;
      padding: 6px 22px;
      font-size: 14px;
      border-radius: 4px;
      text-decoration: none;
    }
  }
}
</style>
