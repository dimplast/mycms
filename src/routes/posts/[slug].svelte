<script context="module">
    export const load = async ({fetch, page: {params}}) => {
        const {slug} = params
        const res = await fetch(`/posts/${slug}.json`)
        if (res.ok){
            const {post} = await res.json()
            return {
                props: {post}
            }
        }

    }
</script>

<script>
    export let post
</script>

<svelte:head>
    <title>{post.title}</title>
</svelte:head>

{JSON.stringify(post)}

