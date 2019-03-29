<template>
  <div class="ion-page">
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="end">
          <ion-button @click="dismiss()">
            <ion-icon name="close" slot="icon-only"></ion-icon>
          </ion-button>
        </ion-buttons>
        <ion-title>Modal</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <h1>This is a modal</h1>
      <h2>Data passed in: {{userData}}</h2>
      <ion-button expand="block" @click="dismiss()">Dismiss the Modal</ion-button>
    </ion-content>
  </div>
</template>
<script>
export default {
  props: {
    userData: {
      type: Number
    }
  },
  methods: {
    dismiss: async function() {
      await this.$ionic.modalController.dismiss();
    }
  }
};
</script>
