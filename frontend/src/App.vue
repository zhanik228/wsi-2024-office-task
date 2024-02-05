<template>
  <main>
    <CreateUser :modalMode="modalMode" v-model:modalOpen="isModalOpen" />
    <SideBar />
    <div class="office">
      <img class="office-img" src="../src/assets/office_base_clean.jpg" alt="">
    </div>
  </main>
</template>

<script>
import CreateUser from "@/components/CreateUser.vue";
import SideBar from "@/components/SideBar.vue";

export default {
  components: { CreateUser, SideBar },
  data() {
    return {
      isInitializeUserOpen: false,
      modalMode: 'create',
      isModalOpen: false,
    }
  }
}
</script>

<style scoped>
.office {
  margin-left: 260px;
}

.office-img {
  width: 1500px;
  display: block;
}
</style>
