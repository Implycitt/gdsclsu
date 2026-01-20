<script>
  import { onMount } from 'svelte';
  import gsap from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';

  gsap.registerPlugin(ScrollTrigger);

  onMount(() => {
    const containers = gsap.utils.toArray('#container');
    containers.forEach((container) => {
      gsap.to(container, {
        autoAlpha: 0,
        ease: "power1.in",
        scrollTrigger: {
          trigger: container,
          pin: true,
          scrub: true
        }
      });
    });
  });
</script>
 
<div class="grid min-h-dvh place-items-center gap-10 grid-template-rows-[auto]">
  <div class="flex flex-col items-center gap-20">
    <div id="container">
      <h1 class="text-9xl"> about us </h1>
    </div>

    <div id="container" class="p-5 text-center">
      We grow by learning together, through hands-on projects, workshops, and real world challenges that push us beyond the classroom. Whether you're new to tech or an experienced builder, there's always more to explore.
    </div>

    <div id="container" class="p-5 text-center">
      Make a difference through tech-driven social impact initiatives. Give back to the community.
    </div>
  </div>
</div>

<style>
  #container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 4rem;
    visibility: hidden;
  }
</style>