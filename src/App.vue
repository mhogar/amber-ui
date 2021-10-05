<template>
  <div class="wrapper">
    <nav class="navbar navbar-expand-md navbar-light fixed-top">
      <div class="container-fluid">
        <router-link to="/" class="navbar-brand">amber</router-link>
        <button class="navbar-toggler" type="button"
                data-bs-toggle="collapse" data-bs-target="#navbarCollapse" aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarCollapse">
          <ul class="navbar-nav me-auto mb-2 mb-md-0">
            <li class="nav-item">
              <router-link to="/users" class="nav-link">Users</router-link>
            </li>
            <li class="nav-item">
              <router-link to="/clients" class="nav-link">Clients</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <router-view v-slot="{ Component }">
      <transition enter-active-class="animate__animated animate__faster animate__fadeIn"
                  leave-active-class="animate__animated animate__faster animate__fadeOut"
                  mode="out-in">
        <component id="currentPage" :is="Component" />
      </transition>
    </router-view>
  </div>
</template>

<style lang="scss">

@import "./assets/theme.scss";
@import "../node_modules/bootstrap/scss/bootstrap";

body {
  background-color: $page;
}

#app {
  padding-top: 4.5rem;
}

.wrapper {
  max-width: 1680px;
  margin-left: auto;
  margin-right: auto;
}

.navbar {
  background-color: $navbar;
}

</style>
