<template>
  <v-select
    v-model="inputValue"
    @change="chageItem"
    :label="attr.label"
    :data-testid="`input-${attr.name}`"
    :value="attr.value"
    :name="attr.name"
    :ref="attr.name"
    :items="attr.options"
    item-text="title"
    :required="isRequired"
    :rules="getRule"
  >
  </v-select>
</template>

<script>
import utility from "../mixins/utility";

export default {
  mixins: [utility],
  methods: {
    chageItem(value) {
      this.sendInputValue(value);
      this.forwardRef(this.$refs[this.attr.name]);
    },
  },
};
</script>

<style>
</style>