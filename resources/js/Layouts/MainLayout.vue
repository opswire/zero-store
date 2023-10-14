<script setup>
import {Link, usePage} from '@inertiajs/vue3'
import {computed} from "vue";

const page = usePage()
const flashSuccess = computed(
    () => page.props.flash.success,
)
</script>

<template>
    <Link :href="route('listings.index')">Index Page</Link>&nbsp;
    <Link :href="route('listings.create')">Create Page</Link>&nbsp;
    <div v-if="flashSuccess" class="success">
        {{ flashSuccess }}
    </div>
    <slot></slot>
</template>

<style scoped>
.success {
    background-color: green;
    color: white;
}
</style>
