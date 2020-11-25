<template>
  <div id="app">
    <CreateText/>
  </div>
</template>

<script>

import CreateText from "@/components/CreateText";

export default {
  name: 'App',
  components: {
    CreateText,
  }
}
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  flex-direction: column;
  margin-top: 30px;
  width: 400px;
}
</style>
