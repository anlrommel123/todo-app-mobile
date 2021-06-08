<template>
    <div class="input-group mt-5">
      <input type="text" class="form-control" v-model="inputItem" @keyup.enter="addItem" placeholder="Add Item">
      <button class="btn btn-primary" type="button" @click="addItem">Add</button>
    </div>
</template>

<script>
    export default {
        name: 'Header',
        // props: {
        //     items: Array
        // },
        data() {
            return {
                inputItem: null
            }
        },

        methods: {
            addItem() {
            //    this.$emit('addItem', {
            //         item: this.inputItem
            //     });

               this.inputItem = null
            }
        }
    }
</script>