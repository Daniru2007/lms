<script>
    import { Router, Route, Link } from "svelte-routing";
    export let url = "";
    let dark = true;
    $: theme = dark ? "dark" : "light";
    $: icon = dark ? "🌛" : "🌞";
    $: ellipse = `<svg class="ellipse ${theme}" width="231" height="251" viewBox="0 0 231 251" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M230.271 192.935C217.172 213.256 198.461 229.342 176.404 239.244C154.348 249.146 129.894 252.439 106.004 248.725C82.1138 245.01 59.8138 234.447 41.8054 218.316C23.7971 202.184 10.8534 181.176 4.54252 157.837C-1.76835 134.499 -1.17551 109.83 6.24919 86.8216C13.6739 63.8129 27.6118 43.4511 46.3743 28.2032C65.1367 12.9553 87.9184 3.47578 111.959 0.913075C136 -1.64963 160.268 2.81451 181.823 13.7646L125.209 125.209L230.271 192.935Z" fill="#D9D9D9"/>
</svg>`;
    $: lines = `<svg class="lines ${theme}" width="939" height="323" viewBox="0 0 939 323" fill="none" xmlns="http://www.w3.org/2000/svg">
<line x1="349.004" y1="313.778" x2="1.02809" y2="315" stroke="#DDF1FF" stroke-width="17"/>
<line y1="-8" x2="938" y2="-8" transform="matrix(-1 0 0 1 939 16)" stroke="#DDF1FF" stroke-width="17"/>
<line y1="-8" x2="641" y2="-8" transform="matrix(-1 0 0 1 642 65)" stroke="#DDF1FF" stroke-width="17"/>
<line y1="-8" x2="755.006" y2="-8" transform="matrix(-0.99996 -0.00897779 0.0124151 -0.999923 755.976 123)" stroke="#DDF1FF" stroke-width="17"/>
</svg>`;
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
        {@html ellipse}
        {@html lines}
        <div class="blur-box {theme}">
            <div>
                <h1>Wellcome to LMS</h1>
                <p>
                    LMS is a website for students and teachers to make their
                    lives alot better with fun learning and entertainment
                </p>
            </div>
        </div>
    </section>
</body>

<style>
</style>
