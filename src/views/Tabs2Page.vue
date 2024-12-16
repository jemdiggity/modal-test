<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom">
        <ion-tab-button tab="tab4" href="/tabs2/tab4">
          <ion-icon aria-hidden="true" :icon="triangle" />
          <ion-label>Tab 4</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab5" href="/tabs2/tab5">
          <ion-icon aria-hidden="true" :icon="ellipse" />
          <ion-label>Tab 5</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab6" href="/tabs2/tab6">
          <ion-icon aria-hidden="true" :icon="square" />
          <ion-label>Tab 6</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script setup lang="ts">
import {
  IonTabBar,
  IonTabButton,
  IonTabs,
  IonLabel,
  IonIcon,
  IonPage,
  IonRouterOutlet,
} from "@ionic/vue";
import { ellipse, square, triangle } from "ionicons/icons";
</script>
