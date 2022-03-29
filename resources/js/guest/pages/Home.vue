<template>
    <div>
        <div class="container my-5">
            <h1>Home Page</h1>
        </div>
        <Posts />
    </div>
</template>

<script>
import Posts from "../components/Posts.vue";

export default {
    name: "Home",
    components: {
        Posts,
    },
};
</script>

<style></style>
