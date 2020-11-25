<template>

    <div class="row" v-if="userid != 0">
        <div class="col-12 col-sm-6 col-md-4" v-for="post in filteredPosts" :key="post.id">
            <div>
                <h4 class="post-title">{{post.title}}</h4>
            </div>
            <div class="post-body">
                    {{post.body}}
            </div>
            <hr/>
        </div>
    </div>

</template>
<script>
export default {
    name: 'Posts',
    props:  {
        userid: Number,
        settings: {},
    },
    data() {
        return {
            posts: null
        }
    },
    computed: {
        filteredPosts() {
            let posts = [];
            for (let post of this.posts) {
                if (post.userId == this.userid) {
                    posts.push(post);
                }
                if (posts.length == 10) {
                    break;
                }
            }
            return posts;
        }
    },
    mounted() {
        this.getPosts();
    },
    methods: {
        async getPosts() {
            const response = await fetch("https://jsonplaceholder.typicode.com/posts")
            this.posts = await response.json();
        },
    },
}
</script>
<style scoped lang="scss">
.post-title {
    text-align:left;
    margin-top: 3px;
}
.post-body {
    text-align: left;
}
</style>
