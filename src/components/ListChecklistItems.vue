<template>
  <div>
    <ListSingleChecklistItem 
      v-for="(item, key, index) in content" 
      :key="item.id"
      :item="item"
      :state="trackItems[index]"
      @checkedItem="toggleCheckedItem"
    />
  </div>
</template>

<script>
import ListSingleChecklistItem from './ListSingleChecklistItem '
export default {

  components: {
    ListSingleChecklistItem 
  },

  created() {
      // TODO Check for this object in localstorage
      const numberOfItems = Object.keys(this.content).length;
      let indexArray = [];
      
      for (let i = 0; i < numberOfItems; i++) {
        indexArray.push({
          position: i,
          checked: false
        });
      }

      this.trackItems = indexArray;
  },

  data() {
    return {
      content: this.sections.content,
      trackItems: {}
    }
  },

  methods: {
    toggleCheckedItem(position) {
      this.trackItems[position].checked = !this.trackItems[position].checked
    }
  },
  
  props: {
    sections: {
      required: true,
      type: Object
    }
  }
}
</script>


