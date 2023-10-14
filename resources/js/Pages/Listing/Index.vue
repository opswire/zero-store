<script setup>
import ListingAddress from "@/Components/ListingAddress.vue";
import {Link} from "@inertiajs/vue3";

defineProps({
    listings: Array,
})
</script>

<template>
    <div v-for="listing in listings" :key="listing.id">
        <div>
            <Link :href="route('listings.show', {listing: listing.id})">
                <ListingAddress :listing="listing"/>
            </Link>
        </div>
        <div>
            <Link :href="route('listings.edit', {listing: listing.id})">Edit</Link>
        </div>
        <div>
            <Link :href="route('listings.destroy', {listing: listing.id})" method="DELETE"
                  as="button">Delete</Link>
        </div>
    </div>
</template>

<style scoped>

</style>
