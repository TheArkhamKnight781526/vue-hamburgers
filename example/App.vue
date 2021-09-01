<template>
  <div style="margin-left: 50px; margin-top: 50px;">
    <hamburger
      type="spin"
      :width="30"
      :height="3"
      :spacing="1"
      color="green"
      :active="isActive"
      @toggle="toggle"
    />
    <h1 v-if="isActive">This will show when you click the hamburger!</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false
    }
  },
  methods: {
    toggle() {
      this.isActive = !this.isActive
    }
  }
}
</script>
