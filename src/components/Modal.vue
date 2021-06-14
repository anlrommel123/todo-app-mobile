<template>
        <ion-header translucent="" role="banner">
            <ion-toolbar>
              <ion-title>New Task</ion-title>
              <ion-buttons slot="end">
                <ion-button @click="dismissModal()">Close</ion-button>
              </ion-buttons>
            </ion-toolbar>
          </ion-header>
        <ion-content class="ion-padding">
            <ion-item>
                <ion-label position="floating">Enter task here</ion-label>
                <ion-input :value="inputItem" @keyup.enter="addItem" @ionInput="inputItem = $event.target.value; onInput$.next($event.target.value)"></ion-input>
            </ion-item>
        </ion-content>
</template>

<script>
import { IonContent, IonHeader, IonTitle, IonToolbar } from '@ionic/vue';
import { defineComponent } from 'vue';
import { modalController } from '@ionic/vue'

export default defineComponent({
  name: 'Modal',
  props: {
    title: { type: String, default: 'Super Modal' },
  },
  data() {
    return {
      content: 'Content',
      inputItem: null
    }
  },
  components: { IonContent, IonHeader, IonTitle, IonToolbar },

  methods: {
        addItem() {
               this.$emit('addItem', {
                    item: this.inputItem,
                    isChecked: false
                });

               this.inputItem = null
        },

        async dismissModal() {
            modalController.dismiss()
        }
  }
});
</script>