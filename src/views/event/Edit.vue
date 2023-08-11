<template>
    <p> Edit the Event </p>
</template>

<script>
export default {
  props: ['event'],
  data: function() {
    return {
      unsavedChanges: true
    }
  },
  beforeRouteLeave(routeTo, routeFrom, next) {
    if (this.unsavedChanges) {
      const answer = window.confirm(
        'Do you really want to leave? You have unsaved changes!'
      )
      if (!answer) {
        return false
      }
    } else {
      next() // <-- Confirms the navigation
    }
  }
}
</script>
