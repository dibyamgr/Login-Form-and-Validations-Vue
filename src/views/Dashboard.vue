<template>
  <div class="dashboard">
    <DashHeader />
    <v-container>
      <div class="page-fluid">
        <Sidebar />
        <div class="main-panel">
          <div class="content-wrapper">
            Welcome.
          </div>
        </div>
      </div>
    </v-container>
  </div>
</template>
<script>
import DashHeader from "../components/dashboard/header/DashHeader";
import Sidebar from "../components/dashboard/sidebar/Sidebar";
export default {
  name: "Dashboard",
  components: {
    DashHeader,
    Sidebar,
  },
};
</script>

<style lang="scss">
.dashboard {
  .page-fluid {
    display: flex;
    flex-direction: row;

    .main-panel {
      padding-top: 6rem;
      width: 100%;

      .content-wrapper {
        padding: 1rem;
      }
    }
  }
}
</style>
