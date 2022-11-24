<script>
    import { Router, Route, Link } from "svelte-routing";
    export let url = "";
    let dark = true;
    $: theme = dark ? "dark" : "light";
</script>

<Router {url}>
    <nav class="nav-bar {theme}">
        <div class="div0" />
        <div class="div1">
            <Link to="/">Home</Link>
            <Link to="/">Courses</Link>
            <Link to="/">Colleges</Link>
        </div>

        <div class="div2">
            <Link to="/">Sign in</Link>
            <Link to="/">Join</Link>
        </div>
    </nav>
</Router>

<button on:click={() => (dark = !dark)}> switch themes </button>

<style>
</style>
