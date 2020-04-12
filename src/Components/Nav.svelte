<section class="Header-section">
	<a class="Logotype" href="#home">MaskFashion</a>
	<div class="Menu">
		<div class="desktop-links">
			<a class="{ isActive('buy') }" href="/buy">Buy a Mask</a>
			<a class="{ isActive('make') }" href="/make">Make a Mask</a>
			<a class="{ isActive('donate') }" href="/donate">Donate a Mask</a>
		</div>
		<div class="mobile-burger">
			<button
				aria-haspopup="true"
				aria-label="Navigation menu"
			>
				<svg 
					xmlns="http://www.w3.org/2000/svg" 
					height="24" 
					viewBox="0 0 24 24" 
					width="24" 
					aria-hidden="true"
				>
    				<path d="M0 0h24v24H0z" fill="none"/>
    				<path d="M3 18h18v-2H3v2zm0-5h18v-2H3v2zm0-7v2h18V6H3z"/>
				</svg>
				<span class="sr-only">Click to open navbar</span>
			</button>
		</div>
	</div>
</section>

<script>
  export let active;
  $: isActive = str => active === str ? 'selected' : '';
</script>

<style type="text/scss">
  @import '../styles/core';
  .Header-section {
  	display: flex;
    justify-content: space-between;
	height: 70px;
	padding: 20px 0;

	a {
		text-decoration: none;
		color: black;
	}

	.Logotype {
		font-size: 24px;
	}

    .Menu {
		text-align: right;
		
    	a {
			padding-left: $unit;
		}
		
		.desktop-links {
			display: none;
		}

		.mobile-burger {
			.sr-only {
				height: 1px;
				overflow: hidden;
				position: absolute;
				width: 1px;
			}
		}
    }
  }

  @media (min-width: 768px) {
	  .Header-section{
		  .Menu {
			  .desktop-links {
				  display: inline;
				  font-size: 18px;
			  }

			  .mobile-burger {
				  display: none;
			  }
		  }
	  }

  }

</style>


