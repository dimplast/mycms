<script context="module">
    export const load = async ({fetch}) => {
        const res = await fetch('/posts.json')
        if (res.ok){
            const {posts} = await res.json()
            return {
                props: {posts}
            }
        }
    }
</script>

<script>
    export let posts
</script>

<svelte:head>
    <title>MyCms</title>
</svelte:head>

<ul>
{#each posts as {title,slug}}
    <li>
        <a href="{`/posts/${slug}`}">{title}</a>
    </li>
{/each}
</ul>




