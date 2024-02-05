<template>
  <main>
    <CreateUser />
  </main>
</template>

<script>
import CreateUser from "@/components/CreateUser.vue";

export default {
  components: {CreateUser},
  data() {
    return {
      isInitializeUserOpen: false,
    }
  }
}
</script>

<style scoped>

</style>
