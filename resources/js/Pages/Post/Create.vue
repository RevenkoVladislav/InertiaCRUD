<script>
import { Link } from '@inertiajs/vue3';
export default {
    name: "Create",
    components: {
        Link
    }
}
</script>

<template>
    <div class="w-96 mx-auto pt-8">
        <h1 class="text-lg mb-8">
            Create
        </h1>
        <form>
            <div class="mb-4">
                <input class="rounded-full w-full border-gray-300"
                    type="text" placeholder="title">
            </div>
            <div class="mb-4">
                <textarea class="rounded-full w-full border-gray-300"
                    name="content" placeholder="content"></textarea>
            </div>
            <div class="mb-4">
                <button class="ml-auto bg-sky-500 block p-2 w-32 rounded-full text-center text-white hover:bg-white hover:text-sky-500 border border-sky-500"
                    type="submit">Store</button>
            </div>
        </form>
    </div>
</template>

<style scoped>

</style>
