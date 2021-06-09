<template>
    <div class="mt-4">
        <hr>
        <h6>TO DO</h6>
        <div v-for="(item, index) in items" :key="index" class="card mt-2">
            <div class="card-body text-secondary">
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault">
                    <label class="form-check-label" for="flexCheckDefault">
                        {{ item.item }}
                    </label>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'ToDos',

        props: {
            items: Array
        }
    }
</script>