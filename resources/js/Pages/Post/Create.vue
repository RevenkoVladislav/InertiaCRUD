<script>
import { Link } from '@inertiajs/vue3';
import MainLayout from "@/Layouts/MainLayout.vue";
export default {
    name: "Create",
    components: {
        Link
    },

    props: [
      'errors'
    ],

    layout: MainLayout,

    data() {
        return {
            title: '',
            content: '',
        }
    },

    methods: {
        store() {
            this.$inertia.post('/posts', {title: this.title, content: this.content});
        }
    }
}
</script>

<template>
        <h1 class="text-lg mb-4">
            Create
        </h1>
        <div class="mb-4">
            <Link :href="route('post.index')" class="text-sm text-sky-500">
                Back
            </Link>
        </div>
        <form @submit.prevent="store">
            <div class="mb-4">
                <input v-model="title"
                    class="rounded-full w-full border-gray-300"
                    type="text" placeholder="title">
                <div v-if="errors.title" class="text-red-600 text-sm">
                    {{ errors.title}}
                </div>
            </div>
            <div class="mb-4">
                <textarea v-model="content"
                    class="rounded-full w-full border-gray-300"
                    name="content" placeholder="content"></textarea>
                <div v-if="errors.content" class="text-red-600 text-sm">
                    {{ errors.content}}
                </div>
            </div>
            <div class="mb-4">
                <button class="ml-auto bg-sky-500 block p-2 w-32 rounded-full text-center text-white hover:bg-white hover:text-sky-500 border border-sky-500"
                    type="submit">Store</button>
            </div>
        </form>
</template>

<style scoped>

</style>
