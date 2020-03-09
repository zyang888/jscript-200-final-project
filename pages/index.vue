<template>
  <div>
    <b-jumbotron>
      <template v-slot:header>JS200 Final Project</template>
      <template v-slot:lead>
        Table of Contents
      </template>
      <hr class="my-4">
      <nuxt-link to="/Game" class="text-warning">Flappy Bird</nuxt-link><p>One or more timing functions<br>Sets, updates or changes local storage</p>
      <nuxt-link to="/Images" class="text-success">Jokes</nuxt-link><p>3rd party API</p>
      <nuxt-link to="/Form" class="text-danger">Form</nuxt-link><p>Contains form fields, validates those fields</p>
    </b-jumbotron>
    <!-- <img v-bind:src="image"> -->
  </div>
</template>

<script>

export default {
  name: 'home'
}
</script>
