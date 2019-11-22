<template>
  <div id="app">
  <!--  <img src="./assets/logo.png">-->
  <b-navbar toggleable="md" type="dark" variant="dark">

        <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>

        <b-navbar-brand to='/' >Agenda</b-navbar-brand>

        <b-collapse is-nav id="nav_collapse">

          <b-navbar-nav>
            <b-nav-item to="/record">Recordar</b-nav-item>
            <b-nav-item href="#">Tareas</b-nav-item>
            <b-nav-item href="#">Notas</b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
        </b-collapse>
    </b-navbar>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>


</style>
