<script lang="ts">
  import { SunMoon } from "@lucide/svelte";

  function toggler() {
    const newMode =
      document.documentElement.getAttribute("data-mode") === "dark"
        ? "light"
        : "dark";

    document.documentElement.setAttribute("data-mode", newMode);
  }
</script>

<button onclick={toggler}>
  <SunMoon />
</button>
