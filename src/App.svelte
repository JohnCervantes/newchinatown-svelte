<script>
  import Header from "./lib/Header.svelte";
  import Main from "./lib/Main.svelte";
  import Footer from "./lib/Footer.svelte";
  import Page from "./Menu.svelte";

  import { Router, Route } from 'svelte-tiny-router';

</script>



<Header/>
<Router>
  <Route path="/" component={Main} />
  <Route path="/menu" component={Page} />
</Router>
<Footer/>