<template>
  <v-form class="form">
    <v-text-field
      v-model="fieldVal"
      :error="Boolean(fieldError)"
      :error-messages="fieldError"
    />
    <v-btn @click="click">click</v-btn>
  </v-form>
</template>
<script>
import Vue from "vue";
export default Vue.extend({
  name: "Form",
  data() {
    return {
      fieldVal: null,
      fieldError: null,
      count: 0,
    };
  },
  methods: {
    click() {
      if (this.count === 0) {
        this.fieldError = "ошибка";
        this.count++;
      } else {
        this.$emit("valid", this.fieldVal);
      }
    },
  },
});
</script>