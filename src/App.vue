<script setup lang="ts">
import { onMounted, ref } from 'vue'
import Button from './components/Button/Button.vue'
import Collapse from './components/Collapse/Collapse.vue'
import Item from './components/Collapse/CollapseItem.vue'
import type { ButtonInstance } from './components/Button/types'

const buttonRef = ref<ButtonInstance | null>(null)
const openValue = ref(['a'])
onMounted(() => {
  if (buttonRef.value) {
    console.log(buttonRef.value.ref)
  }
})

const testClick = () => {
  alert(123)
}
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
    />
  </header>

  <main>
    <Button ref="buttonRef" @click="testClick">Test Button</Button>
    <Button plain>Plain Button</Button>
    <Button round>Round Button</Button>
    <Button circle>Circle Button</Button>
    <Button disabled>Disabled Button</Button><br /><br />
    <Button type="primary">Primary</Button>
    <Button type="success">Success</Button>
    <Button type="info">Info</Button>
    <Button type="warning">Warning</Button>
    <Button type="danger">Danger</Button><br /><br />
    <Button type="primary" plain>Primary</Button>
    <Button type="success" plain>Success</Button>
    <Button type="info" plain>Info</Button>
    <Button type="warning" plain>Warning</Button>
    <Button type="danger" plain>Danger</Button><br /><br />
    <Button size="large">Large</Button>
    <Button size="small">Small</Button>
    <collapse v-model="openValue" accordion>
      <Item name="a">
        <template #title>
          <h1>Title A</h1>
        </template>
        <h1>headline title</h1>
        <div>this is content aaaaaa</div>
      </Item>
      <Item name="b" title="Title B">
        <div>this is content bbbbbbb</div>
      </Item>
      <Item name="c" title="Disabled C" disabled>
        <div>this is content cccccc</div>
      </Item>
    </collapse>
    {{ openValue }}
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
