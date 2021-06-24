<template>
    <div class="mt-4">
        <hr>
        <h6>COMPLETED</h6>
        <div v-for="(item, index) in items" :key="index" v-show="item.isChecked" class="card mt-2">
            <div class="card-body text-secondary">
                <div class="form-check">
                    <input @click="checkItem(index)" class="form-check-input" type="checkbox" :checked="item.isChecked">
                    <label class="form-check-label" for="flexCheckDefault">
                         <s>{{ item.item }}</s>
                    </label>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'completed-item',

        props: {
            items: Array
        },

        methods: {
            checkItem(index) {
                this.$emit('checkItem', index);

                this.$emit('openToast', 'You unchecked the completed task.');
            }
        }

    }
</script>