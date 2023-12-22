<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class=" flex justify-between items-center q-pa-md">
      <q-icon name="arrow_back_ios" size="20px"></q-icon>
      <q-toolbar-title class="text-center ">
          Master Learning
        </q-toolbar-title>

        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />


    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Menu
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Linkedim',
    caption: 'Aqui você será direcionado ao meu perfil',
    icon: 'school',
    link: 'https://www.linkedin.com/in/adrian-gds-0133a0234/'
  },
  {
    title: 'GitHub',
    caption: 'Aqui tem mais projetos...',
    icon: 'code',
    link: 'https://github.com/AdriannGuedes'
  },
]

export default {
  name: 'MainLayout',
  components: {
    EssentialLink
  },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}
</script>

<style lang="stylus">
.q-header{
  background-color: 	#87CEEB;
}

.q-page-container {
  padding-top: 65px !important;
}

</style>
