<script lang="ts">
  import Button from '$lib/button/Button.svelte';
</script>

<section
  class="w-full flex flex-col p-10 space-y-24 xl:space-y-48 pb-48"
  id="whats-next"
>
  <h1 class="w-full text-center text-3xl xl:text-6xl uppercase">What's Next</h1>

  <div class="flex w-full h-full justify-center items-end">
    <div class="w-full flex justify-between items-start">
      <div class="flex w-full space-x-8 xl:space-x-48">
        <div class="flex flex-col w-1/2 items-end space-y-12">
          <img src="/next/butterfly.svg" class="w-16 h-16" alt="Butterfly" />
          <h2 class="text-2xl">Butterfly</h2>
          <div class="flex flex-col text-right">
            <p>Product Design</p>
            <p>UI / UX</p>
            <p>Experience</p>
          </div>
          <a target="_blank" href="http://butterfly-air.com">
            <Button>Visit Website</Button>
          </a>
          <div class="flex flex-col text-right sm:max-w-[60%]">
            <p class="text-sm sm:text-base max-w-[400px]">
              When butterflies are present, we know the air is healthy.
              Butterfly devices measure Indoor Air Quality to an unparalleled
              level of accuracy and reliability based on our unique patented
              LaminAIR flow technology.
            </p>
          </div>
        </div>
        <div class="flex flex-col w-1/2 items-start space-y-12">
          <img src="/next/penta.svg" class="w-16 h-16" alt="Penta" />
          <h2 class="text-2xl">White City Sculpture</h2>
          <div class="flex flex-col text-left">
            <p>Art</p>
            <p>Science</p>
            <p>Challenge</p>
          </div>
          <a
            target="_blank"
            href="https://www.eventbrite.co.uk/e/white-city-sculpture-challenge-2022-registration-259502698557?aff=efbneb"
          >
            <Button>Eventbrite</Button>
          </a>
          <div class="flex flex-col text-left sm:max-w-[60%]">
            <p class="text-sm sm:text-base max-w-[400px]">
              Imperial’s first student-led installation challenge is driving
              synergy between art and science. The 2022 Sculpture Challenge
              provides a chance for bright and diverse minds to collaborate and
              bring their vision to reality on the White City Campus.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
