<template>
  <button
    class="lyj-button"
    ref="_ref"
    :class="{
      [`lyj-button--${type}`]: type,
      [`lyj-button--${size}`]: size,
      'is-plain': plain,
      'is-round': round,
      'is-circle': circle,
      'is-disabled': disabled,
    }"
    :disabled="disabled"
    :autofocus="autofocus"
    :type="nativeType"
  >
    <span>
      <slot />
    </span>
  </button>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { ButtonProps } from './types'
defineOptions({ name: 'LyjButton', inheritAttrs: false })
withDefaults(defineProps<ButtonProps>(), { nativeType: 'button' })
const _ref = ref<HTMLButtonElement>()
defineExpose({
  ref: _ref,
})
</script>

<style>
.lyj-button {
  --main-bg-color: yellow;
  background-color: var(--main-bg-color);
}
</style>
