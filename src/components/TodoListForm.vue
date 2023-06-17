<template>
  <form @submit="onSubmit()">
    <VTextInput v-model="label"/>
    <VButton :disabled="!isFormValid">ADD TODO</VButton>
  </form>
</template>

<script>
import VTextInput from "@/components/VTextInput.vue";
import VButton from "@/components/VButton.vue";

export default {
  name: 'TodoListForm',
  components: {VButton, VTextInput},
  emits: ['submit'],
  data: () => ({
    label: ''
  }),
  computed: {
    isFormValid() {
      return this.label;
    }
  },
  methods: {
    onSubmit() {
      this.$emit('submit', {
        id: 1,
        label: this.label,
        checked: false,
      });
    }
  }
}
</script>

<style scoped>
form {
    display: grid;
    gap: 1em;
    padding: 0.5em;
    grid-template-columns: 1fr max-content;
}

</style>
