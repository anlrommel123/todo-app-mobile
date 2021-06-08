<template>
  <ion-page>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>
  
      <div class="container">
        <HeaderItem />

        <ToDos :items="items" />
      </div>
    </ion-content>

  </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import HeaderItem from '@/components/HeaderItem.vue';
import ToDos from '@/components/ToDos.vue';

export default {
  name: 'tab1',
  components: {IonHeader, IonToolbar, IonTitle, IonContent, IonPage, HeaderItem, ToDos },

  data() {
    return {
      items: [1,2,3,4]
    }
  },

}
</script>