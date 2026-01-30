<script setup>
import { ref, computed, onMounted } from 'vue'
import sidebar from ' '
import { menuItems } from './constants/layout.constants-ui.js'

// Estado reactivo del sidebar
const sidebarOpen = ref(true);

// Manejadores de eventos
const handleSidebarToggle = (isOpen) => {
  sidebarOpen.value = isOpen;
};
</script>

<template>
  <div class="flex h-screen w-full overflow-hidden" >
    <!-- Sidebar fijo a la izquierda -->
    <sidebar
      :menu-items="menuItems"

    />

    <!-- Contenedor principal -->
    <main class="flex-1 overflow-hidden" >
      <router-view />
    </main>
  </div>
</template>

<style scoped>

</style>