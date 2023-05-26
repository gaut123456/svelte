<script>
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';

  const images = [
    'https://picsum.photos/800/400?random=1',
    'https://picsum.photos/800/400?random=2',
    'https://picsum.photos/800/400?random=3',
    'https://picsum.photos/800/400?random=4',
    'https://picsum.photos/800/400?random=5'
  ];

  let currentImage = 0;
  let autoAdvance;

  const nextImage = () => {
    currentImage = (currentImage + 1) % images.length;
  };

  const prevImage = () => {
    currentImage = (currentImage - 1 + images.length) % images.length;
  };

  onMount(() => {
    autoAdvance = setInterval(() => {
      nextImage();
    }, 5000);

    return () => {
      clearInterval(autoAdvance);
    };
  });
</script>

<div class="carousel">
  {#each images as image, i}
    <img
      src={image}
      alt={`Image ${i + 1}`}
      class={i === currentImage ? 'active' : ''}
      transition:fade
    />
  {/each}

  <span class="arrow left" on:click={prevImage}>&larr;</span>
  <span class="arrow right" on:click={nextImage}>&rarr;</span>
</div>

<style>
  .carousel {
    position: relative;
    overflow: hidden;
    width: 100%;
    height: 400px;
  }

  img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: 0;
    transition: opacity 0.5s ease-in-out;
  }

  img.active {
    opacity: 1;
  }

  .arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    padding: 0.5rem;
    font-size: 2rem;
    color: #fff;
    cursor: pointer;
    z-index: 1;
  }

  .left {
    left: 0;
  }

  .right {
    right: 0;
  }
</style>