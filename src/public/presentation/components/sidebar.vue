<script setup>
import { useRoute } from 'vue-router'
import {onMounted} from "vue";

// Props
const props = defineProps({
  menuItems: {
    type: Array,
    required: true
  }
})

const route = useRoute()

// Marca activo según la ruta actual
const isActive = (path) => {
  return route.path.startsWith(path)
}

onMounted(() => {
  console.log('Sidebar mounted with menu items:', props.menuItems);
})
</script>

<template>
  <nav class="sidebar">
    <ul class="menu-list">
      <li
          v-for="item in menuItems"
          :key="item.label"
          :class="['menu-item', { active: isActive(item.to) }]"
      >
        <RouterLink
            :to="item.to"
            class="menu-link"
            :title="item.title"
        >
          <i :class="item.icon"></i>
          <span>{{ item.label }}</span>
        </RouterLink>
      </li>
    </ul>
  </nav>
</template>

<style scoped>

</style>
