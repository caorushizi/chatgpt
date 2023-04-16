<script setup lang="ts">
import { Haptics, ImpactStyle } from '@capacitor/haptics'
import { StatusBar, Style } from '@capacitor/status-bar'
import { RouterView } from 'vue-router'
import { Tabbar, TabbarItem, NavBar } from 'vant'

const onChange = async () => {
  await Haptics.impact({ style: ImpactStyle.Light })
}

StatusBar.setOverlaysWebView({ overlay: false })
const init = async () => {
  await StatusBar.setStyle({ style: Style.Light })
}

init()
</script>

<template>
  <NavBar title="Vant" />

  <RouterView />

  <Tabbar route @change="onChange">
    <TabbarItem replace to="/" icon="home-o">Home</TabbarItem>
    <TabbarItem replace to="/list" icon="search">Search</TabbarItem>
    <TabbarItem replace to="/about" icon="setting-o">Setting</TabbarItem>
  </Tabbar>
</template>

<style scoped></style>
