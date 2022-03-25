<template>
    <main>
        <div class="container-fluid d-flex justify-content-center flex-wrap">
            <div
                class="post m-3 p-5"
                v-for="(post, index) in posts"
                :key="index"
            >
                <h2>{{ post.title }}</h2>
                <p>{{ post.content }}</p>
            </div>
        </div>
    </main>
</template>

<script>
export default {
    name: "Main",
    data() {
        return {
            posts: [],
        };
    },
    created() {
        axios.get("/api/posts").then((apirisp) => {
            this.posts = apirisp.data;
        });
    },
};
</script>

<style lang="scss" scoped>
.post {
    height: 300px;
    width: 450px;
    background: #fff;
    box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);
}
</style>
