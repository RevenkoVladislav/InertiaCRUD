<script>
import { Link } from '@inertiajs/vue3';
import MainLayout from "@/Layouts/MainLayout.vue";
export default {
    name: "Create",
    components: {
        Link
    },

    props: [
        'post'
    ],

    layout: MainLayout,

    data() {
        return {
            id: this.post.id,
            title: this.post.title,
            content: this.post.content,
        }
    },

    methods: {
        update() {
            this.$inertia.patch(`/posts/${this.id}`, {title: this.title, content: this.content});
        }
    }
}
</script>

<template>
        <h1 class="text-lg mb-4">
            Edit
        </h1>
        <div class="mb-4">
            <Link :href="route('post.index')" class="text-sm text-sky-500">
                Back
            </Link>
        </div>
        <form @submit.prevent="update">
            <div class="mb-4">
                <input v-model="title"
                    class="rounded-full w-full border-gray-300"
                    type="text" placeholder="title">
            </div>
            <div class="mb-4">
                <textarea v-model="content"
                    class="rounded-full w-full border-gray-300"
                    name="content" placeholder="content"></textarea>
            </div>
            <div class="mb-4">
                <button class="ml-auto bg-sky-500 block p-2 w-32 rounded-full text-center text-white hover:bg-white hover:text-sky-500 border border-sky-500"
                    type="submit">Update</button>
            </div>
        </form>
</template>

<style scoped>

</style>
