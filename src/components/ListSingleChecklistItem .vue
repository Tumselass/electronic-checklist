<template>
  <div tabindex="0" @click="toggleChecked" @keyup.13="toggleChecked" :class="{'tm_checked-item': state.checked}">
    {{ item.challange }}...........{{ item.response }}
  </div>
</template>

<script>
export default {

  methods: {
    toggleChecked() {
      this.$emit('checkedItem', this.state.position)
    }
  },
  
  props: {
    item: {
      required: true,
      type: Object
    },
    state: {
      required: true,
      type: Object
    } 
  }
}
</script>

