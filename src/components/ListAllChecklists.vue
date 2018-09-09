<template>
  <nav>
    <ul 
      v-for="checklist in checklists"
      :key="checklist.id"
    >
      <router-link :to="'view-checklist/'+checklist.id">
        <li>
          {{ checklist.name }}
          {{ checklist.company }}
        </li>
      </router-link>
    </ul>
  </nav>
</template>

<script>

export default {
  props: {
    checklists: {
      required: true,
      type: Object
    }
  }
};
</script>


<style scoped>
</style>
