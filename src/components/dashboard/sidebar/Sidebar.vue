<template>
  <div class="dash-sidebar">
    <ul class="nav">
      <li class="nav-item active">
        <a class="nav-link" href="">
          <i class="mdi mdi-home-outline"></i>
          <span class="menu-title">Home</span>
        </a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="">
          <i class="mdi mdi-newspaper-variant-multiple-outline"></i>
          <span class="menu-title">My Posts</span>
        </a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="">
          <i class="mdi mdi-magnify-expand"></i>
          <span class="menu-title">Explore</span>
        </a>
      </li>
      <hr class="border-bottom" />
      <li class="nav-item">
        <a class="nav-link" href="">
          <i class="mdi mdi-chart-box-outline"></i>
          <span class="menu-title">Dashboard</span>
        </a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="">
          <i class="mdi mdi-account-group-outline"></i>
          <span class="menu-title">Supporters</span>
        </a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="">
          <i class="mdi mdi-hand-heart-outline"></i>
          <span class="menu-title">Commissions</span>
        </a>
      </li>
      <hr class="border-bottom" />
      <li class="nav-item">
        <a class="nav-link" href="">
          <i class="mdi mdi-cog-sync-outline"></i>
          <span class="menu-title">Settings</span>
        </a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="">
          <i class="mdi mdi-logout"></i>
          <span class="menu-title">Logout</span>
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
  width: 20%;
  z-index: 11;
  transition: width 0.25s ease, background 0.25s ease;
  border-right: 1px solid #f5f5f5;

  .nav {
    overflow: hidden;
    flex-wrap: nowrap;
    flex-direction: column;
    margin-bottom: 60px;
    margin-top: 6rem;
    margin-right: 2rem;

    .nav-item {
      padding: 4px 10px;
      margin-bottom: 0.5rem;

      .nav-link {
        color: #2d3748;
        text-decoration: none;
        display: flex;
        align-items: center;
        font-size: 14px;
        font-weight: 400;

        i {
          margin-right: 1rem;
          font-size: 1.2rem;
        }
      }
    }

    .active {
      background: #f26b38;
      border-radius: 2rem;

      a {
        color: #fff!important;
      }
    }

    .border-bottom {
      background: #f5f5f5;
      height: 2px;
      border: none;
      margin: 1rem 0;
    }
  }
}
</style>
