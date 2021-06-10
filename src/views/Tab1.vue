<template>
  <ion-page>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>
  
      <div class="container">
        <HeaderItem @addItem="saveItem" />
        
        <ToDos :items="items" @checkItem="checkItem" />
        <CompletedItem :items="items" @checkItem="checkItem" />
      </div>
    </ion-content>

  </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue'
import HeaderItem from '@/components/HeaderItem.vue'
import ToDos from '@/components/ToDos.vue'
import CompletedItem from '@/components/CompletedItem.vue';

export default {
  name: 'tab1',
  components: {IonHeader, IonToolbar, IonTitle, IonContent, IonPage, HeaderItem, ToDos, CompletedItem },

  data() {
    return {
      items: []
    }
  },

  methods: {
    saveItem(item) {
      this.items.push(item)
    },

    checkItem(index) {
      this.items.map((f, i) => {
        if (i === index) {
          f['isChecked'] ? f['isChecked'] = false : f['isChecked'] = true
        } 
      })

    }
  }

}
</script>