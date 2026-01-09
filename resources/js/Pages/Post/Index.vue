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
        'posts',
    ],

    methods: {
        deletePost(id) {
            this.$inertia.delete(`/posts/${id}`);
        },
    },
}
</script>

<template>
        <h1 class="text-lg mb-8 text-center">
            Posts
        </h1>
        <div>
            <Link :href="route('post.create')" class="bg-sky-500 block p-2 w-32 rounded-full text-center text-white hover:bg-white hover:text-sky-500 border border-sky-500">Add Post</Link>
        </div>
        <div v-if="posts">
            <div class="mt-8 pt-8 border-t border-gray-300" v-for="post in posts" :key="post.id">
                <div>id: {{ post.id}}</div>
                <div>title: {{ post.title}}</div>
                <div>content: {{ post.content}}</div>
                <div class="text-sm text-right">{{ post.date }}</div>
                <div class="text-sm text-right text-sky-500">
                    <Link :href="route('post.show', post.id)">Show</Link>
                </div>
                <div class="text-sm text-right text-green-600">
                    <Link :href="route('post.edit', post.id)">Edit</Link>
                </div>
                <div class="text-sm cursor-pointer text-right text-red-700">
                    <p @click="deletePost(post.id)">Delete</p>
                </div>
            </div>
        </div>
</template>

<style scoped>

</style>
