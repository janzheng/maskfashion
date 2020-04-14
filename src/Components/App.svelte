<script>
  import Navaid from "navaid";
  import { onDestroy } from "svelte";
  import Nav from "./Nav.svelte";

  import Home from "../routes/Home.svelte";
  import About from "../routes/About.svelte";
  import FourOhFour from "../routes/404.svelte";

  let Route,
    params = {},
    active;
  let uri = location.pathname;
  $: active = uri.split("/")[1] || "home";

  // router, copied from svelte-demo
  // function run(thunk, obj) {
  //   const target = uri;

  //   thunk.then(m => {
  //     if (target !== uri) return;

  //     params = obj || {};

  //     if (m.preload) {
  //       m.preload({ params }).then(() => {
  //         if (target !== uri) return;
  //         Route = m.default;
  //         window.scrollTo(0, 0);
  //       });
  //     } else {
  //       Route = m.default;
  //       window.scrollTo(0, 0);
  //     }
  //   });
  // }

  const router = Navaid("/", () => {
    console.log("404!");
    // run(import('../routes/404.svelte'))
    Route = FourOhFour;
    window.scrollTo(0, 0);
  })
    .on("/", () => {
      // run(import('../routes/Home.svelte')))
      Route = Home;
      window.scrollTo(0, 0);
    })
    .on("/about", () => {
      Route = About;
      window.scrollTo(0, 0);
      // run(import('../routes/About.svelte'))
    })
    // .on('/blog', () => run(import('../routes/Blog.svelte')))
    // .on('/blog/:postid', obj => run(import('../routes/Article.svelte'), obj))
    .listen();

  onDestroy(router.unlisten);
</script>

<style type="text/scss">
  @import "../styles/core";

  // general app styles
  .App {
    width: 100%;
    max-width: 1500px;
    padding: $unit * 2;
    padding-top: 0;
  }

  * {
    font-family: $font-stack;
    font-size: $unit;
    line-height: $line-height;
  }

  :global(h1, h2, h3, h4) {
    font-weight: bold;
    padding-bottom: $unit;
  }
</style>

<main class="App">
  <Nav {active} />
  <svelte:component this={Route} {params} />
</main>
