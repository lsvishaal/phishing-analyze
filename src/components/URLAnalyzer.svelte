<script lang="ts">
  // Script part for your component's logic and data
  let url: string = '';
  let activeTab: string = 'Nmap';

  function handleAnalyze() {
    console.log('Analyzing URL:', url);
    // Add logic to handle URL analysis
  }

  function setActiveTab(tab: string) {
    activeTab = tab;
  }
</script>

<div class="min-h-screen bg-cyan-400 flex justify-center items-center p-4">
  <div class="bg-white dark:bg-red-100 drop-shadow-xl p-8 rounded-lg w-full max-w-3xl">
    <h2 class="text-3xl font-bold mb-6 text-center tracking-tight text-red-500 ">URL Analyzer</h2>

    <!-- Input and Analyze Button -->
    <div class="flex items-center space-x-4 mb-6">
      <input
        type="text"
        placeholder="Enter URL to analyze"
        bind:value={url}
        class="w-full p-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-cyan-500"
      />
      <button
        class="bg-cyan-600 text-white px-4 py-3 rounded-lg hover:bg-cyan-700 transition-all"
        on:click={handleAnalyze}
      >
        Analyze
      </button>
    </div>

    <!-- Analysis Results Container -->
    <div class="p-6 bg-gray-50 rounded-lg">
      <h3 class="text-lg font-semibold mb-4 text-gray-700">Analysis Results</h3>

      <!-- Tabs for Different Tools -->
      <div class="flex mb-6 border-b border-gray-300">
        <button
          class="py-2 px-4 text-sm font-medium transition-all"
          class:active={activeTab === 'Nmap'}
          on:click={() => setActiveTab('Nmap')}
        >
          Nmap
        </button>
        <button
          class="py-2 px-4 text-sm font-medium transition-all"
          class:active={activeTab === 'Gobuster'}
          on:click={() => setActiveTab('Gobuster')}
        >
          Gobuster
        </button>
        <button
          class="py-2 px-4 text-sm font-medium transition-all"
          class:active={activeTab === 'Wappalyzer'}
          on:click={() => setActiveTab('Wappalyzer')}
        >
          Wappalyzer
        </button>
        <button
          class="py-2 px-4 text-sm font-medium transition-all"
          class:active={activeTab === 'Grammar & Text'}
          on:click={() => setActiveTab('Grammar & Text')}
        >
          Grammar & Text
        </button>
      </div>

      <!-- Display Analysis Results -->
      <div class="mt-4">
        <p class="text-gray-500">No results yet. Enter a URL and click 'Analyze'.</p>
      </div>
    </div>
  </div>
</div>

<style>
  .active {
    border-bottom: 2px solid #06b6d4; /* Cyan color for the active tab */
    color: #06b6d4;
  }
</style>
