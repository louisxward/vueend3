<script lang="ts">
import SidebarLink from './SidebarLink.vue'
import { collapsed, toggleSidebar, sidebarWidth } from './state'

export default {
  props: {},
  components: { SidebarLink },
  setup() {
    return { collapsed, toggleSidebar, sidebarWidth }
  }
}
</script>

<template>
  <div class="sidebar" :style="{ width: sidebarWidth }">


    <SidebarLink to="/" icon="fa-solid fa-house-chimney">Home</SidebarLink>
    <SidebarLink to="/about" icon="fa-solid fa-circle-info">About</SidebarLink>

    <span
      class="collapse-icon"
      :class="{ 'rotate-180': collapsed }"
      @click="toggleSidebar">
      <i class="icon"><font-awesome-icon icon="fa-solid fa-angles-left" /></i>
    </span>
  </div>
</template>

<style>
:root {
  --sidebar-bg-color: #4b7bec;
  --sidebar-item-hover: #3265db;
  --sidebar-item-active: #3867d6;
}
</style>S

<style scoped>
.sidebar {
  color: white;
  background-color: var(--sidebar-bg-color);
  float: left;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  bottom: 0;
  padding: 0.5em;
  transition: 0.3s ease;
  display: flex;
  flex-direction: column;
}
.sidebar h1 {
  height: 1.25em;
}
.collapse-icon {
  position: absolute;
  bottom: 0;
  padding: 0.75em;
  color: rgba(255, 255, 255, 0.7);
  transition: 0.2s linear;
}
.rotate-180 {
  transform: rotate(180deg);
  transition: 0.2s linear;
  left: 5px;
}
</style>