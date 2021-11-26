<script>
  import { onMount } from "svelte";
  import Timeline from "../components/Timeline.svelte";
  import Sidebar from "../components/Sidebar.svelte";
  import Header from "../components/Header.svelte";
  import Main from "../components/Main.svelte";

  let data = {};
  const API =
    "https://api-pugstagram.herokuapp.com/?nickname=MiguelAngelMP&name=Miguel%20Angel";

  onMount(async () => {
    const response = await fetch(API);
    data = await response.json();
    console.log(data);
  });
</script>

<Header />
<Main>
  <Timeline posts={data.posts} />
  <Sidebar {...data.user} />
</Main>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Lato:wght@300;400&display=swap");
  @import url("https://fonts.googleapis.com/css2?family=Pacifico&display=swap");
  :global(body) {
    background-color: #fafafa;
    color: rgba(38, 38, 38, 0.7);
    font-family: "Lato", sans-serif;
    margin: 0;
    padding: 0;
  }
  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;
  }
</style>
