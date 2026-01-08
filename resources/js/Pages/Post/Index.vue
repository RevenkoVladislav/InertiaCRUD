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
        <h1 class="text-lg">
            Posts
        </h1>
        <div>
            <Link class="bg-sky-500 rounded-full text-center text-white">Add Post</Link>
        </div>
    </div>
</template>

<style scoped>

</style>
