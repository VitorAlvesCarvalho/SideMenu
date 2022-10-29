<template>
  <section>
    <transition name="side-transition">
      <div v-if="open" class="side-menu">
        <section class="side-menu__action">
          <button @click="toogleMenu" class="side-menu__button">
            <img src="../assets/icons/close.png" />
          </button>
        </section>

        <slot />
      </div>
    </transition>
  </section>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";

@Component({})
export default class App extends Vue {
  @Prop({ type: Boolean, required: false })
  readonly open?: boolean;

  public toogleMenu() {
    this.$emit("update:open", false);
  }
}
</script>

<style lang="scss" scoped>
.side-menu {
  align-items: flex-end;
  background-color: gray;
  width: 300px;
  height: calc(100vh - 56px);
  padding: 24px;

  &__action {
    display: flex;
    justify-content: flex-end;
  }

  &__button {
    background-color: transparent;
    border: none;
    cursor: pointer;
  }
}

.side-transition {
  &-enter,
  &-leave-to {
    transform: translateX(-300px);
  }

  &-enter-active,
  &-leave-active {
    transition: all 800ms;
  }
}
</style>
