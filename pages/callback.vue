<template>
   <b-container fluid>
    <h1>Callback</h1>
   </b-container>
</template>

<script>
export default {
mounted: function () {
  debugger;
  this.$nextTick(function () {
    alert("callback")
  })
}

}
</script>

<style>

</style>
