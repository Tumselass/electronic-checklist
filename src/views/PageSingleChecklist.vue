<template>
  <div>
    <ListSingleChecklist :checklist="checklist" />
  </div>
</template>

<script>
import ListSingleChecklist from '@/components/ListSingleChecklist.vue';
import mockdata from '@/mockdata';

export default {

  data() {
    return {
      checklist: mockdata.checklists[this.$route.params.id]
    }
  },

  components: {
    ListSingleChecklist
  }
}
</script>

