<template>
    <div>
        <div class="input-group mt-5">
            <input type="text" class="form-control" v-model="inputItem" @keyup.enter="addItem" placeholder="Add Task">
            <button class="btn btn-primary" @click="addItem" type="button">Add</button>
        </div>
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
                if (this.inputItem) {

                    this.$emit('addItem', {
                        item: this.inputItem,
                        isChecked: false
                    });

                    this.inputItem = null
                } else {
                    this.$emit('openToast', 'Task name is required.');
                }
            },


        }
    }
</script>