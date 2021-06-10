<template>
    <div class="input-group mt-5">
      <input type="text" class="form-control" v-model="inputItem" @keyup.enter="addItem" placeholder="Add Item">
      <button class="btn btn-primary" type="button" @click="addItem">Add</button>
    </div>
</template>

<script>
    export default {
        name: 'header-item',

        data() {
            return {
                inputItem: null
            }
        },

        methods: {
            addItem() {
               this.$emit('addItem', {
                    item: this.inputItem,
                    isChecked: false
                });

               this.inputItem = null
            }
        }
    }
</script>