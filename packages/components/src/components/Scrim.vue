<script setup lang="ts">
const emits = defineEmits(["click"]);

function handleClick(event: MouseEvent) {
  emits("click", event);
}
</script>

<template>
  <div :class="$style.scrim" @click.self="handleClick">
    <slot></slot>
  </div>
</template>

<style lang="scss" module>
@use "@/styles/color";

.scrim {
  position: absolute;
  top: 0px;
  right: 0px;
  left: 0px;
  bottom: 0px;

  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;

  background-color: rgba(color.$background-dark, 0.7);
}
</style>
