<template>
    <div class="dropdown">
      <button class="dropdown-btn" @click="toggleDropdown">
        <i class="ri-home-4-line dropdown-icon"></i>
        <span class="title">{{ selectedItem || 'Admin Bappeda' }}</span>
        <i class="ri-arrow-down-s-fill dropdown-arrow" :class="{ open: isOpen }"></i>
      </button>
      <div v-if="isOpen" class="dropdown-menu-container">
        <div class="search-container">
          <input
            type="text"
            class="search-input"
            v-model="searchQuery"
            placeholder="Search..."
            @input="filterOptions"
          />
        </div>
        <ul class="dropdown-menu">
          <li
            v-for="item in filteredOptions"
            :key="item.value"
            :class="{ selected: selectedItem === item.label }"
            @click.stop="selectItem(item.label)"
            class="dropdown-item"
          >
            <span :class="`icon ${item.icon || ''}`"></span>
            {{ item.label }}
          </li>
          <li v-if="filteredOptions.length === 0" class="dropdown-item disabled">
            No options found
          </li>
        </ul>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isOpen: false,
        selectedItem: "", 
        searchQuery: "",
        options: [
          { label: "Home", value: "home", icon: "icon-home" },
          { label: "About", value: "about", icon: "icon-info" },
          { label: "Contact", value: "contact", icon: "icon-mail" },
        ],
        filteredOptions: [],
      };
    },
    methods: {
      toggleDropdown() {
        this.isOpen = !this.isOpen;
        if (this.isOpen) {
          this.filteredOptions = this.options;
        }
      },
      selectItem(item) {
        this.selectedItem = item; 
        this.isOpen = false;
      },
      filterOptions() {
        const query = this.searchQuery.toLowerCase();
        this.filteredOptions = this.options.filter((item) =>
          item.label.toLowerCase().includes(query)
        );
      },
    },
    mounted() {
      this.filteredOptions = this.options;
    },
  };
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
  .dropdown {
    position: relative;
    display: inline-block;
    font-family: 'Inter', sans-serif;
    margin: 10px 0;
  }
  
  .dropdown-btn {
    font-family: 'Inter', sans-serif;
    background-color: #2B56C5;
    color: #ffffff;
    width: 218px;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .title {
  font-size: 16px;
  /* margin-left: 5px;  */
  margin-right: auto;
}
  
  .dropdown-btn .dropdown-icon {
    width: 22px;
    height: 22px;
    margin-right: 10px;
    font-size: 18px;
  }
  
  .dropdown-menu-container {
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    border: 1px solid #ccc;
    border-radius: 5px;
    background: white;
    z-index: 1;
  }
  
  .search-container {
    padding: 8px;
    background: #fff;
    border-radius: 4px;
  }
  
  .search-input {
    width: 100%;
    padding: 8px;
    box-sizing: border-box;
    border: none;
    outline: none;
    font-size: 14px;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  .dropdown-menu {
    margin: 0;
    padding: 0;
    list-style: none;
    max-height: 200px;
    overflow-y: auto;
  }
  
  .dropdown-item {
    display: flex;
    align-items: center;
    padding: 10px;
    cursor: pointer;
  }
  
  .dropdown-item:hover {
    background: #e0e0e0;
  }
  
  .dropdown-item.selected {
    background: #e0e0e0;
  }
  
  .dropdown-item.disabled {
    color: #ccc;
    cursor: not-allowed;
  }
  
  .dropdown-arrow {
    font-size: 18px;
    margin-left: 10px;
    color: #7493E6;
  }
  
  .dropdown-arrow.open {
    transform: rotate(180deg);
  }
  </style>