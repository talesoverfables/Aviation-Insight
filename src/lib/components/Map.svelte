<script lang="ts">
  import { onMount } from 'svelte';
  import pkg from '@googlemaps/js-api-loader';
  const { Loader } = pkg; // ✅ Works with CommonJS

  let map: google.maps.Map;
  let mapContainer: HTMLDivElement;

  const apiKey = import.meta.env.VITE_GOOGLE_MAPS_API_KEY;

  const defaultCenter = { lat: 37.0902, lng: -95.7129 }; // USA
  const defaultZoom = 4;

  onMount(() => {
    if (!apiKey) {
      console.error('Google Maps API key is missing!');
      return;
    }

    const loader = new Loader({
      apiKey,
      version: 'weekly',
    });

    loader
      .load()
      .then(() => {
        map = new google.maps.Map(mapContainer, {
          center: defaultCenter,
          zoom: defaultZoom,
        });
      })
      .catch((err) => {
        console.error('Google Maps API failed to load:', err);
      });
  });
</script>

<!-- Full screen responsive map container using Tailwind -->
<div bind:this={mapContainer} class="w-full h-screen"></div>

