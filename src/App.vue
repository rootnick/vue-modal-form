<template>
  <v-app>
    <v-main>
      <v-btn @click="clickBtn"> click me </v-btn>
      <Dialog v-model="visibleDialog">
        <Form @valid="validForm" />
      </Dialog>

      <v-text-field v-model="formData" :disable="true" />
    </v-main>
  </v-app>
</template>

<script>
import Dialog from "./components/ui/Dialog.vue";
import Form from "./components/Form.vue";
export default {
  name: "App",
  components: {
    Dialog,
    Form,
  },

  data() {
    return {
      visibleDialog: false,
      formData: null,
    };
  },

  methods: {
    clickBtn() {
      this.visibleDialog = true;
    },
    closeDialog() {
      this.visibleDialog = false;
    },
    validForm(payload) {
      this.visibleDialog = false;
      this.formData = payload;
    },
  },
};
</script>
