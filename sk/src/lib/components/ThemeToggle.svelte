<script>
  import { theme } from "../app/themeStore";

  function toggleTheme() {
    const newTheme = $theme === "theme-dark" ? "theme-light" : "theme-dark";
    $theme = newTheme;

    if (newTheme === "theme-dark") {
      document.getElementById("theme-dark-stylesheet").media = "all";
      document.getElementById("theme-light-stylesheet").media = "none";
    } else {
      document.getElementById("theme-light-stylesheet").media = "all";
      document.getElementById("theme-dark-stylesheet").media = "none";
    }
  }
</script>

<nav>
  <button on:click={toggleTheme}>Toggle</button>
</nav>

<style lang="scss">
  nav {
    button {
      padding: 0.5em 1em;
      margin: 0;
      background: var(--background-alt);
      border-bottom: solid var(--background);
    }
  }
</style>
