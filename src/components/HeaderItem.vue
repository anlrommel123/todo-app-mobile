<template>
    <div class="input-group mt-5">
      <input type="text" class="form-control" @click="openModal" placeholder="Add Task">
      <button class="btn btn-primary" type="button">Add</button>
    </div>
</template>

<script>
    import { modalController } from '@ionic/vue'
    import Modal from '@/components/Modal.vue'

    export default {
        name: 'header-item',

        methods: {

            async openModal() {
                const modal = await modalController
                    .create({
                        component: Modal,
                        cssClass: 'my-custom-class',
                        componentProps: {
                            title: 'New Title'
                        },
                    })
                return modal.present();
            }
        }
    }
</script>