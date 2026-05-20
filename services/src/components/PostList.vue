<template>
    <h1>Listado de posts</h1>
    <ul class="post-list">
        <li v-for="post in posts" :key="post.id">{{ post.title }}</li>
    </ul>
</template>

<script lang="ts">
    import PostService from '@/services/PostService.vue';
    import { defineComponent, onMounted } from 'vue';

    export default defineComponent({
        name: 'PostList',
        setup() {
                const service = new PostService();
                const posts = service.getPosts()

                onMounted(async () => {
                    await service.fetchAll()
                })

                return {posts}

        }
    })
</script>

<style scoped>

</style>