<template>
  <q-item
    clickable
    v-ripple
    :active="link === '1'"
    @click="link = '1'"
    class="link"
    active-class="active-link"
  >
    <q-item-section avatar>
      <q-icon name="school" />
    </q-item-section>

    <q-item-section>
      <q-item-label>Пункт 1</q-item-label>
    </q-item-section>
  </q-item>
  <q-item
    clickable
    v-ripple
    :active="link === '2'"
    @click="link = '2'"
    class="link"
    active-class="active-link"
  >
    <q-item-section avatar>
      <q-icon name="school" />
    </q-item-section>

    <q-item-section>
      <q-item-label>Пункт 2</q-item-label>
    </q-item-section>
  </q-item>
  <q-item
    clickable
    v-ripple
    :active="link === '3'"
    @click="link = '3'"
    class="link"
    active-class="active-link"
  >
    <q-item-section avatar>
      <q-icon name="school" />
    </q-item-section>

    <q-item-section>
      <q-item-label>Пункт 2</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
  import { ref } from 'vue'

  export default {
    name: 'AsideMenu',
    setup () {
      return {
        link: ref('1')
      }
    }
  }
</script>

<style lang="scss">
  .link {
    color: #F5F5F5;
    background: #424242;
  }
  .active-link {
      color: #424242;
      background: #F5F5F5;
    }
</style>
