<script lang="ts">
  export let color: number;
</script>

<!-- @component a grey block on screen, pass in the color -->
<div class="component" style:--color={color}>
  <span class="text">{color},{color},{color}</span>
</div>

<style>
  .component {
    background-color: rgb(var(--color), var(--color), var(--color));
    font-size: 13px;
    display: grid;
    place-items: center;
    height: 100px;
    width: 200px;
  }
  .text {
    color: white;
    mix-blend-mode: difference;
  }
</style>
