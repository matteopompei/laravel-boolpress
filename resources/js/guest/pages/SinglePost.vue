<template>
    <div>
        <div class="container my-5">
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

            <router-link :to="{ name: 'home' }" class="btn btn-primary"
                >Indietro</router-link
            >
        </div>
    </div>
</template>

<script>
export default {
    name: "SinglePost",
    data() {
        return {
            post: {},
        };
    },
    created() {
        axios.get(`/api/posts/${this.$route.params.slug}`).then((response) => {
            this.post = response.data;
        });
    },
};
</script>

<style lang="scss" scoped>
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
</style>
