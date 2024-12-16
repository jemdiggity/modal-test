<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 4</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding" :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 4</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-button id="open_modal4" expand="block">Open</ion-button>
      <p>{{ message }}</p>
      <InlineModal
        v-model="message"
        trigger="open_modal4"
        navigation="/tabs/tab1"
      ></InlineModal>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonButton,
} from "@ionic/vue";
import { ref } from "vue";

import InlineModal from "@/components/InlineModal.vue";

const message = ref(
  "This modal example uses triggers to automatically open a modal when the button is clicked."
);
</script>
