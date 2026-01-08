<script>
import { Link } from '@inertiajs/vue3';
export default {
    name: "Index",
    components: {
        Link
    }
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
    </div>
</template>

<style scoped>

</style>
