<script>
import { Link } from '@inertiajs/vue3';
export default {
    name: "Index",
    components: {
        Link
    },

    props: [
        'posts',
    ],
}
</script>

<template>
    <div class="w-96 mx-auto pt-8">
        <h1 class="text-lg mb-8">
            Posts
        </h1>
        <div>
            <Link :href="route('post.create')" class="bg-sky-500 block p-2 w-32 rounded-full text-center text-white hover:bg-white hover:text-sky-500 border border-sky-500">Add Post</Link>
        </div>
        <div v-if="posts">
            <div class="mt-8 pt-8 border-t border-gray-400" v-for="post in posts" :key="post.id">
                <div>id: {{ post.id}}</div>
                <div>title: {{ post.title}}</div>
                <div>content: {{ post.content}}</div>
                <div>{{ post.date }}</div>
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>
