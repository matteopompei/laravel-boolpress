<template>
    <div class="container-fluid d-flex justify-content-center flex-wrap">
        <div class="post m-3 p-5" v-for="post in posts" :key="post.slug">
            <h3>{{ post.title }}</h3>
            <div v-if="post.category" class="category">
                {{ post.category.name }}
            </div>
            <div class="tags">
                <ul>
                    <li v-for="tag in post.tags" :key="tag.slug">
                        {{ tag.name }}
                    </li>
                </ul>
            </div>
            <p>{{ post.content }}</p>

            <router-link
                :to="{ name: 'single-post', params: { slug: post.slug } }"
                >Visualizza post</router-link
            >
        </div>
    </div>
</template>

<script>
export default {
    name: "Posts",
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
main {
    margin-top: 50px;

    .post {
        height: 500px;
        width: 450px;
        background: #fff;
        box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);

        .category {
            margin: 5px 0;
            padding: 3px 10px;
            width: fit-content;
            background: #527fe0;
            border-radius: 3px;
            color: #fff;
            font-size: 0.8rem;
        }

        .tags {
            width: fit-content;
            margin: 5px 0;

            ul {
                padding: 0;
            }

            li {
                display: inline;
                padding: 3px 10px;
                margin-right: 3px;
                background: #585b62;
                border-radius: 3px;
                color: #fff;
                font-size: 0.7rem;
            }
        }
    }
}
</style>
