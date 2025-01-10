<template>
  <div :tabindex="searchable ? -1 : tabindex"
       :class="{ 'multiselect--active': isOpen, 'multiselect--disabled': disabled, 'multiselect--above': isAbove }"
       @focus="activate()" 
       @blur="searchable ? false : deactivate()" 
       @keydown.self.down.prevent="pointerForward()"
       @keydown.self.up.prevent="pointerBackward()" 
       @keypress.enter.tab.stop.self="addPointerElement($event)"
       @keyup.esc="deactivate()" 
       class="multiselect" 
       role="combobox" 
       :aria-owns="'listbox-' + id">
    <div @mousedown.prevent.stop="toggle()" class="multiselect__tags">
      <span><i class="ri-home-4-line"></i>{{ selectedOption || ' Admin Bappeda' }}</span>
      <div class="multiselect__select"></div>
    </div>
    <div v-show="isOpen" class="multiselect__content-wrapper" tabindex="-1" :style="{ maxHeight: optimizedHeight + 'px' }">
      <input ref="search" type="text" autocomplete="off" spellcheck="false" :placeholder="placeholder"
             :style="inputStyle" :value="search" :disabled="disabled" :tabindex="tabindex"
             @input="updateSearch($event.target.value)" class="multiselect__input multiselect__input_custom" />
      <ul class="multiselect__content" role="listbox" :id="'listbox-' + id">
        <li v-for="(option, index) of filteredOptions" :key="index" 
            class="multiselect__option" 
            @click.stop="select(option)">
          <span>{{ getOptionLabel(option) }}</span>
        </li>
        <li v-show="showNoResults && (filteredOptions.length === 0 && search && !loading)">
          <span class="multiselect__option">No elements found.</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import multiselectMixin from 'vue-multiselect/src/multiselectMixin'
import pointerMixin from 'vue-multiselect/src/pointerMixin'

export default {
  name: 'vue-multiselect',
  mixins: [multiselectMixin, pointerMixin],
  props: {
    searchable: {
      type: Boolean,
      default: true
    },
    options: {
      type: Array,
      default: () => [' Home', ' About', ' Contact']
    },
    placeholder: {
      type: String,
      default: 'Search...'
    },
    tabindex: {
      type: Number,
      default: 0
    },
    maxHeight: {
      type: Number,
      default: 300
    },
    disabled: {
      type: Boolean,
      default: false
    },
    showNoResults: {
      type: Boolean,
      default: true
    }
  },
  data() {
    return {
      search: '',
      isOpen: false,
      selectedOption: null
    };
  },
  computed: {
    filteredOptions() {
      return this.search
        ? this.options.filter(option => option.toLowerCase().includes(this.search.toLowerCase()))
        : this.options;
    }
  },
  methods: {
    activate() {
      this.isOpen = true;
    },
    deactivate() {
      this.isOpen = false;
    },
    toggle() {
      this.isOpen = !this.isOpen;
    },
    select(option) {
      this.selectedOption = option; // Update the selected option
      this.isOpen = false; // Close the dropdown
      this.search = ''; // Clear the search box
    },
    updateSearch(value) {
      this.search = value;
    },
    getOptionLabel(option) {
      return option;
    }
  }
};
</script>

<style scoped>
.multiselect {
  width: 218px;
  margin-top: 10px;
  border-radius: 4px;
  background-color: #ffffff;
  font-family: 'Inter', sans-serif;
  position: relative;
}

.multiselect__tags {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 8px;
  background-color: #2B56C5;
  color: white;
  font-size: 16px;
  cursor: pointer;
}

.multiselect__select {
  margin-left: 8px;
  font-size: 12px;
}
.multiselect__tags span i {
  margin-right: 10px;
}

.multiselect__input_custom {
  width: 200px;
  padding: 6px 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 14px;
  margin: 8px 0 8px 8px;
}

.multiselect__content-wrapper {
  position: absolute;
  width: auto;
  background: white;
  border: 1px solid #ccc;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  z-index: 10;
}

.multiselect__content {
  list-style: none;
  padding: 0;
  margin: 0;
}

.multiselect__option {
  padding: 10px 12px;
  cursor: pointer;
  font-size: 14px;
  color: #333;
}

.multiselect__option:hover {
  background-color: #f1f1f1;
}

.multiselect__option--selected {
  background-color: #e8e8e8;
}

.multiselect__select::before {
  border-color: #7493E6 transparent transparent;
}
</style>
