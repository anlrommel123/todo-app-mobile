<template>
    <div class="mt-4">
        <hr>
        <h6>TO DO</h6>
        <div v-for="(item, index) in items" :key="index" v-show="!item.isChecked" class="card mt-2">
            <div class="card-body text-dark">
                <div class="form-check">
                    <input @click="checkItem(index)" class="form-check-input" type="checkbox" :checked="item.isChecked">
                    <label class="form-check-label">
                        {{ item.item }}
                    </label>
                    <button class="btn btn-sm float-end"><ion-icon @click="deleteItem(index)" size="small" color="danger" :icon="trash" /></button> 
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import { IonIcon } from '@ionic/vue';
    import { trash } from 'ionicons/icons';

    export default {
        name: 'todos',

        components: {
            IonIcon
        },

        setup() {
            return {
                trash
            }
        },

        props: {
            items: Array
        },

        methods: {
            checkItem(index) {
                this.$emit('checkItem', index)
            },

            deleteItem(index) {
                this.$emit('deleteItem', index)
            }
        }
    }
</script>