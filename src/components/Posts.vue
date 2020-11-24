<template>
    <div v-if="userid != 0">
        <div v-for="post in filteredPosts" :key="post.id">
            <div>
                <h4>{{post.title}}</h4>
            </div>
            <div v-scroll="handleScroll">
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
