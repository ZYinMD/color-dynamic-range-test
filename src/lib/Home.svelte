<script lang="ts">
  import ColorBlock from "$lib/ColorBlock.svelte";
</script>

<h1>color dynamic range test</h1>
<p>
  Helps see if the setting of <span class="blue">Color Dynamic Range</span> (aka
  Output Dynamic Range, HDMI Dynamic Range) is mismatched between your GPU and monitor.
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
    Turn off "Night Light" or "Night Shift" on your system, which reduces blue
    light at night.
  </li>
  <li>
    In graphics settings, if you can choose between RGB and YCBCR_42X, choose
    RGB.
  </li>
</ul>
<p>
  Color dynamic range can be set to either <strong>"limited"</strong> or
  <strong>"full"</strong>. Both your GPU and monitor could have this setting.
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
    If you see 2 shades of whites and 2 shades of blacks, then your monitor is
    also <strong>full</strong>, you should leave it that way.
  </li>
  <li>
    If you see only 1 shade of white and 1 shade of black, then your monitor is
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
    If you see 2 shades of whites and 2 shades of blacks, then your GPU is also <strong
      >limited</strong
    >. You should continue to set monitor to
    <strong>limited</strong>.
  </li>
  <li>
    If you see only 1 shade of white and 1 shade of black, then your GPU is
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
  span.blue {
    color: rgb(70, 125, 160);
  }
</style>
