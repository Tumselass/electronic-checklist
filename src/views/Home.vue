<template>
  <div class="home">
    <ListAllChecklists :checklists="checklists" />
  </div>
</template>

<script>
// @ is an alias to /src
import ListAllChecklists from '@/components/ListAllChecklists.vue';
import mockdata from '@/mockdata';

export default {

  components: {
    ListAllChecklists,
  },

  data() {
    return {
      checklists: mockdata.checklists
    }
  }
};
</script>
