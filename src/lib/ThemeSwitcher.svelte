<script lang="ts">
  let selected: string = $state("mint");

  $effect(() => {
    const val = selected;
    document.documentElement.setAttribute("data-theme", val);
  });

  // function toggler(selected: string) {
  //   const newMode =

  //   // document.documentElement.setAttribute("data-theme", newMode);
  // }
</script>

<form class="mx-auto w-full max-w-md space-y-4">
  <!-- Default -->
  <select class="select" bind:value={selected}>
    <option value="catppuccin">Catppuccin</option>
    <option value="cerberus">Cerberus</option>
    <option value="concord">Concord</option>
    <option value="crimson">Crimson</option>
    <option value="fennec">Fennec</option>
    <option value="hamlindigo">Hamlindigo</option>
    <option value="legacy">Legacy</option>
    <option value="mint">Mint</option>
    <option value="modern">Modern</option>
    <option value="mona">Mona</option>
    <option value="nosh">Nosh</option>
    <option value="nouveau">Nouveau</option>
    <option value="pine">Pine</option>
    <option value="reign">Reign</option>
    <option value="rocket">Rocket</option>
    <option value="rose">Rose</option>
    <option value="sahara">Sahara</option>
    <option value="seafoam">Seafoam</option>
    <option value="terminus">Terminus</option>
    <option value="vintage">Vintage</option>
    <option value="vox">Vox</option>
    <option value="wintry">Wintry</option>
  </select>
</form>
