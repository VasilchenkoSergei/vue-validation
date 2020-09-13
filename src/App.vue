<template>
  <div id="app">
    <div class="container">
      <user-form />
    </div>
  </div>
</template>

<script>
import UserForm from './components/UserForm'

export default {
  name: 'App',
  components: {
    UserForm
  }
}
</script>
