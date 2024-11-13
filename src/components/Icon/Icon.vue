<template>
  <i class="lyj-icon">
    <font-awesome-icon v-bind="$props"></font-awesome-icon>
  </i>
</template>

<script setup lang="ts">
import type { FontAwesomeIconProps } from '@fortawesome/vue-fontawesome'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
defineOptions({ name: 'LyjIcon', inheritAttrs: false })
defineProps<FontAwesomeIconProps>()
</script>
