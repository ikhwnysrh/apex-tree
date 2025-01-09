<template>
  <link
    href="https://cdn.jsdelivr.net/npm/remixicon@4.5.0/fonts/remixicon.css"
    rel="stylesheet"
  />
  <div class="sidebar">
    <div class="custom-dropdown">
      <!-- Dropdown button displays the selected option and its icon, plus the arrow -->
      <button class="dropdown-button">
        <i :class="selectedOption.icon"></i> {{ selectedOption.name }}
        <i :class="dropdownOpen ? 'ri-arrow-drop-up-line' : 'ri-arrow-drop-down-line'" class="dropdown-arrow"></i>
      </button>
      <div class="dropdown-content">
        <!-- Iterate over options and trigger a method to set the selected option -->
        <button v-for="option in options" :key="option.id" @click="selectOption(option)">
          <i :class="option.icon"></i> {{ option.name }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Track whether the dropdown is open or closed
      dropdownOpen: false,

      // Store the selected option
      selectedOption: {
        name: "Home",
        icon: "ri-home-4-line",
      },

      // Options list with id, name, and icon
      options: [
        { id: 1, name: "Home", icon: "ri-home-4-line" },
        { id: 2, name: "About", icon: "ri-information-line" },
        { id: 3, name: "Contact", icon: "ri-mail-line" },
      ],
    };
  },
  methods: {
    // Method to update the selected option when an option is clicked
    selectOption(option) {
      this.selectedOption = option;
      this.dropdownOpen = false; // Close the dropdown after selection
    },
    // Method to toggle the dropdown open/close state
    toggleDropdown() {
      this.dropdownOpen = !this.dropdownOpen;
    },
  },
};
</script>

<style scoped>
.sidebar {
  position: relative;
  padding: 1rem;
}

.custom-dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-button {
  background-color: #2134be;
  color: white;
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 0.5rem;
  display: flex;
  align-items: center;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
  justify-content: space-between; /* Spread content and the arrow */
  width: 100%;
}

.dropdown-button i {
  margin-right: 0.5rem;
}

.dropdown-button:hover {
  background-color: #172c99;
}

.dropdown-arrow {
  transition: transform 0.3s ease;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #fff;
  min-width: 200px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  z-index: 1;
  border-radius: 0.5rem;
  top: 100%;
  margin-top: 0.5rem;
  transition: opacity 0.3s ease-in-out;
  opacity: 0;
}

.custom-dropdown:hover .dropdown-content,
.dropdown-content:hover {
  display: block;
  opacity: 1;
}

.dropdown-content button {
  background-color: #fff;
  color: #2134be;
  padding: 0.75rem 1.5rem;
  border: none;
  width: 100%;
  text-align: left;
  border-radius: 0.5rem;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
}

.dropdown-content button i {
  margin-right: 0.75rem;
}

.dropdown-content button:hover {
  background-color: #f0f0f0;
}

.custom-dropdown .dropdown-content button:focus {
  outline: none;
}

.custom-dropdown .dropdown-content button.selected {
  background-color: #172c99;
  color: white;
}
</style>
