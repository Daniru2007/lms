<script>
    import { Router, Route, Link } from "svelte-routing";
    export let url = "";
    let dark = true;
    $: theme = dark ? "dark" : "light";
    $: icon = dark ? "🌛" : "🌞";
</script>

<body class={theme}>
    <Router {url}>
        <nav class="nav-bar {theme}">
            <div class="div0" />
            <div class="div1">
                <Link to="/">Home</Link>
                <Link to="/">Courses</Link>
                <Link to="/">Colleges</Link>
            </div>

            <div>
                <button
                    class="change-theme {theme}"
                    on:click={() => (dark = !dark)}>{icon}</button
                >
            </div>

            <div class="div2">
                <Link to="/">Sign in</Link>
                <Link to="/">Join</Link>
            </div>
        </nav>
    </Router>

    <section class="home {theme}">
        <div class={theme}><h1>Hello</h1></div>
    </section>
</body>

<style>
</style>
