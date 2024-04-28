<script setup>
import { ref } from 'vue'
</script>

<template>
  <!--menu bootstrap-->
  <nav class="navbar navbar-expand-lg bg-body-tertiary" data-bs-theme="dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="/">
        <img src="/public/favicon.ico" alt="Bootstrap" width="30" height="24">
      </a>
      <router-link class="navbar-brand" to="/">Personagens</router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup"
        aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <router-link class="nav-link" arial-current="page" to="/">Inicio</router-link>
          <router-link class="nav-link" arial-current="page" to="/about">Sobre</router-link>
        </div>
      </div>
    </div>
  </nav>

  <div class="mais">
    <router-view></router-view>
  </div>

</template>

<style></style>