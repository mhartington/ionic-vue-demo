<template>
  <div class="ion-page">
    <ion-header>
      <ion-toolbar>
        <ion-title>Hello World</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <h1>Welcome To @ionic/vue</h1>
      <img alt="Vue logo" src="../assets/logo.png">
      <ion-button expand="block" @click="navigate()">Go to About Page</ion-button>

      <ion-button expand="block" @click="showModal()">Show a Modal</ion-button>
    </ion-content>
  </div>
</template>

<script>
import Modal from "@/components/Modal.vue";
export default {
  name: "home",
  methods: {
    navigate: function() {
      this.$router.push("about");
    },
    showModal: async function() {
      const modal = await this.$ionic.modalController.create({
        component: Modal,
        componentProps: {
          propsData: {
            userData: Math.round(Math.random() * 100)
          }
        }
      });
      await modal.present();
    }
  }
};
</script>
