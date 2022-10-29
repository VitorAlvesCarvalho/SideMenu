<template>
  <main>
    <AppBar @toogle-menu="toogleMenu" />
    <SideMenu :open.sync="openSideMenu" />
  </main>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import SideMenu from "@/components/SideMenu.vue";
import AppBar from "@/components/AppBar.vue";

@Component({
  components: {
    SideMenu,
    AppBar,
  },
})
export default class App extends Vue {
  public openSideMenu = false;

  public toogleMenu() {
    this.openSideMenu = !this.openSideMenu;
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
