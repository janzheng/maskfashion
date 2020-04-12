
<div class="Header-section">
	<div class="Logotype">MaskFashion</div>
	<div class="Menu">
		<a class="{ isActive('buy') }" href="/buy">Buy a Mask</a>
		<a class="{ isActive('make') }" href="/make">Make a Mask</a>
		<a class="{ isActive('donate') }" href="/donate">Donate a Mask</a>
	</div>
</div>


<script>
  export let active;
  $: isActive = str => active === str ? 'selected' : '';


</script>


<style type="text/scss">
  @import '../styles/core';

  // general app styles 
  .Header-section {
  	display: grid;
  	grid-template-columns: 1fr 2fr;
    grid-template-rows: 1fr;

    .Menu {
    	text-align: right;
    	
    	a {
    		padding-left: $unit;
    	}
    }
  }



</style>


