<script>
import { Link } from '@inertiajs/vue3';
import MainLayout from "@/Layouts/MainLayout.vue";
export default {
    name: "Index",
    components: {
        Link
    },

    layout: MainLayout,

    props: [
        'post',
    ],
}
</script>

<template>
        <h1 class="text-lg mb-8" v-if="post.title">
            Post: {{ post.title }}
        </h1>

        <div class="mb-2">
            <Link :href="route('post.index')" class="text-sm text-sky-500">
                Back
            </Link>
        </div>

        <div v-if="post">
            <div class="mt-8 pt-8 border-t border-gray-300">
                <div>id: {{ post.id}}</div>
                <div>title: {{ post.title}}</div>
                <div>content: {{ post.content}}</div>
                <div class="text-sm text-right">{{ post.date }}</div>
            </div>
        </div>
</template>

<style scoped>

</style>
