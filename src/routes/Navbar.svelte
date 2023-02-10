<script>
  import { page } from "$app/stores";

  const navs = [
    {
      title: "Home",
      href: "/",
    },
    {
      title: "About",
      href: "/about",
    },
    {
      title: "Services",
      href: "/services",
    },
    {
      title: "Contact",
      href: "/contact",
    },
  ];

  let currentRoute;
  $: currentRoute = $page.route.id;
</script>

<nav>
  <div class="container">
    <h1>Start Bootstrap</h1>
    <ul>
      {#each navs as { title, href }}
        <li>
          <a {href} class:active={currentRoute === href} {title}>{title}</a>
        </li>
      {/each}
    </ul>
  </div>
</nav>

<style>
  h1 {
    margin: 0;
    font-size: 1.2em;
    font-weight: normal;
  }
  nav {
    background-color: #212529;
    color: #fff;
  }
  .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem 2rem;
  }
  ul {
    list-style: none;
    display: flex;
    gap: 2rem;
    padding: 0;
    margin: 0;
    margin-left: auto;
    font-size: 0.98em;
  }
  li {
    /* style to li uppercase text and bold and a gap */
    text-transform: uppercase;
    font-weight: normal;
  }
  a {
    /* style to a text-decoration none and color */
    text-decoration: none;
    color: #ddd;
  }
  .active {
    /* style to active class */
    font-weight: bold;
    color: #fff;
    border-bottom: 4px solid #fff;
    padding-bottom: 0.5em;
  }
</style>
