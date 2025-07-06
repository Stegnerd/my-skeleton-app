<script>
  import LightSwitch from "$lib/LightSwitch.svelte";
  import ThemeSwitcher from "$lib/ThemeSwitcher.svelte";
</script>

<h1>Welcome to SvelteKit</h1>
<p>
  Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the
  documentation
</p>

<div class="flex items-center gap-4">
  <!-- A standard button -->
  <button type="button" class="btn preset-filled">Button</button>
  <LightSwitch />
  <ThemeSwitcher />
</div>
