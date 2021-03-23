<template>
  <div id="app" class="text-center">
    <h3 class="mt-4 customRow">Currency conversor using VueJs</h3>
    <div class="row customRow justify-content-around mt-5">
      <Conversor moeda-a="USD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="USD" />
    </div>
    <div class="row customRow justify-content-around mt-5">
      <Conversor moeda-a="CAD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="CAD" />
    </div>
    <div class="row customRow justify-content-around mt-5">
      <Conversor moeda-a="GBP" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="GBP" />
    </div>
  </div>
</template>

<script>
import Conversor from './components/Conversor'

export default {
  name: 'App',
  components: {
    Conversor
  }
}
</script>

<style>
.customRow {
  min-width: 600px;
  max-width: 800px;
}
</style>
