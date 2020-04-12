
<main class="App">

  <Cytosis 
    airKey={'keylYLkFHWTY3b8Ca'} 
    airBase={'appU40RlkLFNfoQ3X'} 
    tableQuery={'all-tables'}
    routeName={'all-content'}
    bind:cytosis={data}
  >
    <HeaderSection />
    <HeroSection />
    <MakerSection />
    <MakeAMaskSection />
    <CommunitiesSection />
    <DonateSection />
    <FYISection />
    <FooterSection />
  </Cytosis>
</main>




<script>
  import Cytosis from './Components/Cytosis.svelte'
  import { cytosis, makers, dropoff, content } from './stores.js';
  // import { onMount } from 'svelte'
  // import Search from './Search.svelte'
  // import SearchResults from './SearchResults.svelte'
  // import LoadingIndicator from './Components/LoadingIndicator.svelte'

  let data
  // cytosis.update(data)

  $: if(data) {
    cytosis.set(data)
    makers.set(data.tables['Mask Makers'])
    dropoff.set(data.tables['Mask Dropoff'])
    content.set(data.tables['Site Content'])

    console.log('$cytosis updated: ', $cytosis )
    console.log('$makers updated: ', $makers )
    console.log('$content updated: ', $content )

    console.log('_cytosis updated: ', data )
  }


  import HeaderSection from './HeaderSection.svelte'
  import HeroSection from './HeroSection.svelte'
  import MakerSection from './MakerSection.svelte'
  import MakeAMaskSection from './MakeAMaskSection.svelte'
  import CommunitiesSection from './CommunitiesSection.svelte'
  import DonateSection from './DonateSection.svelte'
  import FYISection from './FYISection.svelte'
  import FooterSection from './FooterSection.svelte'


</script>




<style type="text/scss">
  @import './styles/core';

  .App {
    width: 100%;
    max-width: 1500px;
    padding: $unit * 2;
    padding-top: 0;
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







