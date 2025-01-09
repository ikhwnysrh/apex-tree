<template>
    <div>
      <multiselect
        v-model="value"
        :options="options"
        placeholder=""
      >
        <!-- Slot untuk mengganti placeholder dengan ikon -->
        <template #placeholder>
          <div style="display: flex; align-items: center; gap: 8px;">
            <!-- Ikon di placeholder -->
            <span class="icon-placeholder" style="font-size: 16px;">
              <i class="ri-home-4-line"></i>
            </span>
            <span>Home</span>
          </div>
        </template>
  
        <!-- Slot untuk opsi dropdown dengan ikon -->
        <template #option="{ option }">
          <div style="display: flex; align-items: center; gap: 8px;">
            <!-- Ikon untuk setiap opsi -->
            <span :class="option.iconClass" style="font-size: 16px;"></span>
            <span>{{ option.label }}</span>
          </div>
        </template>
      </multiselect>
    </div>
  </template>
  
  <script>
  import Multiselect from 'vue-multiselect';
  
  export default {
    components: { Multiselect },
    data() {
      return {
        value: null,
        options: [
          { label: 'Home', iconClass: 'ri-home-4-line' },
          { label: 'About', iconClass: 'ri-information-line' },
          { label: 'Contact', iconClass: 'ri-mail-line' }
        ]
      }
    }
  }
  </script>
  
  <style src="vue-multiselect/dist/vue-multiselect.min.css"></style>
  
  <style>
  /* Gaya umum untuk multiselect */
  .multiselect {
    width: 300px;
  }

  .multiselect__placeholder {
    color: #ffff; /* Warna teks placeholder */
  }
  
  /* Background pada dropdown */
  .multiselect__content {
    background-color: aliceblue; /* Ganti dengan warna latar yang diinginkan */
    border-radius: 5px;
  }
  
  /* Background untuk opsi dropdown */
  .multiselect__option:hover {
    background-color: #2134be; /* Ganti dengan warna latar opsi yang diinginkan */
    padding: 10px;
    border-radius: 4px;
  }
  .multiselect__option {
    background-color: #2134be; /* Ganti dengan warna latar opsi yang diinginkan */
    padding: 10px;
    border-radius: 4px;
  }
  

  .multiselect__tags {
    background-color: #0000; /* Ganti dengan warna latar yang diinginkan */
    border-radius: 5px;
  }
  
  /* Placeholder dengan ikon */
  .icon-placeholder {
    color: #fff; /* Warna ikon di placeholder */
  }
  </style>
  