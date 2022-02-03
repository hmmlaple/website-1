<script lang="ts">
  import PostPreview from "../blog/post-preview.svelte";

  import SectionCommon from "../section-common.svelte";
  export let customers: any;
  export let title: string;
  export let text: string = "";
  export let id: string = "";
</script>

<SectionCommon {title} {text} {$$restProps} {id}>
  <div
    slot="content"
    class="grid justify-center md:grid-cols-2 gap-xx-small mx-auto mt-small"
    style="max-width: 860px"
  >
    {#each customers as { title, excerpt, image, slug }}
      <PostPreview
        post={{
          title,
          excerpt,
          slug,
          image,
          teaserImage: image,
        }}
        headlineOrder="h3"
        type="customers"
        isMostRecent={true}
        availability={!(slug === "customer-io")}
      />
    {/each}
  </div>
</SectionCommon>
