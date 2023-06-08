<script>
    import { base } from '$app/paths';
    import { page } from '$app/stores';
</script>

<header>
    <nav>
        <ul>
            <li class:active={$page.url.pathname === base}>
                <a href={base}>Home</a>
            </li>

            <li class:active={$page.url.pathname === base + '/about'}>
                <a href="{base}/about">About</a>
            </li>
        </ul>
    </nav>
</header>

<main>
    <slot />
</main>

<footer>
    <p>URL of the current site: {$page.url}</p>
</footer>

<style>
    :global(body) {
        margin: 0;
        padding: 0;
        background: #222;
        color: #fff;
        font-family: sans-serif;
    }

    main {
        max-width: 600px;
        padding: 0 1rem;
    }

    footer {
        padding: 0 1rem;
    }

    ul {
        display: flex;
        width: 100%;
        background: #111;
        list-style: none;
        padding: 0;
        margin: 0;
    }

    li {
        color: inherit;
    }

    a {
        display: inline-block;
        text-decoration: none;
        color: inherit;
        padding: 1rem;
    }

    li.active a {
        background: #222;
    }
</style>
