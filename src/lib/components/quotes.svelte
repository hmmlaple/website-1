<script lang="ts">
  import type { Quote } from "$lib/types/quote.type";
  export let quotes: Quote[];
  let selectedQuote: Quote = quotes[0];
</script>

<style lang="postcss">
  .quotes {
    max-width: 1000px !important;
  }

  .quote {
    height: 350px;

    @media (max-width: 1040px) {
      height: 300px;
    }

    @media (max-width: 890px) {
      @apply block;
      height: auto;
    }
  }

  .quote .text {
    @media (max-width: 890px) {
      height: 230px;
    }
    @media (max-width: 630px) {
      height: 270px;
    }
    @media (max-width: 430px) {
      height: 310px;
    }
  }
</style>

<div
  class="quotes bg-off-white shadow-normal rounded-2xl sm:rounded-5xl pt-micro px-0 sm:px-xx-small sm:pt-x-small sm:pb-micro lg:p-small mx-auto"
>
  <div class="flex justify-around flex-wrap max-w-3xl mx-auto">
    {#each quotes as quote}
      <button
        class="flex justify-center py-3 group mx-xx-small sm:mx-micro"
        on:mouseenter={() => (selectedQuote = quote)}
        on:click={() => (selectedQuote = quote)}
      >
        <img
          src={quote.companyLogo.src}
          alt={quote.companyLogo.alt}
          class="h-7 w-20 sm:h-9 sm:w-28 transition group-hover:opacity-100 group-focus:opacity-100 group-focus:filter-none group-hover:filter-none"
          class:opacity-60={selectedQuote !== quote}
          class:grayscale={selectedQuote !== quote}
        />
      </button>
    {/each}
  </div>
  <div
    class="quote flex flex-col md:flex-row mt-xx-small lg:mt-small text-left pb-small md:pb-macro"
  >
    <div>
      <img
        src={selectedQuote.img.src}
        alt={selectedQuote.img.alt}
        class="sm:max-w-xs sm:rounded-3xl lg:max-w-sm xl:max-w-md w-full mx-auto"
      />
    </div>
    <div
      class="text flex-1 max-w-lg pt-micro px-xx-small sm:pl-x-small lg:pl-small lg:pr-0 mx-auto"
    >
      <p class="text-large">
        &ldquo;{selectedQuote.text}&rdquo;
      </p>

      <p class="font-bold mt-xx-small">
        {selectedQuote.author}, {selectedQuote.jobTitle}
      </p>
    </div>
  </div>
</div>
