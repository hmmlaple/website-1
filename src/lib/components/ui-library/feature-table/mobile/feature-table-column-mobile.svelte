<script lang="ts">
  import FeatureTableItemMobile from "./feature-table-item-mobile.svelte";
  import FeatureTableHeaderMobile from "./feature-table-header-mobile.svelte";
  import type { FeatureTableColumn } from "../feature-table.types";

  export let featureData: FeatureTableColumn;

  const shadow = featureData.isHighlighted ? "shadow-brand" : "shadow-normal";

  let isShown: boolean = false;
</script>

<div class="p-x-small bg-off-white {shadow} rounded-3xl max-w-[400px] mx-auto">
  <FeatureTableHeaderMobile headerData={featureData.header} bind:isShown>
    {#if isShown}
      <section
        class="grid grid-cols-1 auto-rows-[4rem] gap-8 pt-4 mb-4 inner-grid-mobile"
      >
        {#each featureData.items as item}
          <FeatureTableItemMobile definition={item} />
        {/each}
        {#if featureData.link}
          <div class="flex justify-center items-center">
            <a
              href={featureData.link.href}
              class="btn-cta"
              class:btn-primary={featureData.isHighlighted}
              >{featureData.link.label}</a
            >
          </div>
        {/if}
      </section>
    {/if}
  </FeatureTableHeaderMobile>
</div>
