<template>
<div class="q-pa-md">
  <q-layout view="lHh Lpr lFf" class="shadow-2 rounded-borders">
    <q-header elevated>
      <q-toolbar class="text-center">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          <q-avatar>
            <img src="../../public/favicon.png">
          </q-avatar>
          AdvanceEdu
        </q-toolbar-title>

<q-btn-group>
        <q-btn-dropdown flat auto-close rounded dense icon="person">
          
        <!-- dropdown content goes here -->
        <q-list padding style="width: 250px">
          <q-item clickable>
            <q-item-section avatar>
              <q-avatar icon="person" color="blue" text-color="white" />
            </q-item-section>
            <q-item-section>
              <q-item-label>Profile</q-item-label>
            </q-item-section>
            <q-item-section side>
              <q-icon name="info" color="amber" />
            </q-item-section>
          </q-item>

          <q-item clickable>
            <q-item-section avatar>
              <q-avatar icon="inbox" color="blue" text-color="white" />
            </q-item-section>
            <q-item-section>
              <q-item-label>Inbox</q-item-label>
            </q-item-section>
            <q-item-section side>
              <q-icon name="info" color="amber" />
            </q-item-section>
          </q-item>

          <q-item clickable>
            <q-item-section avatar>
              <q-avatar icon="settings" color="blue" text-color="white" />
            </q-item-section>
            <q-item-section>
              <q-item-label>Settings</q-item-label>
            </q-item-section>
            <q-item-section side>
              <q-icon name="info" color="amber" />
            </q-item-section>
          </q-item>

          <q-separator inset />
          <q-item-label header>Files</q-item-label>

          <q-item clickable>
            <q-item-section avatar>
              <q-avatar icon="assignment" color="teal" text-color="white" />
            </q-item-section>
            <q-item-section>
              <q-item-label>Machine learning</q-item-label>
              
            </q-item-section>
            <q-item-section side>
              <q-icon name="info" color="amber" />
            </q-item-section>
          </q-item>

          <q-item clickable>
            <q-item-section avatar>
              <q-avatar icon="assignment" color="teal" text-color="white" />
            </q-item-section>
            <q-item-section>
              <q-item-label>Web development</q-item-label>
            </q-item-section>
            <q-item-section side>
              <q-icon name="info" color="amber" />
            </q-item-section>
          </q-item>
        </q-list>
      </q-btn-dropdown>
    </q-btn-group>
  </q-toolbar>

      <q-tabs v-model="tab">
        <q-route-tab to="/page1" label="Dashboard" />
        <q-route-tab to="/page1" label="Courses" />
        <q-route-tab to="/page2" label="Library" />
        <q-route-tab to="/page3" label="Chatroom" />
        <q-route-tab to="/page3" label="Lectures" />
      </q-tabs>
    </q-header>

    <q-footer bordered class="bg-primary text-white" >
        <q-tabs no-caps active-color="white" indicator-color="transparent" class="text-black" v-model="tab">
          <q-tab name="articles" label="Community" />
          <q-tab name="videos" label="Tutorials" />
          <q-tab name="books" label="Documents" />
        </q-tabs>
        
      </q-footer>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Essential Links
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
  </div>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'


const linksList = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
];


import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      tab: ref('images'),
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
