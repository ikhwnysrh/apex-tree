<script setup>
import { ref } from 'vue';
import Multiselect from 'vue-multiselect';
import 'vue-multiselect/dist/vue-multiselect.min.css';

// Data untuk menu sidebar dengan ikon
const menuOptions = ref([
  { name: 'Home', path: '/', icon: 'ri-home-line' },
  { name: 'About', path: '/about', icon: 'ri-information-line' },
  { name: 'Services', path: '/services', icon: 'ri-tools-line' },
  { name: 'Contact', path: '/contact', icon: 'ri-mail-line' }
]);

// Value yang dipilih
const selectedMenu = ref(null);

// Fungsi untuk menampilkan label dengan ikon
const menuLabel = (option) => {
  return `
    <i class="${option.icon}" style="margin-right: 8px;"></i>${option.name}
  `;
};
</script>

<template>
  <div class="sidebar">
    <h3 class="sidebar-title">Menu</h3>
    <multiselect 
      v-model="selectedMenu" 
      :options="menuOptions" 
      :custom-label="menuLabel" 
      placeholder="Select a menu" 
      label="name" 
      track-by="name"
      class="menu-dropdown"
    >
      <template #option="{ option }">
        <!-- Tampilan opsi dengan ikon -->
        <i :class="option.icon" style="margin-right: 8px;"></i>
        {{ option.name }}
      </template>
    </multiselect>

    <!-- Debugging -->
    <pre class="language-json"><code>{{ selectedMenu }}</code></pre>
  </div>
</template>

<style scoped>
.sidebar {
  width: 250px;
  padding: 16px;
  background-color: #f4f4f4;
  border: 1px solid #ddd;
  border-radius: 8px;
}

.sidebar-title {
  margin-bottom: 16px;
  font-size: 18px;
  font-weight: bold;
  text-align: center;
}

.menu-dropdown {
  width: 100%;
}

pre {
  margin-top: 16px;
  padding: 8px;
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 4px;
}
</style>
