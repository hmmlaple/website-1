<script context="module">
  export const prerender = true;
</script>

<script>
  import MeetBobAndAlice from "$lib/components/local-development/meet-bob-and-alice.svelte";
  import Explore from "$lib/components/explore.svelte";
  import GitpodVsLocalDevelopmentPost from "$lib/components/local-development-post.svelte";
  import OpenGraph from "$lib/components/open-graph.svelte";
  import CalloutSecondary from "$lib/components/callout-secondary.svelte";
  import Header from "$lib/components/header.svelte";
  import { benefits } from "$lib/contents/local-development";
  import CardSmall from "$lib/components/card/card-small.svelte";
</script>

<style lang="postcss">
  div {
    grid-template-columns: repeat(auto-fill, 316px);

    @media (max-width: 1460px) {
      @apply max-w-4xl mx-auto;
    }

    @media (max-width: 400px) {
      grid-template-columns: none;
    }
  }
</style>

<OpenGraph
  data={{
    title: "Gitpod vs local development",
    description:
      "Why should you move your dev environment to the cloud? Here is the answer.",
  }}
/>

<Header
  title="Gitpod vs local development"
  text="Why should you move your dev environment to the cloud? Here is the answer."
  fullWidth={true}
>
  <div slot="content" class="grid gap-micro justify-center mt-small">
    {#each benefits as benefit}
      <CardSmall card={benefit} />
    {/each}
  </div>
</Header>

<MeetBobAndAlice />

<CalloutSecondary
  title="Feel the difference"
  text="Spin up fresh, automated dev environments for each task, in the cloud, in
  seconds."
/>

<GitpodVsLocalDevelopmentPost
  title="Full blog post"
  text={`
  Read the full blog post by <a href="https://twitter.com/mikenikles" target="_blank">Mike Nikles</a>, our Senior Developer Success Engineer, sharing the story of moving to the cloud.
  `}
/>

<Explore />
