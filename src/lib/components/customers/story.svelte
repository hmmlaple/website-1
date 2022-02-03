<script type="ts">
  import Section from "../section.svelte";
  export let bannerImg: string;
  export let text: string;
  export let image: { src: string; alt: string };
</script>

<style lang="postcss">
  :global(nav.toc) {
    @apply hidden;
  }

  :global(blockquote) {
    @apply bg-transparent border-l-4 border-orange-900 pl-xx-small py-0 sm:m-small rounded-none !important;
  }

  :global(blockquote) :global(p) {
    @apply text-h6 text-black font-semibold !important;
  }
</style>

<Section>
  <div class="text-center max-w-3xl mx-auto">
    <h2 class="h2">Full customer story</h2>
    <p>{text}</p>

    {#if image}
      <img src={image.src} alt={image.alt} class="rounded-t-2xl mt-small" />
    {/if}
  </div>

  <div class="prose max-w-3xl mx-auto mt-x-large">
    <div
      class="h-36 bg-cover bg-center rounded-t-2xl mb-small"
      style="background-image: url({bannerImg});"
    />
    <slot />
  </div>
</Section>
