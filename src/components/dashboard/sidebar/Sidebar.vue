<template>
  <div class="dash-sidebar">
    <ul class="nav">
      <li class="nav-item active">
        <a class="nav-link" href="">
          <i class="mdi mdi-home"></i>
          <span class="menu-title">Dashboard</span>
        </a>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "Sidebar",
};
</script>
<style lang="scss">
.dash-sidebar {
  min-height: calc(100vh - 60px);
  background: #fff;
  font-weight: 500;
  padding: 0;
  width: 235px;
  z-index: 11;
  transition: width 0.25s ease, background 0.25s ease;

  .nav {
    overflow: hidden;
    flex-wrap: nowrap;
    flex-direction: column;
    margin-bottom: 60px;
  }
}
</style>
