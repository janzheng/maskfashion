<script>
  import { onMount } from 'svelte'
  // import Search from './Search.svelte'
  // import SearchResults from './SearchResults.svelte'
  // import LoadingIndicator from './Components/LoadingIndicator.svelte'


  import HeaderSection from './HeaderSection.svelte'
  import HeroSection from './HeroSection.svelte'
  import MakerSection from './MakerSection.svelte'
  import MakeAMaskSection from './MakeAMaskSection.svelte'
  import CommunitiesSection from './CommunitiesSection.svelte'
  import DonateSection from './DonateSection.svelte'
  import FYISection from './FYISection.svelte'
  import FooterSection from './FooterSection.svelte'


</script>

<main class="App">

  <HeaderSection />
  <HeroSection />
  <MakerSection />
  <MakeAMaskSection />
  <CommunitiesSection />
  <DonateSection />
  <FYISection />
  <FooterSection />
</main>




<style type="text/scss">
  @import './styles/core';

  // general app styles 
  .App {
    width: 100%;
    max-width: 1500px;
    padding: $unit * 2;
  }

  * {
    font-family: $font-stack;
    font-size: $unit;
    line-height: $line-height;
  }

  :global(h1, h2, h3, h4) {
    font-weight: bold;
    padding-bottom: $unit;
  }



</style>







