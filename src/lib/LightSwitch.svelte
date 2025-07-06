<script lang="ts">
  import { SunMoon } from "@lucide/svelte";

  function toggler() {
    const newMode =
      document.documentElement.getAttribute("data-mode") === "dark"
        ? "light"
        : "dark";

    document.documentElement.setAttribute("data-mode", newMode);
    // TODO: LOOK AT SETTING THESE IN LOCAL STORAGE SO IT PERSISTS
  }
</script>

<button onclick={toggler}>
  <SunMoon />
</button>
