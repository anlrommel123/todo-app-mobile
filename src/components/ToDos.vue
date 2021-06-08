<template>
    <div>
        <div class="card mt-5">
            <div v-for="(item, index) in items" :key="index" class="card-body text-secondary">
                This is some text within a card body.
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'ToDos',
        props: {
            items: Array
        },

        mounted() {
          //console.log(this.items)
          //this.items.push(5)
        }
    }
</script>