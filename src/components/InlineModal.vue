<template>
  <ion-modal ref="modal" :trigger="trigger" @willDismiss="onWillDismiss">
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-button @click="cancel()">Cancel</ion-button>
        </ion-buttons>
        <ion-title>Welcome</ion-title>
        <ion-buttons slot="end">
          <ion-button :strong="true" @click="confirm()">Confirm</ion-button>
        </ion-buttons>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <ion-item>
        <ion-input
          label="Enter your name"
          label-placement="stacked"
          ref="input"
          type="text"
          placeholder="Your name"
        ></ion-input>
      </ion-item>
      <ion-button @click="navigate(navigation)">Navigation</ion-button>
    </ion-content>
  </ion-modal>
</template>

<script setup lang="ts">
import {
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonButtons,
  IonButton,
  IonModal,
  IonItem,
  IonInput,
} from "@ionic/vue";
import { OverlayEventDetail } from "@ionic/core/components";
import { ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const modal = ref();
const input = ref();
const model = defineModel();
const { trigger, navigation } = defineProps(["trigger", "navigation"]);

const cancel = () => modal.value.$el.dismiss(null, "cancel");

const confirm = () => {
  const name = input.value.$el.value;
  modal.value.$el.dismiss(name, "confirm");
};

const onWillDismiss = (ev: CustomEvent<OverlayEventDetail>) => {
  if (ev.detail.role === "confirm") {
    model.value = `Hello, ${ev.detail.data}!`;
  }
};

const navigate = (path: string) => {
  cancel();
  router.push(path);
};
</script>

<style scoped></style>
