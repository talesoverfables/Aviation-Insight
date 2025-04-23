<script lang="ts">
    import { goto } from '$app/navigation';
  
    const goToMap = () => {
      goto('/map');
    };
</script>
  
<main class="min-h-screen flex items-center justify-center bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500 text-center px-4">
  <div class="bg-white rounded-3xl shadow-2xl p-8 max-w-lg w-full">
    <h1 class="text-4xl md:text-5xl font-bold text-gray-800 mb-6">
      Welcome to the METAR Weather Map
    </h1>
    <p class="text-lg text-gray-600 mb-8">
      Explore real-time aviation weather summaries across the map.
    </p>
  
    <button
      on:click={goToMap}
      class="w-full px-8 py-4 bg-gradient-to-r from-blue-600 to-purple-600 hover:from-blue-700 hover:to-purple-700 text-white text-lg rounded-xl shadow-lg transition duration-200 transform hover:scale-105"
    >
      Go to Interactive Map
    </button>
  </div>
</main>
  
  
