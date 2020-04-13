
<div class="App">

  <Cytosis 
    airKey={'keylYLkFHWTY3b8Ca'} 
    airBase={'appU40RlkLFNfoQ3X'} 
    tableQuery={'all-tables'}
    routeName={'all-content'}
    bind:cytosis={data}
  >
    {#if isLoading}
      Content is loading
    {/if}

    {#if !isLoading}
      <HeroSection />
      <MakerSection />
      <MakeAMaskSection />
      <CommunitiesSection />
      <DonateSection />
      <FYISection />
      <FooterSection />
    {/if}
  </Cytosis>
</div>


<script>

  import Cytosis from '../components/Cytosis.svelte'
  import { cytosis, makers, dropoff, content } from '../stores.js';
  // import { onMount } from 'svelte'
  // import Search from './Search.svelte'
  // import SearchResults from './SearchResults.svelte'
  // import LoadingIndicator from './components/LoadingIndicator.svelte'

  import HeroSection from '../sections/HeroSection.svelte'
  import MakerSection from '../sections/MakerSection.svelte'
  import MakeAMaskSection from '../sections/MakeAMaskSection.svelte'
  import CommunitiesSection from '../sections/CommunitiesSection.svelte'
  import DonateSection from '../sections/DonateSection.svelte'
  import FYISection from '../sections/FYISection.svelte'
  import FooterSection from '../sections/FooterSection.svelte'


  let data
  let isLoading = true
  // cytosis.update(data)

  $: if(data) {
    isLoading = false
    cytosis.set(data)
    makers.set(data.tables['Mask Makers'])
    dropoff.set(data.tables['Mask Dropoff'])
    content.set(data.tables['Site Content'])

    console.log('$cytosis updated: ', $cytosis )
    console.log('$makers updated: ', $makers )
    console.log('$content updated: ', $content )
    console.log('_cytosis updated: ', data )
  }

</script>







