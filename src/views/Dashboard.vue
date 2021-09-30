<template>
  <div class="dashboard">
    <DashHeader />
    <div class="page-fluid">
      <Sidebar />
    </div>
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
    padding-top: 100px;
  }
}
</style>
