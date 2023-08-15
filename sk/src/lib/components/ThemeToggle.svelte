<script>
    import { theme } from "../app/themeStore";
  
    function toggleTheme() {
      const newTheme = $theme === "theme-dark" ? "theme-light" : "theme-dark";
      $theme = newTheme;
  
      const lightStylesheet = document.getElementById("theme-light-stylesheet");
      const darkStylesheet = document.getElementById("theme-dark-stylesheet");
  
      if (newTheme === "theme-dark") {
        if (darkStylesheet && 'media' in darkStylesheet) darkStylesheet.media = "all";
        if (lightStylesheet && 'media' in lightStylesheet) lightStylesheet.media = "none";
      } else {
        if (lightStylesheet && 'media' in lightStylesheet) lightStylesheet.media = "all";
        if (darkStylesheet && 'media' in darkStylesheet) darkStylesheet.media = "none";
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
