<template>
  <div>
    <div 
      v-for="section in sections"
      :key="section.id"
    >
    <h1> {{ section.name }} </h1>
    <ListChecklistItems :sections="sections[section.id]" />
    </div>
  </div>
</template>

<script>
import ListChecklistItems from './ListChecklistItems';

export default {

  components: {
    ListChecklistItems
  },

  data() {
    return {
      sections: this.checklist.sections
    }
  },
  
  props: {
    checklist: {
      required: true,
      type: Object
    }
  }
}
</script>

