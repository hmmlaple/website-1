<script context="module">
  export const prerender = true;
</script>

<script>
  import Cta from "$lib/components/support/cta.svelte";
  import PopularArticles from "$lib/components/support/popular-articles.svelte";
  import OpenGraph from "$lib/components/open-graph.svelte";
  import { cards } from "$lib/contents/support";
  import Resources from "$lib/components/resources.svelte";
  import SectionCommon from "$lib/components/section-common.svelte";
  import Header from "$lib/components/header.svelte";
  import Search from "$lib/components/docs/search.svelte";
</script>

<OpenGraph
  data={{
    description: "Need help?",
    title: "Support",
  }}
/>

<Header title="Need help?">
  <Search
    slot="content"
    placeholder="Search Documentation"
    class="text-left py-7 sm:pl-medium h-14"
    containerClasses="roun max-w-lg mx-auto shadow rounded-xl"
    iconClasses="h-6 w-6 left-4 sm:left-5"
  />
</Header>
<Cta />
<SectionCommon title="Helpful Resources">
  <Resources {cards} slot="content" />
</SectionCommon>
<PopularArticles />
