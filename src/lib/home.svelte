<script lang="ts">
  import ColorBlock from "$lib/ColorBlock.svelte";
</script>

<h1>color dynamic range test</h1>
<p>
  Test if the color dynamic range setting is mismatched between your GPU and
  monitor.
</p>

<div class="colors-blocks">
  <ColorBlock color={255} />
  <ColorBlock color={240} />
  <ColorBlock color={15} />
  <ColorBlock color={0} />
</div>

<p>For best result, you should</p>
<ul>
  <li>
    Turn off "light shift" or "night light" on your system, which reduces blue
    color at night.
  </li>
  <li>
    In graphics settings, if you can choose between RGB and YCBCR_42X, choose
    RGB.
  </li>
</ul>
<p>
  Color dynamic range can be set to either <strong>"limited"</strong> or
  <strong>"full"</strong>. Both your GPU and your monitor <em>may</em> have this
  setting.
</p>
<p>
  <strong>Scenario 1: </strong> if your GPU and monitor both have this setting:
</p>
<ul>
  <li>You should set both to <strong>full</strong>.</li>
</ul>
<p>
  <strong>Scenario 2: </strong> if your GPU has this setting, but your monitor doesn't:
</p>
<ul>
  <li>Set your GPU to <strong>full</strong>, then look at this page.</li>
  <li>
    If you see 4 different colors, 2 whites and 2 blacks, then your monitor is
    also <strong>full</strong>.
  </li>
  <li>
    If you see only 1 type of white and 1 type of black, then your monitor is
    <strong>limited</strong>. You should set your GPU to
    <strong>limited</strong> too.
  </li>
</ul>
<p>
  <strong>Scenario 3: </strong> if your monitor has this setting, but GPU doesn't:
</p>
<ul>
  <li>Set to <strong>limited</strong> on monitor, then look at this page.</li>
  <li>
    If you see 4 different colors, 2 whites and 2 blacks, then your GPU is also <strong
      >limited</strong
    >. You should continue to set monitor to
    <strong>limited</strong>.
  </li>
  <li>
    If you see only 1 type of white and 1 type of black, then your GPU is
    <strong>full</strong>. You should set your monitor to
    <strong>full</strong> too.
  </li>
</ul>

<style>
  .colors-blocks {
    width: fit-content;
  }
  .colors-blocks :global(div:first-child) {
    border: 1px solid rgb(240, 240, 240);
  }
  ul {
    padding-left: 20px;
    margin-top: -10px;
  }
  li {
    line-height: 1.4;
    margin: 4px 0;
  }
</style>
