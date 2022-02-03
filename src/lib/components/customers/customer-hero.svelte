<script lang="ts">
  import CustomerCard from "./customer-card.svelte";

  export let title: string;
  export let text: string;
  export let textMaxWClass: string = "max-w-3xl";
  export let logo: {
    src: string;
    alt: string;
  };
  export let card: {
    image: string;
    details: {
      industry: string;
      plan: string;
      people: {
        title: string;
        text: string;
      };
      website: {
        href: string;
        text: string;
      };
    };
  };
</script>

<style lang="postcss">
  .h1 {
    @apply mb-micro md:mb-xx-small;
  }
</style>

<header
  class="flex flex-col lg:flex-row items-center justify-between max-w-7xl mx-auto mt-small mb-x-large md:my-x-large lg:my-xx-large"
>
  <div class="lg:mr-small mb-small lg:mb-0">
    <header class={textMaxWClass}>
      <p
        class="flex flex-col-reverse sm:flex-row sm:items-center h5 font-bold text-light-grey mb-xx-small"
      >
        <img
          src={logo.src}
          alt={logo.alt}
          class="h-10 w-36 sm:mr-micro mt-macro sm:mt-0"
        />
        <span>Customer story</span>
      </p>
      <h1 class="h1">{title}</h1>
    </header>
    <p class="text-large max-w-3xl">{text}</p>
  </div>
  <CustomerCard {card} />
</header>
