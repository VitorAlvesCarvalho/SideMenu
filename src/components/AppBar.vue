<template>
  <header class="app-bar">
    <button @click="toogleMenu" class="app-bar__button">
      <img src="../assets/icons/menu.png" />
    </button>
  </header>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import SideMenu from "@/components/SideMenu.vue";

@Component({
  components: {
    SideMenu,
  },
})
export default class App extends Vue {
  public open = false;

  public toogleMenu() {
    this.$emit("toogle-menu");
  }
}
</script>

<style lang="scss" scoped>
.app-bar {
  background-color: gray;
  padding: 16px 16px 12px;

  &__button {
    background-color: transparent;
    border: none;
    cursor: pointer;
  }
}
</style>
